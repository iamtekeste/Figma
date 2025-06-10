---

MinimalBlendMixin

# Interface: MinimalBlendMixin

Defined in: figmaPluginTypes.ts:7174

## See

https://www.figma.com/plugin-docs/api/N/A

## Extended by

- [`BlendMixin`](BlendMixin.md)
- [`StickyNode`](StickyNode.md)
- [`TableNode`](TableNode.md)
- [`ShapeWithTextNode`](ShapeWithTextNode.md)
- [`CodeBlockNode`](CodeBlockNode.md)
- [`ConnectorNode`](ConnectorNode.md)

## Properties

### blendMode

> **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:7182

Blend mode of this node, as shown in the Layer panel. In addition to the blend modes that paints & effects support, the layer blend mode can also have the value PASS_THROUGH.

---

### opacity

> **opacity**: `number`

Defined in: figmaPluginTypes.ts:7178

Opacity of the node, as shown in the Layer panel. Must be between 0 and 1.
