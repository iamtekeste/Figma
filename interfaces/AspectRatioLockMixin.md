---

AspectRatioLockMixin

# Interface: AspectRatioLockMixin

Defined in: figmaPluginTypes.ts:5866

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)
- [`RectangleNode`](RectangleNode.md)
- [`EllipseNode`](EllipseNode.md)
- [`PolygonNode`](PolygonNode.md)
- [`StarNode`](StarNode.md)
- [`VectorNode`](VectorNode.md)
- [`TextNode`](TextNode.md)
- [`TextPathNode`](TextPathNode.md)
- [`BooleanOperationNode`](BooleanOperationNode.md)
- [`StampNode`](StampNode.md)
- [`HighlightNode`](HighlightNode.md)
- [`WashiTapeNode`](WashiTapeNode.md)
- [`SectionNode`](SectionNode.md)

## Properties

### targetAspectRatio

> `readonly` **targetAspectRatio**: `null` \| [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:5905

When toggled, causes the layer to keep its proportions when the user resizes it via auto layout, constraints, the properties panel, or on-canvas.
If not set, the node does NOT resize toward a specific targetAspectRatio.

#### Remarks

Use `lockAspectRatio` and `unlockAspectRatio` to set targetAspectRatio.

```ts
const parentFrame = figma.createFrame();
const image = await figma.createNodeFromJSXAsync(
  <figma.widget.Image
    src="https://picsum.photos/200/300"
    width={200}
    height={300}
  />
);
parentFrame.appendChild(image);

image.lockAspectRatio(); // set to 2:3 ratio, implicit from the size

// Add autolayout to parent, which defaults to Hug x Hug
parentFrame.layoutMode = "HORIZONTAL";

// Set child to fill-width
image.layoutGrow = 1;

// Resize parent to be much larger
parentFrame.resize(500, 1000);

// Since the child is fill-width, it will expand to the available space
image.width == 500;
image.height == 750;
// Image maintains the 2:3 ratio even as it grew with auto layout!
```

Caution: ⚠️ `targetAspectRatio` cannot be used with auto-resizing text (TextNodes where textAutoResize !== NONE).

## Methods

### lockAspectRatio()

> **lockAspectRatio**(): `void`

Defined in: figmaPluginTypes.ts:5909

Locks the node's `targetAspectRatio` to the current ratio of its width and height.

#### Returns

`void`

---

### unlockAspectRatio()

> **unlockAspectRatio**(): `void`

Defined in: figmaPluginTypes.ts:5913

Unlocks the node's `targetAspectRatio`.

#### Returns

`void`
