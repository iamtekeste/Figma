---

MinimalStrokesMixin

# Interface: MinimalStrokesMixin

Defined in: figmaPluginTypes.ts:6572

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`GeometryMixin`](GeometryMixin.md)
- [`ShapeWithTextNode`](ShapeWithTextNode.md)
- [`ConnectorNode`](ConnectorNode.md)

## Properties

### dashPattern

> **dashPattern**: readonly `number`[]

Defined in: figmaPluginTypes.ts:6623

A list of numbers specifying alternating dash and gap lengths, in pixels.

---

### strokeAlign

> **strokeAlign**: `"CENTER"` \| `"INSIDE"` \| `"OUTSIDE"`

Defined in: figmaPluginTypes.ts:6619

The alignment of the stroke with respect to the boundaries of the shape.

#### Remarks

Center-aligned stroke means the center of the stroke falls exactly on the geometry. Inside-aligned stroke shifts the stroke so it lies completely inside the shape, and outside-aligned stroke is vice versa.

Note: Inside and outside stroke are actually implemented by doubling the stroke weight and masking the stroke by the fill. This means inside-aligned stroke will never draw strokes outside the fill and outside-aligned stroke will never draw strokes inside the fill.

---

### strokeGeometry

> `readonly` **strokeGeometry**: [`VectorPaths`](../type-aliases/VectorPaths.md)

Defined in: figmaPluginTypes.ts:6628

An array of paths representing the object strokes relative to the node.
StrokeGeometry is always from the center regardless of the nodes `strokeAlign`.

---

### strokeJoin

> **strokeJoin**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`StrokeJoin`](../type-aliases/StrokeJoin.md)

Defined in: figmaPluginTypes.ts:6609

The decoration applied to vertices which have two or more connected segments.

#### Remarks

On a vector network, the value is set on the whole vector network. Use the vector network API to set it on individual vertices.

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if different vertices have different values.properties.

---

### strokes

> **strokes**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:6576

The paints used to fill the area of the shape's strokes. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

---

### strokeStyleId

> **strokeStyleId**: `string`

Defined in: figmaPluginTypes.ts:6582

The id of the [PaintStyle](PaintStyle.md) object that the [MinimalStrokesMixin.strokes](#strokes) property of this node is linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setStrokeStyleIdAsync` to update the style.

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

## Methods

### setStrokeStyleIdAsync()

> **setStrokeStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:6586

Set the [PaintStyle](PaintStyle.md) that the [MinimalStrokesMixin.strokes](#strokes) property of this node is linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>
