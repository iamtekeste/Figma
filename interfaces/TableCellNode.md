---

TableCellNode

# Interface: TableCellNode

Defined in: figmaPluginTypes.ts:9071

## See

https://www.figma.com/plugin-docs/api/TableCellNode

## Extends

- [`MinimalFillsMixin`](MinimalFillsMixin.md)

## Properties

### columnIndex

> `readonly` **columnIndex**: `number`

Defined in: figmaPluginTypes.ts:9087

The column index of this cell relative to its parent table.

---

### fills

> **fills**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:6658

The paints used to fill the area of the shape. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Remarks

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if the node has multiple sets of fills. Text nodes can have multiple sets of fills if some characters are colored differently than others.

Use [UtilAPI.solidPaint](UtilAPI.md#solidpaint) to create solid paint fills with CSS color strings.

Page nodes have a [`backgrounds`](https://www.figma.com/plugin-docs/api/PageNode/#backgrounds) property instead of a `fills` property.

#### Inherited from

[`MinimalFillsMixin`](MinimalFillsMixin.md).[`fills`](MinimalFillsMixin.md#fills)

---

### fillStyleId

> **fillStyleId**: `string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:6668

The id of the [PaintStyle](PaintStyle.md) object that the [MinimalFillsMixin.fills](MinimalFillsMixin.md#fills) property of this node is linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setFillStyleIdAsync` to update the style.

#### Remarks

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if the node has multiple fills.properties. Text nodes can have multiple fills if some characters are colored differently than others.

#### Inherited from

[`MinimalFillsMixin`](MinimalFillsMixin.md).[`fillStyleId`](MinimalFillsMixin.md#fillstyleid)

---

### height

> `readonly` **height**: `number`

Defined in: figmaPluginTypes.ts:9090

---

### parent

> `readonly` **parent**: [`TableNode`](TableNode.md)

Defined in: figmaPluginTypes.ts:9089

---

### rowIndex

> `readonly` **rowIndex**: `number`

Defined in: figmaPluginTypes.ts:9083

The row index of this cell relative to its parent table.

---

### text

> `readonly` **text**: [`TextSublayerNode`](TextSublayerNode.md)

Defined in: figmaPluginTypes.ts:9079

Text sublayer of the TableCellNode

---

### toString

> `readonly` **toString**: `string`

Defined in: figmaPluginTypes.ts:9088

Returns a string representation of an object.

---

### type

> `readonly` **type**: `"TABLE_CELL"`

Defined in: figmaPluginTypes.ts:9075

The type of this node, represented by the string literal "TABLE_CELL"

---

### width

> `readonly` **width**: `number`

Defined in: figmaPluginTypes.ts:9091

## Methods

### setFillStyleIdAsync()

> **setFillStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:6672

Sets the [PaintStyle](PaintStyle.md) that the [MinimalFillsMixin.fills](MinimalFillsMixin.md#fills) property of this node is linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`MinimalFillsMixin`](MinimalFillsMixin.md).[`setFillStyleIdAsync`](MinimalFillsMixin.md#setfillstyleidasync)
