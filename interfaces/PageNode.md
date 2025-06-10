---

PageNode

# Interface: PageNode

Defined in: figmaPluginTypes.ts:8279

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`BaseNodeMixin`](BaseNodeMixin.md).[`ChildrenMixin`](ChildrenMixin.md).[`ExportMixin`](ExportMixin.md).[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`MeasurementsMixin`](MeasurementsMixin.md)

## Properties

### backgrounds

> **backgrounds**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:8365

The background color of the canvas (currently only supports a single solid color paint).

---

### children

> `readonly` **children**: readonly [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5369

The list of children, sorted back-to-front. That is, the first child in the array is the bottommost layer on the screen, and the last child in the array is the topmost layer.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this property.

#### Remarks

This array can be read like and iterated like a regular array. However, calling this property always returns a new array, and both the property and the new array are read-only.

As such, this property cannot be assigned to, and the array cannot be modified directly (it wouldn't do anything). Instead, use [ChildrenMixin.appendChild](ChildrenMixin.md#appendchild), [ChildrenMixin.insertChild](ChildrenMixin.md#insertchild) or [BaseNodeMixin.remove](BaseNodeMixin.md#remove).

Note: If you are curious, the reason why inserting children has to be done via API calls is because our internal representation for the layer tree uses [fractional indexing](https://www.figma.com/blog/multiplayer-editing-in-figma/) and [ChildrenMixin.insertChild](ChildrenMixin.md#insertchild) performs that conversion.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`children`](ChildrenMixin.md#children)

---

### explicitVariableModes

> **explicitVariableModes**: `object`

Defined in: figmaPluginTypes.ts:8250

The explicitly set modes for this node.
For `SceneNodes`, represents a subset of [SceneNodeMixin.resolvedVariableModes](SceneNodeMixin.md#resolvedvariablemodes).
Note that this does not include [workspace and team-default modes](https://help.figma.com/hc/en-us/articles/12611253730071).

#### Index Signature

\[`collectionId`: `string`\]: `string`

#### Inherited from

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`explicitVariableModes`](ExplicitVariableModesMixin.md#explicitvariablemodes)

---

### exportSettings

> **exportSettings**: readonly [`ExportSettings`](../type-aliases/ExportSettings.md)[]

Defined in: figmaPluginTypes.ts:6748

List of export settings stored on the node. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportSettings`](ExportMixin.md#exportsettings)

---

### flowStartingPoints

> **flowStartingPoints**: readonly `object`[]

Defined in: figmaPluginTypes.ts:8358

The sorted list of flow starting points used when accessing Presentation view.

#### Remarks

The default starting point is the first one (e.g., used when no frames are selected and you click the toolbar's play icon to enter Presentation view).

---

### focusedSlide?

> `optional` **focusedSlide**: `null` \| [`SlideNode`](SlideNode.md)

Defined in: figmaPluginTypes.ts:8454

Note: This API is only available in Figma Slides

When in single slide view, the Slide that is currently focused is accessible via this property.

#### Remarks

You can also set this via:

```ts
figma.currentPage.focusedSlide = slideNode;
```

---

### guides

> **guides**: readonly [`Guide`](Guide.md)[]

Defined in: figmaPluginTypes.ts:8308

The guides on this page.

#### Remarks

Like many of our array properties, `page.guide` creates a new, read-only array every time it is called. To change the guides, you will need to make a copy of the existing array and/or assign a new array.

Example:

```ts
function addNewGuide(page: PageNode, guide: Guide) {
  // .concat() creates a new array
  page.guides = page.guides.concat(guide);
}
```

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:4878

The unique identifier of a node. For example, `1:3`. The node id can be used with methods such as [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync), but plugins typically don't need to use this since you can usually just access a node directly.

#### Remarks

One possible use case for using the `id` is to have a serializable representation of a Figma node. To "deserialize" an id back into a node, pass it to [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync). This will return null if the node is no longer present in the document.

In the URLs for Figma files, node ids are hyphenated. However, for use with the API, node ids must use colons. For example, if a Figma file URL has the node id `1-3`, you must convert it to `1:3`.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`id`](BaseNodeMixin.md#id)

---

### isAsset

> `readonly` **isAsset**: `boolean`

Defined in: figmaPluginTypes.ts:5010

Returns true if Figma detects that a node is an asset, otherwise returns false. An asset is is either an icon or a raster image.

This property is useful if you’re building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

Note: This property uses a set of heuristics to determine if a node is an asset. At a high level an icon is a small vector graphic and an image is a node with an image fill.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`isAsset`](BaseNodeMixin.md#isasset)

---

### isPageDivider

> **isPageDivider**: `boolean`

Defined in: figmaPluginTypes.ts:8377

Returns true if the node is a page divider, which is only possible when the page node is empty and has a page divider name. A page divider name consists of all asterisks, all en dashes, all em dashes, or all spaces.

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:4898

The name of the layer that appears in the layers panel. Calling `figma.root.name` will return the name, read-only, of the current file.

#### Remarks

If the node is a [TextNode](TextNode.md), the name will update automatically by default based on the `characters` property (`autoRename` is true). If you manually override the text node's name, it will set `autoRename` to false. This matches the behavior in the editor.

If the node is a PageNode with no children and the name is a page divider name, it will set `isPageDivider` to true. A page divider name consists of all asterisks, all en dashes, all em dashes, or all spaces.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`name`](BaseNodeMixin.md#name)

---

### parent

> `readonly` **parent**: `null` \| BaseNode & ChildrenMixin

Defined in: figmaPluginTypes.ts:4888

Returns the parent of this node, if any. This property is not meant to be directly edited. To reparent, see [ChildrenMixin.appendChild](ChildrenMixin.md#appendchild).

#### Remarks

The root node (i.e. `figma.root`) doesn't have a parent.

Components accessed via [instance.getMainComponentAsync()](InstanceNode.md#getmaincomponentasync) or [instance.mainComponent](InstanceNode.md#maincomponent) do not always have a parent. They could be remote components or soft-deleted components.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`parent`](BaseNodeMixin.md#parent)

---

### prototypeBackgrounds

> **prototypeBackgrounds**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:8369

The background color of the prototype (currently only supports a single solid color paint).

---

### prototypeStartNode

> `readonly` **prototypeStartNode**: `null` \| [`FrameNode`](FrameNode.md) \| [`GroupNode`](GroupNode.md) \| [`ComponentNode`](ComponentNode.md) \| [`InstanceNode`](InstanceNode.md)

Defined in: figmaPluginTypes.ts:8373

The starting point when launching a prototype. Prototypes with a starting node contain all frames reachable from that node. Prototypes without a starting node contain all frames on the current page. Note that prototypes are per-page.

---

### removed

> `readonly` **removed**: `boolean`

Defined in: figmaPluginTypes.ts:4911

Returns true if this node has been removed since it was first accessed. If your plugin stays open for a while and stores references to nodes, you should write your code defensively and check that the nodes haven't been removed by the user.

#### Remarks

A node can be removed for any number of reasons. Some examples:

- Your plugin called node.remove() on it
- Someone else deleted the node using multiplayer
- The user triggered an undo action and the node was removed
- The user simply deleted the node
- You removed all children out of a group, and the group auto-deleted itself

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`removed`](BaseNodeMixin.md#removed)

---

### selectedTextRange

> **selectedTextRange**: `null` \| \{ `end`: `number`; `node`: [`TextNode`](TextNode.md); `start`: `number`; \}

Defined in: figmaPluginTypes.ts:8346

The current text node being edited, if any, and the text currently being selected within that text node.

#### Remarks

This property will return `null` if there is no text node being edited. Setting this property to a `node` will enter text edit mode on that `node`. Leaving text edit mode will set this value to `null`.

When `start == end`, it means that no characters is currently selected -- i.e., there is just a cursor.

Changing `selectedTextRange` will trigger a `selectionchanged` message.

---

### selection

> **selection**: readonly [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:8334

The selected nodes on this page. Each page stores its own selection separately. The ordering of nodes in the selection is **unspecified**, you should not be relying on it.

#### Remarks

Like many of our array properties, `page.selection` returns a new, read-only array every time it is called (the nodes inside are references to existing nodes, not copies). To change the selection, you will need to make a copy of the existing array and/or assign a new array.

Example:

```ts
function addNewNodeToSelection(page: PageNode, node: SceneNode) {
  // .concat() creates a new array
  page.selection = page.selection.concat(node);
}

function selectFirstChildOfNode(page: PageNode, node: SceneNode) {
  if (node.children.length > 0) {
    page.selection = [node.children[0]];
  }
}
```

- As the selection is just a node property, the selection is preserved when the user switches between pages.
- Nodes in the selection are unique. When setting the selection, the API will de-deduplicate nodes in the selection. This API could have been a `Set<SceneNode>`, but it's generally easier to work with array and to get the first node using just selection[0].
- Only **directly selected nodes** are present in this array. A node is directly selected when it is selected and none of its ancestors are selected. That means the array will never contain both a node and one of its descendents.

---

### type

> `readonly` **type**: `"PAGE"`

Defined in: figmaPluginTypes.ts:8288

The type of this node, represented by the string literal "PAGE"

## Methods

### addDevResourceAsync()

> **addDevResourceAsync**(`url`, `name?`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5100

Adds a dev resource to a node. This will fail if the node already has a dev resource with the same url.

#### Parameters

##### url

`string`

The url of the dev resource.

##### name?

`string`

The name of the dev resource. If not provided, Figma will get the name from the url.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`addDevResourceAsync`](BaseNodeMixin.md#adddevresourceasync)

---

### addMeasurement()

> **addMeasurement**(`start`, `end`, `options?`): [`Measurement`](Measurement.md)

Defined in: figmaPluginTypes.ts:7288

Adds a measurement between two nodes in the current page.

Measurements are always between a start and end node. The side indicates which edge of the node to draw the measurement from.

Measurements can only go on the same axis, i.e. from side `"LEFT"` -> `"LEFT"`, `"LEFT"` -> `"RIGHT"`, `"TOP"` -> `"BOTTOM"` etc. But not `"LEFT"` -> `"TOP"`.

See the [Measurement type](https://www.figma.com/plugin-docs/api/Measurement) for usage examples.

Note: This method is only available in Dev Mode. You can check the editor type of your plugin to know if the user is in Dev Mode or not:

```ts
if (figma.editorType === "dev") {
  // In Figma's Dev Mode
}
```

#### Parameters

##### start

###### node

[`SceneNode`](../type-aliases/SceneNode.md)

###### side

[`MeasurementSide`](../type-aliases/MeasurementSide.md)

##### end

###### node

[`SceneNode`](../type-aliases/SceneNode.md)

###### side

[`MeasurementSide`](../type-aliases/MeasurementSide.md)

##### options?

###### freeText?

`string`

###### offset?

[`MeasurementOffset`](../type-aliases/MeasurementOffset.md)

**Default**

```ts
{
  type: "INNER";
  relative: 0;
}
```

#### Returns

[`Measurement`](Measurement.md)

#### Inherited from

[`MeasurementsMixin`](MeasurementsMixin.md).[`addMeasurement`](MeasurementsMixin.md#addmeasurement)

---

### appendChild()

> **appendChild**(`child`): `void`

Defined in: figmaPluginTypes.ts:5381

Adds a new child to the end of the [ChildrenMixin.children](ChildrenMixin.md#children) array. That is, visually on top of all other children.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### child

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

`void`

#### Remarks

Reparenting nodes is subject to many restrictions. For example, some nodes cannot be moved, others would break the document if moved. Below are possible exceptions that can be thrown if the operation is invalid.

If this is called on an auto-layout frame, calling this function can cause this layer to be resized and children to be moved.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`appendChild`](ChildrenMixin.md#appendchild)

---

### clearExplicitVariableModeForCollection()

#### Call Signature

> **clearExplicitVariableModeForCollection**(`collectionId`): `void`

Defined in: figmaPluginTypes.ts:8258

Clears an explicit mode for the given collection on this node

##### Parameters

###### collectionId

`string`

##### Returns

`void`

##### Deprecated

Use `clearExplicitVariableModeForCollection(VariableCollection)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

##### Inherited from

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`clearExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#clearexplicitvariablemodeforcollection)

#### Call Signature

> **clearExplicitVariableModeForCollection**(`collection`): `void`

Defined in: figmaPluginTypes.ts:8264

Clears an explicit mode for the given collection on this node

##### Parameters

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a variable collection ID is deprecated.

##### Returns

`void`

##### Inherited from

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`clearExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#clearexplicitvariablemodeforcollection)

---

### clone()

> **clone**(): `PageNode`

Defined in: figmaPluginTypes.ts:8292

Create a clone of this page, parented under [PluginAPI.root](PluginAPI.md#root). Prototyping connections will be copied such that they point to their equivalent in the cloned page. Components will be cloned as instances who master is the original component.

#### Returns

`PageNode`

---

### deleteDevResourceAsync()

> **deleteDevResourceAsync**(`url`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5122

Deletes a dev resource on a node. This will fail if the node does not have a dev resource with the same url.

#### Parameters

##### url

`string`

The url of the dev resource.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`deleteDevResourceAsync`](BaseNodeMixin.md#deletedevresourceasync)

---

### deleteMeasurement()

> **deleteMeasurement**(`id`): `void`

Defined in: figmaPluginTypes.ts:7338

Delete a measurement.

See the [Measurement type](https://www.figma.com/plugin-docs/api/Measurement) for usage examples.

Note: This method is only available in Dev Mode. You can check the editor type of your plugin to know if the user is in Dev Mode or not:

```ts
if (figma.editorType === "dev") {
  // In Figma's Dev Mode
}
```

#### Parameters

##### id

`string`

#### Returns

`void`

#### Inherited from

[`MeasurementsMixin`](MeasurementsMixin.md).[`deleteMeasurement`](MeasurementsMixin.md#deletemeasurement)

---

### editDevResourceAsync()

> **editDevResourceAsync**(`currentUrl`, `newValue`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5109

Edits a dev resource on a node. This will fail if the node does not have a dev resource with the same url.

#### Parameters

##### currentUrl

`string`

The current url of the dev resource.

##### newValue

The new name and/or url of the dev resource.

###### name?

`string`

###### url?

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`editDevResourceAsync`](BaseNodeMixin.md#editdevresourceasync)

---

### editMeasurement()

> **editMeasurement**(`id`, `newValue`): [`Measurement`](Measurement.md)

Defined in: figmaPluginTypes.ts:7318

Edit a measurement’s offset.

See the [Measurement type](https://www.figma.com/plugin-docs/api/Measurement) for usage examples.

Note: This method is only available in Dev Mode. You can check the editor type of your plugin to know if the user is in Dev Mode or not:

```ts
if (figma.editorType === "dev") {
  // In Figma's Dev Mode
}
```

#### Parameters

##### id

`string`

##### newValue

###### freeText?

`string`

###### offset?

[`MeasurementOffset`](../type-aliases/MeasurementOffset.md)

#### Returns

[`Measurement`](Measurement.md)

#### Inherited from

[`MeasurementsMixin`](MeasurementsMixin.md).[`editMeasurement`](MeasurementsMixin.md#editmeasurement)

---

### exportAsync()

#### Call Signature

> **exportAsync**(`settings?`): `Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

Defined in: figmaPluginTypes.ts:6811

Exports the node as an encoded image.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

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

##### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportAsync`](ExportMixin.md#exportasync)

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`string`\>

Defined in: figmaPluginTypes.ts:6812

##### Parameters

###### settings

[`ExportSettingsSVGString`](ExportSettingsSVGString.md)

##### Returns

`Promise`\<`string`\>

##### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportAsync`](ExportMixin.md#exportasync)

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`Object`\>

Defined in: figmaPluginTypes.ts:6813

##### Parameters

###### settings

[`ExportSettingsREST`](ExportSettingsREST.md)

##### Returns

`Promise`\<`Object`\>

##### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportAsync`](ExportMixin.md#exportasync)

---

### findAll()

> **findAll**(`callback?`): [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5459

Searches this entire subtree (this node's children, its children's children, etc). Returns all nodes for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### callback?

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`. If this argument is omitted, `findAll` returns all nodes in the subtree.

#### Returns

[`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

Nodes are included in **back-to-front** order. Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

This traversal method is known as ["pre-order traversal"](<https://en.wikipedia.org/wiki/Tree_traversal#Pre-order_(NLR)>).

Note that the node this method is called on is **not included**.

Example: find all nodes whose name is "Color":

```ts
const colors = figma.currentPage.findAll((n) => n.name === "Color");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
If you only need to search immediate children, it is much faster to call `node.children.filter(callback)` or `node.findChildren(callback)`.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findAll`](ChildrenMixin.md#findall)

---

### findAllWithCriteria()

> **findAllWithCriteria**\<`T`\>(`criteria`): `object` & [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5582

Searches this entire subtree (this node's children, its children's children, etc). Returns all nodes that satisfy all of specified criteria.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Type Parameters

##### T

`T` _extends_ (`"TEXT"` \| `"DOCUMENT"` \| `"PAGE"` \| `"SLICE"` \| `"FRAME"` \| `"GROUP"` \| `"COMPONENT_SET"` \| `"COMPONENT"` \| `"INSTANCE"` \| `"BOOLEAN_OPERATION"` \| `"VECTOR"` \| `"STAR"` \| `"LINE"` \| `"ELLIPSE"` \| `"POLYGON"` \| `"RECTANGLE"` \| `"TEXT_PATH"` \| `"TRANSFORM_GROUP"` \| `"STICKY"` \| `"CONNECTOR"` \| `"SHAPE_WITH_TEXT"` \| `"CODE_BLOCK"` \| `"STAMP"` \| `"WIDGET"` \| `"EMBED"` \| `"LINK_UNFURL"` \| `"MEDIA"` \| `"SECTION"` \| `"HIGHLIGHT"` \| `"WASHI_TAPE"` \| `"TABLE"` \| `"SLIDE"` \| `"SLIDE_ROW"` \| `"SLIDE_GRID"` \| `"INTERACTIVE_SLIDE_ELEMENT"`)[]

#### Parameters

##### criteria

[`FindAllCriteria`](FindAllCriteria.md)\<`T`\>

An object of type [FindAllCriteria](FindAllCriteria.md) that specifies the search criteria. The following criterias are currently supported:

- Nodes with specific [types](../type-aliases/NodeType.md)
- Nodes with [SharedPluginData](PluginDataMixin.md#getsharedplugindata) by their namespace and keys.
- Nodes with [PluginData](PluginDataMixin.md#getplugindata) by their keys.
- A combination of any of the above.

#### Returns

`object` & [`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

This is a faster but more limited search compared to [ChildrenMixin.findAll](ChildrenMixin.md#findall), which lets you search nodes based on any logic you can include in a callback.

When paired with [`figma.skipInvisibleInstanceChildren = true`](https://www.figma.com/plugin-docs/api/properties/figma-skipinvisibleinstancechildren), this method can be hundreds of times faster in large documents with tens of thousands of nodes.

The return value is narrowly typed to match the provided `types`, which makes it much easier to use node-type-specific properties. For example, `node.findAllWithCriteria({ types: ['TEXT'] })` will return `TextNode[]` instead of the more generic `SceneNode[]` from [ChildrenMixin.findAll](ChildrenMixin.md#findall).

Nodes are included in **back-to-front** order, which is the same order as in [ChildrenMixin.findAll](ChildrenMixin.md#findall). Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

This traversal method is known as ["pre-order traversal"](<https://en.wikipedia.org/wiki/Tree_traversal#Pre-order_(NLR)>).

Note: The node this method is called on is **not included**.

## Example Usages

### Find by node type

```ts
// Find all component and component set nodes in the current
// page
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["COMPONENT", "COMPONENT_SET"],
});

// Find all text nodes in the current page
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["TEXT"],
});
```

### Find by plugin data

```ts
// Find all nodes in the current page with plugin data
// for the current plugin.
const nodes = figma.currentPage.findAllWithCriteria({
  pluginData: {},
});

// Find all nodes in the current page with plugin data
// for the current plugin with keys "a" or "b"
const nodes = figma.currentPage.findAllWithCriteria({
  pluginData: {
    keys: ["a", "b"],
  },
});
```

### Find by shared plugin data

```ts
// Find all nodes in the current page with shared plugin data
// stored on the "bar" namespace
const nodes = figma.currentPage.findAllWithCriteria({
  sharedPluginData: {
    namespace: "bar",
  },
});

// Find all nodes in the current page with shared plugin data
// stored on the "bar" namespace and keys "a" or "b"
const nodes = figma.currentPage.findAllWithCriteria({
  sharedPluginData: {
    namespace: "bar",
    keys: ["a", "b"],
  },
});
```

### Combining criterias

You can combine multiple criterias for further narrow your search.

```ts
// Find all text nodes in the current page with plugin data
// for the current plugin
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["TEXT"],
  pluginData: {},
});

// Find all text nodes in the current page with shared plugin data
// stored on the "bar" namespace
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["TEXT"],
  sharedPluginData: {
    namespace: "bar",
  },
});
```

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findAllWithCriteria`](ChildrenMixin.md#findallwithcriteria)

---

### findChild()

> **findChild**(`callback`): `null` \| [`SceneNode`](../type-aliases/SceneNode.md)

Defined in: figmaPluginTypes.ts:5434

Searches the immediate children of this node (i.e. not including the children's children). Returns the first node for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### callback

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`.

#### Returns

`null` \| [`SceneNode`](../type-aliases/SceneNode.md)

#### Remarks

This function returns `null` if no matching node is found.

Example: find the first frame that is an immediate child of the current page.

```ts
const firstChildFrame = figma.currentPage.findChild((n) => n.type === "FRAME");
```

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findChild`](ChildrenMixin.md#findchild)

---

### findChildren()

> **findChildren**(`callback?`): [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5417

Searches the immediate children of this node (i.e. not including the children's children). Returns all nodes for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### callback?

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`. If this argument is omitted, `findChildren` returns `node.children`.

#### Returns

[`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

Example: find all frames that are immediate child of the current page.

```ts
const childFrames = figma.currentPage.findChildren((n) => n.type === "FRAME");
```

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findChildren`](ChildrenMixin.md#findchildren)

---

### findOne()

> **findOne**(`callback`): `null` \| [`SceneNode`](../type-aliases/SceneNode.md)

Defined in: figmaPluginTypes.ts:5481

Searches this entire subtree (this node's children, its children's children, etc). Returns the first node for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### callback

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`.

#### Returns

`null` \| [`SceneNode`](../type-aliases/SceneNode.md)

#### Remarks

This function returns `null` if no matching node is found. The traversal order is the same as in [ChildrenMixin.findAll](ChildrenMixin.md#findall).

Note that the node this method is called on is **not included**.

Example: find one node whose name is "Template":

```ts
const template = figma.currentPage.findOne((n) => n.name === "Template");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
If you only need to search immediate children, it is much faster to call `node.children.find(callback)` or `node.findChild(callback)`.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findOne`](ChildrenMixin.md#findone)

---

### findWidgetNodesByWidgetId()

> **findWidgetNodesByWidgetId**(`widgetId`): [`WidgetNode`](WidgetNode.md)[]

Defined in: figmaPluginTypes.ts:5600

Searches this entire subtree (this node's children, its children's children, etc). Returns all widget nodes that match the provided `widgetId`.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### widgetId

`string`

The widget ID to search for, which represents unique identifier for the widget.

#### Returns

[`WidgetNode`](WidgetNode.md)[]

#### Remarks

`node.widgetId` is not to be confused with `node.id`, which is the unique identifier for the node on the canvas. In other words, if you clone a widget, the cloned widget will have a matching `widgetId` but a different `id`.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findWidgetNodesByWidgetId`](ChildrenMixin.md#findwidgetnodesbywidgetid)

---

### getCSSAsync()

> **getCSSAsync**(): `Promise`\<\{[`key`: `string`]: `string`; \}\>

Defined in: figmaPluginTypes.ts:5014

Resolves to a JSON object of CSS properties of the node. This is the same CSS that Figma shows in the inspect panel and is helpful if you are building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

#### Returns

`Promise`\<\{[`key`: `string`]: `string`; \}\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getCSSAsync`](BaseNodeMixin.md#getcssasync)

---

### getDevResourcesAsync()

> **getDevResourcesAsync**(`options?`): `Promise`\<[`DevResourceWithNodeId`](DevResourceWithNodeId.md)[]\>

Defined in: figmaPluginTypes.ts:5091

Gets all of the dev resources on a node. This includes any inherited dev resources from components and component sets.

#### Parameters

##### options?

An optional parameter to include getting all of the dev resources on the children of the node. Defaults to false.

###### includeChildren?

`boolean`

#### Returns

`Promise`\<[`DevResourceWithNodeId`](DevResourceWithNodeId.md)[]\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getDevResourcesAsync`](BaseNodeMixin.md#getdevresourcesasync)

---

### getMeasurements()

> **getMeasurements**(): [`Measurement`](Measurement.md)[]

Defined in: figmaPluginTypes.ts:7266

Get all measurements in the current page.

Learn more about measurements in the [Help Center](https://help.figma.com/hc/en-us/articles/20774752502935).

#### Returns

[`Measurement`](Measurement.md)[]

#### Inherited from

[`MeasurementsMixin`](MeasurementsMixin.md).[`getMeasurements`](MeasurementsMixin.md#getmeasurements)

---

### getMeasurementsForNode()

> **getMeasurementsForNode**(`node`): [`Measurement`](Measurement.md)[]

Defined in: figmaPluginTypes.ts:7270

Get all measurements pointing to a node in the current page. This includes all measurements whose start _or_ end node is the node passed in.

#### Parameters

##### node

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

[`Measurement`](Measurement.md)[]

#### Inherited from

[`MeasurementsMixin`](MeasurementsMixin.md).[`getMeasurementsForNode`](MeasurementsMixin.md#getmeasurementsfornode)

---

### getPluginData()

> **getPluginData**(`key`): `string`

Defined in: figmaPluginTypes.ts:5031

Retrieves custom information that was stored on this node or style using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). If there is no data stored for the provided key, an empty string is returned.

#### Parameters

##### key

`string`

#### Returns

`string`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getPluginData`](BaseNodeMixin.md#getplugindata)

---

### getPluginDataKeys()

> **getPluginDataKeys**(): `string`[]

Defined in: figmaPluginTypes.ts:5053

Retrieves a list of all keys stored on this node or style using using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). This enables iterating through all data stored privately on a node or style by your plugin.

#### Returns

`string`[]

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getPluginDataKeys`](BaseNodeMixin.md#getplugindatakeys)

---

### getRelaunchData()

> **getRelaunchData**(): `object`

Defined in: figmaPluginTypes.ts:5000

Retreives the reluanch data stored on this node using [BaseNodeMixin.setRelaunchData](BaseNodeMixin.md#setrelaunchdata)

#### Returns

`object`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getRelaunchData`](BaseNodeMixin.md#getrelaunchdata)

---

### getSharedPluginData()

> **getSharedPluginData**(`namespace`, `key`): `string`

Defined in: figmaPluginTypes.ts:5057

Retrieves custom information that was stored on this node or style using [PluginDataMixin.setSharedPluginData](PluginDataMixin.md#setsharedplugindata). If there is no data stored for the provided namespace and key, an empty string is returned.

#### Parameters

##### namespace

`string`

##### key

`string`

#### Returns

`string`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getSharedPluginData`](BaseNodeMixin.md#getsharedplugindata)

---

### getSharedPluginDataKeys()

> **getSharedPluginDataKeys**(`namespace`): `string`[]

Defined in: figmaPluginTypes.ts:5079

Retrieves a list of all keys stored on this node or style using [PluginDataMixin.setSharedPluginData](PluginDataMixin.md#setsharedplugindata). This enables iterating through all data stored in a given namespace.

#### Parameters

##### namespace

`string`

#### Returns

`string`[]

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getSharedPluginDataKeys`](BaseNodeMixin.md#getsharedplugindatakeys)

---

### getTopLevelFrame()

> **getTopLevelFrame**(): `undefined` \| [`FrameNode`](FrameNode.md)

Defined in: figmaPluginTypes.ts:5022

Returns the top-most frame that contains this node. If the node is not inside a frame, this will return undefined.

Note: This function will only work in Figma Design and will throw an error if called in FigJam or Slides.

#### Returns

`undefined` \| [`FrameNode`](FrameNode.md)

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getTopLevelFrame`](BaseNodeMixin.md#gettoplevelframe)

---

### insertChild()

> **insertChild**(`index`, `child`): `void`

Defined in: figmaPluginTypes.ts:5402

Adds a new child at the specified index in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a PageNode, you must first call [PageNode.loadAsync](#loadasync) to access this function.

#### Parameters

##### index

`number`

Determines where the new layer gets inserted. For example, suppose a group has layers A, B, C, where C is the top-most layer.

- `insertChild(0, D)` gives a group with layers **D**, A, B, C
- `insertChild(1, D)` gives a group with layers A, **D**, B, C
- `insertChild(2, D)` gives a group with layers A, B, **D**, C
- `insertChild(3, D)` gives a group with layers A, B, C, **D**
- `insertChild(4, D)` throws an error since the group originally only has 3 children

##### child

[`SceneNode`](../type-aliases/SceneNode.md)

The node to be inserted.

#### Returns

`void`

#### Remarks

Reparenting nodes is subject to many restrictions. For example, some nodes cannot be moved, others would break the document if moved. Below are possible exceptions that can be thrown if the operation is invalid.

If this is called on an auto-layout frame, calling this function can cause this layer to be resized and children to be moved.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`insertChild`](ChildrenMixin.md#insertchild)

---

### loadAsync()

> **loadAsync**(): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:8381

Loads the contents of the page node.

#### Returns

`Promise`\<`void`\>

---

### off()

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:8439

Removes a callback added with [PageNode.on](#on) or [PageNode.once](#once).

#### Parameters

##### type

`"nodechange"`

##### callback

(`event`) => `void`

#### Returns

`void`

#### Remarks

The callback needs to be the same object that was originally added. For example, you can do this:

```ts title="Correct way to remove a callback"
let fn = () => {
  console.log("nodechange");
};
page.on("nodechange", fn);
page.off("nodechange", fn);
```

whereas the following won't work, because the function objects are different:

```ts title="Incorrect way to remove a callback"
page.on("nodechange", () => {
  console.log("nodechange");
});
page.off("nodechange", () => {
  console.log("nodechange");
});
```

---

### on()

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:8414

Registers a callback that will be invoked when an event occurs on the page. Current supported events are:

- `"nodechange"`: Emitted when a node is added, removed, or updated.

#### Parameters

##### type

`"nodechange"`

The type of event to listen for.

##### callback

(`event`) => `void`

The callback to be invoked when the event occurs.

#### Returns

`void`

#### Remarks

## Available event types

### `"nodechange"`

This event will be emitted when a node on the page is added, removed, or updated.

The callback will receive a NodeChangeEvent with the below interface:

```ts
interface NodeChangeEvent {
  nodeChanges: NodeChange[];
}
```

There are 3 different [NodeChange](../type-aliases/NodeChange.md) types. Each of these changes has a `type` property to distinguish them:

| Change                                                                              | `type` property     | Description                                                                                                                                                                                          |
| ----------------------------------------------------------------------------------- | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`CreateChange`](https://www.figma.com/plugin-docs/api/NodeChange#createchange)     | `'CREATE'`          | A node has been created in the page. If a node with nested children is being added to the page a `CreateChange` will only be made for the highest level parent that was added to the page.           |
| [`DeleteChange`](https://www.figma.com/plugin-docs/api/NodeChange#deletechange)     | `'DELETE'`          | A node has been removed from the page. If a node with nested children is being removed from the page a `DeleteChange` will only be made for the highest level parent that was removed from the page. |
| [`PropertyChange`](https://www.figma.com/plugin-docs/api/NodeChange#propertychange) | `'PROPERTY_CHANGE'` | A property of a node has changed.                                                                                                                                                                    |

---

### once()

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:8418

Same as [PageNode.on](#on), but the callback will only be called once, the first time the specified event happens.

#### Parameters

##### type

`"nodechange"`

##### callback

(`event`) => `void`

#### Returns

`void`

---

### remove()

> **remove**(): `void`

Defined in: figmaPluginTypes.ts:4933

Removes this node and **all of its children** from the document.

#### Returns

`void`

#### Remarks

If you want to only remove this node but not its children, you will have to first move them to another node before calling `remove()`.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`remove`](BaseNodeMixin.md#remove)

---

### setDevResourcePreviewAsync()

> **setDevResourcePreviewAsync**(`url`, `preview`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5127

Caution: This is a private API only available to [Figma partners](https://www.figma.com/partners/)

#### Parameters

##### url

`string`

##### preview

[`PlainTextElement`](../type-aliases/PlainTextElement.md)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setDevResourcePreviewAsync`](BaseNodeMixin.md#setdevresourcepreviewasync)

---

### setExplicitVariableModeForCollection()

#### Call Signature

> **setExplicitVariableModeForCollection**(`collectionId`, `modeId`): `void`

Defined in: figmaPluginTypes.ts:8270

Sets an explicit mode for the given collection on this node

##### Parameters

###### collectionId

`string`

###### modeId

`string`

##### Returns

`void`

##### Deprecated

Use `setExplicitVariableModeForCollection(VariableCollection, Variable)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

##### Inherited from

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`setExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#setexplicitvariablemodeforcollection)

#### Call Signature

> **setExplicitVariableModeForCollection**(`collection`, `modeId`): `void`

Defined in: figmaPluginTypes.ts:8277

Sets an explicit mode for the given collection on this node

##### Parameters

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a variable collection ID is deprecated.

###### modeId

`string`

A variable mode ID.

##### Returns

`void`

##### Inherited from

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`setExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#setexplicitvariablemodeforcollection)

---

### setPluginData()

> **setPluginData**(`key`, `value`): `void`

Defined in: figmaPluginTypes.ts:5049

Lets you store custom information on any node or style, **private** to your plugin. The total size of your entry (`pluginId`, `key`, `value`) cannot exceed 100 kB.

#### Parameters

##### key

`string`

The key under which to store the data. This is similar to writing to a plain object via `obj[key] = value`.

##### value

`string`

The data you want to store. If you want to store a value type other than a string, encode it as a JSON string first via `JSON.stringify` and `JSON.parse`. If you set the value to the empty string (""), the key/value pair is removed.

#### Returns

`void`

#### Remarks

The data is specific to your plugin ID. Plugins with other IDs won't be able to read this data. You can retrieve it later by calling `getPluginData` with the same key. To find all data stored on a node or style by your plugin use `getPluginDataKeys`.

Caution: ⚠ The data is stored privately for **stability**, not **security**. It prevents other plugins from accessing with your data. It does not, however, prevent users from seeing the data given sufficient effort. For example, they could export the document as a .fig file and try to decode it.

Caution: ⚠ Data will become inaccessible if your plugin ID changes.

Caution: ⚠ Total entry size cannot exceed 100 kB.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setPluginData`](BaseNodeMixin.md#setplugindata)

---

### setRelaunchData()

> **setRelaunchData**(`data`): `void`

Defined in: figmaPluginTypes.ts:4996

Sets state on the node to show a button and description when the node is selected. Clears the button and description when `relaunchData` is `{}`.

Note: In Figma and Dev Mode, this shows up in the properties panel. In FigJam, this shows up in the property menu. See [here](https://www.figma.com/plugin-docs/api/properties/nodes-setrelaunchdata#example-figma-design-ui) for examples.

#### Parameters

##### data

```ts
{
  [command: string]: string // description
}
```

e.g. `data = { myCommand: 'Short description' }`

#### Returns

`void`

#### Remarks

Each call to this method sets entirely new relaunch data, removing any relaunch data and associated buttons/descriptions from before. To maintain buttons from a previous call one can store the button information using [setPluginData](https://www.figma.com/plugin-docs/api/properties/nodes-setplugindata/) and later fetch it with [getPluginData](https://www.figma.com/plugin-docs/api/PageNode/#getplugindata) before passing it on to `setRelaunchData`.

To use this API, the plugin manifest must include a `relaunchButtons` section: see the [manifest guide](https://www.figma.com/plugin-docs/manifest#relaunchbuttons) for more information.

Note: Note that if the `command` passed to this method does not match a command in the manifest, nothing will be displayed. Similarly if the name of a command in the manifest changes or is removed, then all buttons with that command will disappear. This behavior can be used to remove buttons when a particular action is no longer supported by the plugin.

In Figma design, the relaunch data can also be placed on the PageNode or [DocumentNode](DocumentNode.md), to show a button and description when nothing is selected. Relaunch buttons added to the PageNode will be displayed on that page, combined with buttons from the [DocumentNode](DocumentNode.md) that show on every page. This is not supported in FigJam.

## Examples

```ts title="manifest.json"
// With the following in the manifest:
"relaunchButtons": [
  {"command": "edit", "name": "Edit shape"},
  {"command": "open", "name": "Open Shaper", "multipleSelection": true}
]
```

```ts title="code.ts"
// Add two buttons (ordered by the above array from the manifest):
// * an "Edit shape" button with a description of "Edit this trapezoid
//   with Shaper" that runs the plugin with `figma.command === 'edit'`.
// * an "Open Shaper" button with no description that runs the plugin with
//   `figma.command === 'open'`.
node.setRelaunchData({ edit: 'Edit this trapezoid with Shaper', open: '' })

// With the following in the manifest:
"relaunchButtons": [
  {"command": "relaunch", "name": "Run again", "multipleSelection": true}
]

// Pass an empty description to show only a button
node.setRelaunchData({ relaunch: '' })

// Remove the button and description
node.setRelaunchData({})
```

### Example Figma Design UI

![Relaunch UI in Figma Design](https://www.figma.com/plugin-docs/img/relaunch_ui_design.png)

### Example FigJam UI

![Relaunch UI in FigJam](https://www.figma.com/plugin-docs/img/relaunch_ui_figjam.png)

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setRelaunchData`](BaseNodeMixin.md#setrelaunchdata)

---

### setSharedPluginData()

> **setSharedPluginData**(`namespace`, `key`, `value`): `void`

Defined in: figmaPluginTypes.ts:5075

Lets you store custom information on any node or style, **public** to all plugins. The total size of your entry (`namespace`, `key`, `value`) cannot exceed 100 kB.

#### Parameters

##### namespace

`string`

A unique string to identify your plugin and avoid key collisions with other plugins. The namespace must be at least 3 alphanumeric characters.

##### key

`string`

The key under which to store the data. This is similar to writing to a plain object via `obj[key] = value`.

##### value

`string`

The data you want to store. If you want to store a value type other than a string, encode it as a JSON string first via `JSON.stringify` and `JSON.parse`. If you set the value to the empty string (""), the key/value pair is removed.

#### Returns

`void`

#### Remarks

This lets you store custom information on any node or style. You can retrieve it later by calling [PluginDataMixin.getSharedPluginData](PluginDataMixin.md#getsharedplugindata) with the same namespace and key. To find all data stored on a node or style in a particular namespace, use [PluginDataMixin.getSharedPluginDataKeys](PluginDataMixin.md#getsharedplugindatakeys).

Any data you write using this API will be readable by any plugin. The intent is to allow plugins to interoperate with each other. Use [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata) instead if you don't want other plugins to be able to read your data.

You must also provide a `namespace` argument to avoid key collisions with other plugins. This argument is mandatory to prevent multiple plugins from using generic key names like `data` and overwriting one another. We recommend passing a value that identifies your plugin. This namespace can be given to authors of other plugins so that they can read data from your plugin.

Caution: ⚠ Total entry size cannot exceed 100 kB.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setSharedPluginData`](BaseNodeMixin.md#setsharedplugindata)

---

### toString()

> **toString**(): `string`

Defined in: figmaPluginTypes.ts:4925

Returns a string representation of the node. For debugging purposes only, do not rely on the exact output of this string in production code.

#### Returns

`string`

#### Remarks

This currently returns a string of the form `[Node ID]` where `ID` is the id of the node. This is just for debugging convenience so the node displays something useful when converted to a string. We recommend not relying on this in production.

Example:

```ts
// e.g. [Node 0:5]
console.log(`Current selected node ${figma.currentPage.selection[0]}`);
```

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`toString`](BaseNodeMixin.md#tostring)
