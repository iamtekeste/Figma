---

ConstraintMixin

# Interface: ConstraintMixin

Defined in: figmaPluginTypes.ts:5605

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`RectangleNode`](RectangleNode.md)
- [`LineNode`](LineNode.md)
- [`EllipseNode`](EllipseNode.md)
- [`PolygonNode`](PolygonNode.md)
- [`StarNode`](StarNode.md)
- [`VectorNode`](VectorNode.md)
- [`TextNode`](TextNode.md)
- [`TextPathNode`](TextPathNode.md)
- [`StampNode`](StampNode.md)
- [`HighlightNode`](HighlightNode.md)

## Properties

### constraints

> **constraints**: [`Constraints`](Constraints.md)

Defined in: figmaPluginTypes.ts:5613

Constraints of this node relative to its containing [FrameNode](FrameNode.md), if any.

#### Remarks

Not all node types have a constraint property. In particular, Group and BooleanOperation nodes do not have a constraint property themselves. Instead, resizing a frame applies the constraints on the children of those nodes.
