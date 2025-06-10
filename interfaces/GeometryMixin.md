---

GeometryMixin

# Interface: GeometryMixin

Defined in: figmaPluginTypes.ts:6677

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`MinimalFillsMixin`](MinimalFillsMixin.md)

## Extended by

- [`DefaultShapeMixin`](DefaultShapeMixin.md)
- [`BaseFrameMixin`](BaseFrameMixin.md)

## Properties

### dashPattern

> **dashPattern**: readonly `number`[]

Defined in: figmaPluginTypes.ts:6623

A list of numbers specifying alternating dash and gap lengths, in pixels.

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`dashPattern`](MinimalStrokesMixin.md#dashpattern)

---

### fillGeometry

> `readonly` **fillGeometry**: [`VectorPaths`](../type-aliases/VectorPaths.md)

Defined in: figmaPluginTypes.ts:6699

An array of paths representing the object fills relative to the node.

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

### strokeAlign

> **strokeAlign**: `"CENTER"` \| `"INSIDE"` \| `"OUTSIDE"`

Defined in: figmaPluginTypes.ts:6619

The alignment of the stroke with respect to the boundaries of the shape.

#### Remarks

Center-aligned stroke means the center of the stroke falls exactly on the geometry. Inside-aligned stroke shifts the stroke so it lies completely inside the shape, and outside-aligned stroke is vice versa.

Note: Inside and outside stroke are actually implemented by doubling the stroke weight and masking the stroke by the fill. This means inside-aligned stroke will never draw strokes outside the fill and outside-aligned stroke will never draw strokes inside the fill.

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`strokeAlign`](MinimalStrokesMixin.md#strokealign)

---

### strokeCap

> **strokeCap**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`StrokeCap`](../type-aliases/StrokeCap.md)

Defined in: figmaPluginTypes.ts:6687

The decoration applied to vertices which have only one connected segment.

#### Remarks

On a vector network, the value is set on the whole vector network. Use the vector network API to set it on individual vertices.

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if different vertices have different values.properties.

---

### strokeGeometry

> `readonly` **strokeGeometry**: [`VectorPaths`](../type-aliases/VectorPaths.md)

Defined in: figmaPluginTypes.ts:6628

An array of paths representing the object strokes relative to the node.
StrokeGeometry is always from the center regardless of the nodes `strokeAlign`.

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`strokeGeometry`](MinimalStrokesMixin.md#strokegeometry)

---

### strokeJoin

> **strokeJoin**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`StrokeJoin`](../type-aliases/StrokeJoin.md)

Defined in: figmaPluginTypes.ts:6609

The decoration applied to vertices which have two or more connected segments.

#### Remarks

On a vector network, the value is set on the whole vector network. Use the vector network API to set it on individual vertices.

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if different vertices have different values.properties.

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`strokeJoin`](MinimalStrokesMixin.md#strokejoin)

---

### strokeMiterLimit

> **strokeMiterLimit**: `number`

Defined in: figmaPluginTypes.ts:6691

The miter limit on the stroke. This is the same as the [SVG miter limit](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/stroke-miterlimit).

---

### strokes

> **strokes**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:6576

The paints used to fill the area of the shape's strokes. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`strokes`](MinimalStrokesMixin.md#strokes)

---

### strokeStyleId

> **strokeStyleId**: `string`

Defined in: figmaPluginTypes.ts:6582

The id of the [PaintStyle](PaintStyle.md) object that the [MinimalStrokesMixin.strokes](MinimalStrokesMixin.md#strokes) property of this node is linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setStrokeStyleIdAsync` to update the style.

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`strokeStyleId`](MinimalStrokesMixin.md#strokestyleid)

---

### strokeWeight

> **strokeWeight**: `number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:6599

The thickness of the stroke, in pixels. This value must be non-negative and can be fractional.

Caution: For rectangle nodes or frame-like nodes using different individual stroke weights, this property will return [PluginAPI.mixed](PluginAPI.md#mixed).

Note: For rectangle nodes or frame-like nodes, individual stroke weights can be set for each side using the following properties:

- [IndividualStrokesMixin.strokeTopWeight](IndividualStrokesMixin.md#stroketopweight)
- [IndividualStrokesMixin.strokeBottomWeight](IndividualStrokesMixin.md#strokebottomweight)
- [IndividualStrokesMixin.strokeLeftWeight](IndividualStrokesMixin.md#strokeleftweight)
- [IndividualStrokesMixin.strokeRightWeight](IndividualStrokesMixin.md#strokerightweight)

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`strokeWeight`](MinimalStrokesMixin.md#strokeweight)

## Methods

### outlineStroke()

> **outlineStroke**(): `null` \| [`VectorNode`](VectorNode.md)

Defined in: figmaPluginTypes.ts:6695

This method performs an action similar to using the "Outline Stroke" function in the editor from the right-click menu. However, this method creates and returns a new node while leaving the original intact. Returns `null` if the node has no strokes.

#### Returns

`null` \| [`VectorNode`](VectorNode.md)

---

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

---

### setStrokeStyleIdAsync()

> **setStrokeStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:6586

Set the [PaintStyle](PaintStyle.md) that the [MinimalStrokesMixin.strokes](MinimalStrokesMixin.md#strokes) property of this node is linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`MinimalStrokesMixin`](MinimalStrokesMixin.md).[`setStrokeStyleIdAsync`](MinimalStrokesMixin.md#setstrokestyleidasync)
