---

BlurEffectNormal

# Interface: BlurEffectNormal

Defined in: figmaPluginTypes.ts:3730

## See

https://www.figma.com/plugin-docs/api/Effect

## Extends

- [`BlurEffectBase`](BlurEffectBase.md)

## Properties

### blurType

> `readonly` **blurType**: `"NORMAL"`

Defined in: figmaPluginTypes.ts:3734

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

### radius

> `readonly` **radius**: `number`

Defined in: figmaPluginTypes.ts:3715

The radius of the blur. Must be >= 0. A lower radius creates a sharper blur. For progressive blurs, this is the end radius of the blur.

#### Inherited from

[`BlurEffectBase`](BlurEffectBase.md).[`radius`](BlurEffectBase.md#radius)

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
