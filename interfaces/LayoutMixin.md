---

LayoutMixin

# Interface: LayoutMixin

Defined in: figmaPluginTypes.ts:5717

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`AutoLayoutChildrenMixin`](AutoLayoutChildrenMixin.md)

## Extended by

- [`DefaultShapeMixin`](DefaultShapeMixin.md)
- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)
- [`SliceNode`](SliceNode.md)

## Properties

### absoluteBoundingBox

> `readonly` **absoluteBoundingBox**: `null` \| [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:5712

The bounds of the node that does not include rendered properties like drop shadows or strokes. The `x` and `y` inside this property represent the absolute position of the node on the page.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`absoluteBoundingBox`](DimensionAndPositionMixin.md#absoluteboundingbox)

---

### absoluteRenderBounds

> `readonly` **absoluteRenderBounds**: `null` \| [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:5721

The actual bounds of a node accounting for drop shadows, thick strokes, and anything else that may fall outside the node's regular bounding box defined in `x`, `y`, `width`, and `height`. The `x` and `y` inside this property represent the absolute position of the node on the page. This value will be `null` if the node is invisible.

---

### absoluteTransform

> `readonly` **absoluteTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5708

The position of a node relative to its **containing page** as a [Transform](../type-aliases/Transform.md) matrix.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`absoluteTransform`](DimensionAndPositionMixin.md#absolutetransform)

---

### ~~constrainProportions~~

> **constrainProportions**: `boolean`

Defined in: figmaPluginTypes.ts:5727

When toggled, causes the layer to keep its proportions when the user resizes it via the properties panel.

#### Deprecated

Use `targetAspectRatio`, `lockAspectRatio`, and `unlockAspectRatio` instead.

---

### height

> `readonly` **height**: `number`

Defined in: figmaPluginTypes.ts:5642

The height of the node. Use a resizing method to change this value.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`height`](DimensionAndPositionMixin.md#height)

---

### layoutAlign

> **layoutAlign**: `"MIN"` \| `"CENTER"` \| `"MAX"` \| `"STRETCH"` \| `"INHERIT"`

Defined in: figmaPluginTypes.ts:6507

Applicable only on direct children of auto-layout frames. Determines if the layer should stretch along the parent’s counter axis. Defaults to `“INHERIT”`.

#### Remarks

Changing this property will cause the `x`, `y`, `size`, and `relativeTransform` properties on this node to change, if applicable (inside an auto-layout frame).

- Setting `"STRETCH"` will make the node "stretch" to fill the width of the parent vertical auto-layout frame, or the height of the parent horizontal auto-layout frame excluding the frame's padding.
- If the current node is an auto layout frame (e.g. an auto layout frame inside a parent auto layout frame) if you set layoutAlign to `“STRETCH”` you should set the corresponding axis – either [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode) or [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode) – to be`“FIXED”`. This is because an auto-layout frame cannot simultaneously stretch to fill its parent and shrink to hug its children.
- Setting `"INHERIT"` does not "stretch" the node.

Caution: ⚠️ Previously, layoutAlign also determined counter axis alignment of auto-layout frame children. Counter axis alignment is now set on the auto-layout frame itself through [AutoLayoutMixin.counterAxisAlignItems](AutoLayoutMixin.md#counteraxisalignitems). Note that this means all layers in an auto-layout frame must now have the same counter axis alignment. This means `"MIN"`, `"CENTER"`, and `"MAX"` are now deprecated values of `layoutAlign`.

#### Inherited from

[`AutoLayoutChildrenMixin`](AutoLayoutChildrenMixin.md).[`layoutAlign`](AutoLayoutChildrenMixin.md#layoutalign)

---

### layoutGrow

> **layoutGrow**: `number`

Defined in: figmaPluginTypes.ts:6517

This property is applicable only for direct children of auto-layout frames. Determines whether a layer should stretch along the parent’s primary axis. 0 corresponds to a fixed size and 1 corresponds to stretch.

#### Remarks

0 and 1 are currently the only supported values.

Note: If the current node is an auto-layout frame (e.g. an auto-layout frame inside a parent auto-layout frame) if you set `layoutGrow` to 1 you should set the corresponding axis – either [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode) or [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode) – to be `“FIXED”`. This is because an auto-layout frame cannot simultaneously stretch to fill its parent and shrink to hug its children.

#### Inherited from

[`AutoLayoutChildrenMixin`](AutoLayoutChildrenMixin.md).[`layoutGrow`](AutoLayoutChildrenMixin.md#layoutgrow)

---

### layoutPositioning

> **layoutPositioning**: `"AUTO"` \| `"ABSOLUTE"`

Defined in: figmaPluginTypes.ts:6551

This property is applicable only for direct children of auto-layout frames. Determines whether a layer's size and position should be dermined by auto-layout settings or manually adjustable.

#### Remarks

Changing this property may cause the parent layer's size to change, since it will recalculate as if this child did not exist. It will also change this node's `x`, `y`, and `relativeTransform` properties.

- The default value of `"AUTO"` will layout this child according to auto-layout rules.
- Setting `"ABSOLUTE"` will take this child out of auto-layout flow, while still nesting inside the auto-layout frame. This allows explicitly setting `x`, `y`, `width`, and `height`. `"ABSOLUTE"` positioned nodes respect constraint settings.

```ts title="Auto-layout frame absolutely positioned red circle at the top-right corner"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());

// Create a small red circle
const ellipse = figma.createEllipse();
ellipse.resize(20, 20);
ellipse.fills = [{ type: "SOLID", color: { r: 1, g: 0, b: 0 } }];
parentFrame.appendChild(ellipse);
parentFrame.clipsContent = false;
parentFrame.layoutMode = "HORIZONTAL";

// Enable absolute positioning so we can move the circle
ellipse.layoutPositioning = "ABSOLUTE";

// Center the circle on the top-right corner of the frame
ellipse.x = 90;
ellipse.y = -10;

// Make the circle stick to the top-right corner of the frame
ellipse.constraints = { horizontal: "MAX", vertical: "MIN" };
```

#### Inherited from

[`AutoLayoutChildrenMixin`](AutoLayoutChildrenMixin.md).[`layoutPositioning`](AutoLayoutChildrenMixin.md#layoutpositioning)

---

### layoutSizingHorizontal

> **layoutSizingHorizontal**: `"FILL"` \| `"FIXED"` \| `"HUG"`

Defined in: figmaPluginTypes.ts:5813

Applicable only on auto-layout frames, their children, and text nodes. This is a shorthand for setting [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow), [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign), [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode), and [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode). This field maps directly to the "Horizontal sizing" dropdown in the Figma UI.

#### Remarks

`"HUG"` is only valid on auto-layout frames and text nodes. `"FILL"` is only valid on auto-layout children. Setting these values when they don't apply will throw an error.

```ts title="Setting layoutSizingHorizontal on an auto-layout frame"
const parentFrame = figma.createFrame();
const child2 = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(child2);
parentFrame.layoutMode = "VERTICAL";
// Make the second child twice as wide as the first
child2.resize(200, 100);

// Parent frame (child 2 is clipped)
// +-------------+
// |+-----------+|
// ||           ||
// ||  Child 1  ||
// ||           ||
// |+-----------+|
// |+------------|
// ||            |
// ||  Child 2   |
// ||            |
// |+------------|
// +-------------+

parentFrame.layoutSizingHorizontal = "FIXED";

// Parent frame (child 2 is not clipped)
// +------------------------+
// |+-----------+           |
// ||           |           |
// ||  Child 1  |           |
// ||           |           |
// |+-----------+           |
// |+----------------------+|
// ||                      ||
// ||       Child 2        ||
// ||                      ||
// |+----------------------+|
// +------------------------+
parentFrame.layoutSizingHorizontal = "HUG";
```

```ts title="Setting layoutSizingHorizontal on an auto-layout child"
const parentFrame = figma.createFrame();
const child2 = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(child2);
parentFrame.layoutMode = "HORIZONTAL";
parentFrame.resize(300, 100);

// Parent frame
// +-------------------------------------+
// |+-----------++-----------+           |
// ||           ||           |           |
// ||  Child 1  ||  Child 2  |           |
// ||           ||           |           |
// |+-----------++-----------+           |
// +-------------------------------------+
child2.layoutSizingHorizontal = "FIXED";

// Parent frame
// +-------------------------------------+
// |+-----------++----------------------+|
// ||           ||                      ||
// ||  Child 1  ||       Child 2        ||
// ||           ||                      ||
// |+-----------++----------------------+|
// +-------------------------------------+
child2.layoutSizingHorizontal = "FILL";
```

---

### layoutSizingVertical

> **layoutSizingVertical**: `"FILL"` \| `"FIXED"` \| `"HUG"`

Defined in: figmaPluginTypes.ts:5821

Applicable only on auto-layout frames, their children, and text nodes. This is a shorthand for setting [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow), [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign), [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode), and [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode). This field maps directly to the "Vertical sizing" dropdown in the Figma UI.

#### Remarks

`"HUG"` is only valid on auto-layout frames and text nodes. `"FILL"` is only valid on auto-layout children. Setting these values when they don't apply will throw an error.

---

### maxHeight

> **maxHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5658

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxHeight`.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`maxHeight`](DimensionAndPositionMixin.md#maxheight)

---

### maxWidth

> **maxWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5650

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxWidth`.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`maxWidth`](DimensionAndPositionMixin.md#maxwidth)

---

### minHeight

> **minHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5654

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to null to remove `minHeight`.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`minHeight`](DimensionAndPositionMixin.md#minheight)

---

### minWidth

> **minWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5646

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `minWidth`.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`minWidth`](DimensionAndPositionMixin.md#minwidth)

---

### relativeTransform

> **relativeTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5704

The position of a node relative to its **containing parent** as a [Transform](../type-aliases/Transform.md) matrix. Not used for scaling, see `width` and `height` instead. Read the details page to understand the nuances of this property.

#### Remarks

### Scale

The `relativeTransform` is **not** used for scaling a node. The transform always has unit axes. That is, `sqrt(m00^2 + m10^2) == sqrt(m01^2 + m11^2) == 1`. In order to set the size of a node, use [LayoutMixin.resize](#resize) or [LayoutMixin.resizeWithoutConstraints](#resizewithoutconstraints).

Note: If you have a background in computer graphics, you may find it odd that we use the transform matrix in such a manner. This is because in 2D UI design, it's rare that you would want to scale the children when resizing a frame. And even if you did, it would be through more nuanced constraint settings that aren't captured by a transformation matrix.

Also, if nodes had both a `width` and a separate `m00` scale property, it would be confusing to the users which one they're changing, especially during interactions like dragging.

### Container parent

The relative transform of a node is shown relative to its container parent, which includes canvas nodes, frame nodes, component nodes, and instance nodes. Just like in the properties panel, it is **not** relative to its direct parent if the parent is a group or a boolean operation.

Example 1: In the following hierarchy, the relative transform of `rectangle` is relative to `page` (which is just its position on the canvas).

```text
page
  group
    rectangle
```

Example 2: In the following hierarchy, the relative transform of `rectangle` is relative to `frame`.

```text
page
  frame
    boolean operation
      rectangle
```

One implication is that to calculate the absolute position of a node, you have to either use the [DimensionAndPositionMixin.absoluteTransform](DimensionAndPositionMixin.md#absolutetransform) property or multiply relative transform matrices while traversing up the node hierarchy while ignoring groups and boolean operations.

Note: Why this complication? We do it this way because groups and boolean operations automatically resize to fit their children. While you _can_ set the relative transform of a group to move it, it's a property derived from the position and size of its children.
If the relative transform was always relative to it’s immediate parent, you could get into confusing situations where moving a layer inside a group by setting the relative transform changes the position of the parent, which then requires changing the relative transform of the child in order to preserve its on-screen position!

### Skew

While it is possible to skew a layer by setting `m00`, `m01`, `m10`, `m11` to the right values, be aware that the skew will not be surfaced in the properties panel and may be confusing to the user dealing with a skewed node.

### Auto-layout frames

The translation components `m02` and `m12` of the transform matrix is automatically computed in children of auto-layout frames. Setting `relativeTransform` on those layers will ignore the translation components, but do keep the rotation components.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`relativeTransform`](DimensionAndPositionMixin.md#relativetransform)

---

### rotation

> **rotation**: `number`

Defined in: figmaPluginTypes.ts:5735

The rotation of the node in degrees. Returns values from -180 to 180. Identical to `Math.atan2(-m10, m00)` in the [DimensionAndPositionMixin.relativeTransform](DimensionAndPositionMixin.md#relativetransform) matrix. When setting `rotation`, it will also set `m00`, `m01`, `m10`, `m11`.

#### Remarks

The rotation is with respect to the top-left of the object. Therefore, it is independent from the position of the object. If you want to rotate with respect to the center (or any arbitrary point), you can do so via matrix transformations and [DimensionAndPositionMixin.relativeTransform](DimensionAndPositionMixin.md#relativetransform).

---

### width

> `readonly` **width**: `number`

Defined in: figmaPluginTypes.ts:5638

The width of the node. Use a resizing method to change this value.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`width`](DimensionAndPositionMixin.md#width)

---

### x

> **x**: `number`

Defined in: figmaPluginTypes.ts:5626

The position of the node. Identical to `relativeTransform[0][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`x`](DimensionAndPositionMixin.md#x)

---

### y

> **y**: `number`

Defined in: figmaPluginTypes.ts:5634

The position of the node. Identical to `relativeTransform[1][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

#### Inherited from

[`DimensionAndPositionMixin`](DimensionAndPositionMixin.md).[`y`](DimensionAndPositionMixin.md#y)

## Methods

### rescale()

> **rescale**(`scale`): `void`

Defined in: figmaPluginTypes.ts:5861

Rescales the node. This API function is the equivalent of using the Scale Tool from the toolbar.

#### Parameters

##### scale

`number`

The scale by which to resize the node from the top-left corner.

#### Returns

`void`

#### Remarks

The scale factor must be >= 0.01

---

### resize()

> **resize**(`width`, `height`): `void`

Defined in: figmaPluginTypes.ts:5836

Resizes the node. If the node contains children with constraints, it applies those constraints during resizing. If the parent has auto-layout, causes the parent to be resized.

#### Parameters

##### width

`number`

New width of the node. Must be >= 0.01

##### height

`number`

New height of the node. Must be >= 0.01, except for [LineNode](LineNode.md) which must always be given a height of exactly 0.

#### Returns

`void`

#### Remarks

Since this function applies constraints recursively (when there are multiple levels of nested frames with constraints), calls to this function could be expensive. Use [LayoutMixin.resizeWithoutConstraints](#resizewithoutconstraints) if you don't need to apply constraints.

Caution: ⚠️ If this node is a text node with a missing font or contains a text node with a missing font, the text node will be resized but the text will not re-layout until the next time the text node is opened on a machine that _has_ the font. This can cause the text node to re-layout immediately and be surprising to your user. Consider checking if the document [PluginAPI.hasMissingFont](PluginAPI.md#hasmissingfont) before using this function.

Ignores `targetAspectRatio`. If `targetAspectRatio` has been set, it will be updated to correspond to the post-resize value.

---

### resizeWithoutConstraints()

> **resizeWithoutConstraints**(`width`, `height`): `void`

Defined in: figmaPluginTypes.ts:5851

Resizes the node. Children of the node are never resized, even if those children have constraints. If the parent has auto-layout, causes the parent to be resized (this constraint cannot be ignored).

#### Parameters

##### width

`number`

New width of the node. Must be >= 0.01

##### height

`number`

New height of the node. Must be >= 0.01, except for [LineNode](LineNode.md) which must always be given a height of exactly 0.

#### Returns

`void`

#### Remarks

This function will not cause its children to resize. Use [LayoutMixin.resize](#resize) if you need to apply constraints.

Caution: ⚠️ If this node is a text node with a missing font, the text node will be resized but the text will not re-layout until the next time the text node is opened on a machine that _has_ the font. This can cause the text node to re-layout immediately and be surprising to your user. Consider checking the text node property [`hasMissingFont`](https://www.figma.com/plugin-docs/api/TextNode#hasmissingfont) before using this function.

Ignores `targetAspectRatio`. If `targetAspectRatio` has been set, it will be updated to correspond to the post-resize value.
