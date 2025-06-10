---

MinimalFillsMixin

# Interface: MinimalFillsMixin

Defined in: figmaPluginTypes.ts:6646

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`GeometryMixin`](GeometryMixin.md)
- [`TextSublayerNode`](TextSublayerNode.md)
- [`StickyNode`](StickyNode.md)
- [`TableNode`](TableNode.md)
- [`TableCellNode`](TableCellNode.md)
- [`ShapeWithTextNode`](ShapeWithTextNode.md)
- [`SectionNode`](SectionNode.md)

## Properties

### fills

> **fills**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:6658

The paints used to fill the area of the shape. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Remarks

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if the node has multiple sets of fills. Text nodes can have multiple sets of fills if some characters are colored differently than others.

Use [UtilAPI.solidPaint](UtilAPI.md#solidpaint) to create solid paint fills with CSS color strings.

Page nodes have a [`backgrounds`](https://www.figma.com/plugin-docs/api/PageNode/#backgrounds) property instead of a `fills` property.

---

### fillStyleId

> **fillStyleId**: `string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:6668

The id of the [PaintStyle](PaintStyle.md) object that the [MinimalFillsMixin.fills](#fills) property of this node is linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setFillStyleIdAsync` to update the style.

#### Remarks

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if the node has multiple fills.properties. Text nodes can have multiple fills if some characters are colored differently than others.

## Methods

### setFillStyleIdAsync()

> **setFillStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:6672

Sets the [PaintStyle](PaintStyle.md) that the [MinimalFillsMixin.fills](#fills) property of this node is linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>
