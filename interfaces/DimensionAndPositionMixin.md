---

DimensionAndPositionMixin

# Interface: DimensionAndPositionMixin

Defined in: figmaPluginTypes.ts:5618

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`LayoutMixin`](LayoutMixin.md)
- [`OpaqueNodeMixin`](OpaqueNodeMixin.md)

## Properties

### absoluteBoundingBox

> `readonly` **absoluteBoundingBox**: `null` \| [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:5712

The bounds of the node that does not include rendered properties like drop shadows or strokes. The `x` and `y` inside this property represent the absolute position of the node on the page.

---

### absoluteTransform

> `readonly` **absoluteTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5708

The position of a node relative to its **containing page** as a [Transform](../type-aliases/Transform.md) matrix.

---

### height

> `readonly` **height**: `number`

Defined in: figmaPluginTypes.ts:5642

The height of the node. Use a resizing method to change this value.

---

### maxHeight

> **maxHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5658

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxHeight`.

---

### maxWidth

> **maxWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5650

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxWidth`.

---

### minHeight

> **minHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5654

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to null to remove `minHeight`.

---

### minWidth

> **minWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5646

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `minWidth`.

---

### relativeTransform

> **relativeTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5704

The position of a node relative to its **containing parent** as a [Transform](../type-aliases/Transform.md) matrix. Not used for scaling, see `width` and `height` instead. Read the details page to understand the nuances of this property.

#### Remarks

### Scale

The `relativeTransform` is **not** used for scaling a node. The transform always has unit axes. That is, `sqrt(m00^2 + m10^2) == sqrt(m01^2 + m11^2) == 1`. In order to set the size of a node, use [LayoutMixin.resize](LayoutMixin.md#resize) or [LayoutMixin.resizeWithoutConstraints](LayoutMixin.md#resizewithoutconstraints).

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

One implication is that to calculate the absolute position of a node, you have to either use the [DimensionAndPositionMixin.absoluteTransform](#absolutetransform) property or multiply relative transform matrices while traversing up the node hierarchy while ignoring groups and boolean operations.

Note: Why this complication? We do it this way because groups and boolean operations automatically resize to fit their children. While you _can_ set the relative transform of a group to move it, it's a property derived from the position and size of its children.
If the relative transform was always relative to it’s immediate parent, you could get into confusing situations where moving a layer inside a group by setting the relative transform changes the position of the parent, which then requires changing the relative transform of the child in order to preserve its on-screen position!

### Skew

While it is possible to skew a layer by setting `m00`, `m01`, `m10`, `m11` to the right values, be aware that the skew will not be surfaced in the properties panel and may be confusing to the user dealing with a skewed node.

### Auto-layout frames

The translation components `m02` and `m12` of the transform matrix is automatically computed in children of auto-layout frames. Setting `relativeTransform` on those layers will ignore the translation components, but do keep the rotation components.

---

### width

> `readonly` **width**: `number`

Defined in: figmaPluginTypes.ts:5638

The width of the node. Use a resizing method to change this value.

---

### x

> **x**: `number`

Defined in: figmaPluginTypes.ts:5626

The position of the node. Identical to `relativeTransform[0][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

---

### y

> **y**: `number`

Defined in: figmaPluginTypes.ts:5634

The position of the node. Identical to `relativeTransform[1][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.
