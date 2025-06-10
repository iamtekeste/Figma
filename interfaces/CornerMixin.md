---

CornerMixin

# Interface: CornerMixin

Defined in: figmaPluginTypes.ts:6704

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`RectangleNode`](RectangleNode.md)
- [`EllipseNode`](EllipseNode.md)
- [`PolygonNode`](PolygonNode.md)
- [`StarNode`](StarNode.md)
- [`VectorNode`](VectorNode.md)
- [`BooleanOperationNode`](BooleanOperationNode.md)
- [`HighlightNode`](HighlightNode.md)

## Properties

### cornerRadius

> **cornerRadius**: `number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:6714

The number of pixels to round the corners of the object by.

#### Remarks

This value must be non-negative and can be fractional. If an edge length is less than twice the corner radius, the corner radius for each vertex of the edge will be clamped to half the edge length.

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if different vertices have different values.properties. Vector nodes can have individual corner radii on each vertex. Rectangle nodes can also have different corner radii on each of the four corners.

---

### cornerSmoothing

> **cornerSmoothing**: `number`

Defined in: figmaPluginTypes.ts:6722

A value that lets you control how "smooth" the corners are. Ranges from 0 to 1.

#### Remarks

A value of 0 is the default and means that the corner is perfectly circular. A value of 0.6 means the corner matches the iOS 7 "squircle" icon shape. Other values produce various other curves. See [this post](https://www.figma.com/blog/desperately-seeking-squircles/) for the gory details!
