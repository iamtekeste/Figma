---

ExportMixin

# Interface: ExportMixin

Defined in: figmaPluginTypes.ts:6744

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`DefaultShapeMixin`](DefaultShapeMixin.md)
- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`OpaqueNodeMixin`](OpaqueNodeMixin.md)
- [`PageNode`](PageNode.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)
- [`SliceNode`](SliceNode.md)

## Properties

### exportSettings

> **exportSettings**: readonly [`ExportSettings`](../type-aliases/ExportSettings.md)[]

Defined in: figmaPluginTypes.ts:6748

List of export settings stored on the node. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

## Methods

### exportAsync()

#### Call Signature

> **exportAsync**(`settings?`): `Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

Defined in: figmaPluginTypes.ts:6811

Exports the node as an encoded image.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

##### Parameters

###### settings?

[`ExportSettings`](../type-aliases/ExportSettings.md)

When this parameter is absent, this function defaults to exporting as a PNG at 1x resolution.

Note that the result is a Uint8Array, representing the bytes of the image file (encoded in the specified format).

```ts title="Create a hexagon, export as PNG, and place on canvas"
(async () => {
  const polygon = figma.createPolygon();
  polygon.pointCount = 6;
  polygon.fills = [{ type: "SOLID", color: { r: 1, g: 0, b: 0 } }];

  // highlight-start
  // Export a 2x resolution PNG of the node
  const bytes = await polygon.exportAsync({
    format: "PNG",
    constraint: { type: "SCALE", value: 2 },
  });
  // highlight-end

  // Add the image onto the canvas as an image fill in a frame
  const image = figma.createImage(bytes);
  const frame = figma.createFrame();
  frame.x = 200;
  frame.resize(200, 230);
  frame.fills = [
    {
      imageHash: image.hash,
      scaleMode: "FILL",
      scalingFactor: 1,
      type: "IMAGE",
    },
  ];
})();
```

```ts title="Export a VectorNode as an SVG string"
(async () => {
  // Create a triangle using the VectorPath API
  const vector = figma.createVector();
  vector.vectorPaths = [
    {
      windingRule: "EVENODD",
      data: "M 0 100 L 100 100 L 50 0 Z",
    },
  ];

  // highlight-start
  // Export the vector to SVG
  const svg = await vector.exportAsync({ format: "SVG_STRING" });
  // highlight-end
  console.log(svg);
})();
```

```ts title="Export a node as a JSON object"
(async () => {
  const json = await figma.currentPage.selection[0].exportAsync({
    format: "JSON_REST_V1",
  });
  // Return a JSON object in the same format as the Figma REST API response
  console.log(json.document);
})();
```

##### Returns

`Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`string`\>

Defined in: figmaPluginTypes.ts:6812

##### Parameters

###### settings

[`ExportSettingsSVGString`](ExportSettingsSVGString.md)

##### Returns

`Promise`\<`string`\>

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`Object`\>

Defined in: figmaPluginTypes.ts:6813

##### Parameters

###### settings

[`ExportSettingsREST`](ExportSettingsREST.md)

##### Returns

`Promise`\<`Object`\>
