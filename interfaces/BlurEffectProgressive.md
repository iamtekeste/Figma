---

BlurEffectProgressive

# Interface: BlurEffectProgressive

Defined in: figmaPluginTypes.ts:3739

## See

https://www.figma.com/plugin-docs/api/Effect

## Extends

- [`BlurEffectBase`](BlurEffectBase.md)

## Properties

### blurType

> `readonly` **blurType**: `"PROGRESSIVE"`

Defined in: figmaPluginTypes.ts:3743

The string literal representing the blur type. Always check the `blurType` before reading other properties.

---

### boundVariables?

> `readonly` `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:3723

The variable bound to the radius field on this blur effect

#### radius?

> `optional` **radius**: [`VariableAlias`](VariableAlias.md)

#### Inherited from

[`BlurEffectBase`](BlurEffectBase.md).[`boundVariables`](BlurEffectBase.md#boundvariables)

---

### endOffset

> `readonly` **endOffset**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:3755

Position of the ending point of the progressive blur. The position is in normalized object space (top left corner of the bounding box of the object is (0, 0) and the bottom right is (1,1)).

---

### radius

> `readonly` **radius**: `number`

Defined in: figmaPluginTypes.ts:3715

The radius of the blur. Must be >= 0. A lower radius creates a sharper blur. For progressive blurs, this is the end radius of the blur.

#### Inherited from

[`BlurEffectBase`](BlurEffectBase.md).[`radius`](BlurEffectBase.md#radius)

---

### startOffset

> `readonly` **startOffset**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:3751

Position of the starting point of the progressive blur. The position is in normalized object space (top left corner of the bounding box of the object is (0, 0) and the bottom right is (1,1)).

---

### startRadius

> `readonly` **startRadius**: `number`

Defined in: figmaPluginTypes.ts:3747

Radius of the starting point of the progressive blur.

---

### type

> `readonly` **type**: `"LAYER_BLUR"` \| `"BACKGROUND_BLUR"`

Defined in: figmaPluginTypes.ts:3711

The string literal representing the type of effect this is. Always check the `type` before reading other properties.

#### Inherited from

[`BlurEffectBase`](BlurEffectBase.md).[`type`](BlurEffectBase.md#type)

---

### visible

> `readonly` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:3719

Whether this blur is visible.

#### Inherited from

[`BlurEffectBase`](BlurEffectBase.md).[`visible`](BlurEffectBase.md#visible)
