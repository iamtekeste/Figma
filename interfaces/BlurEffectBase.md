---

BlurEffectBase

# Interface: BlurEffectBase

Defined in: figmaPluginTypes.ts:3707

## See

https://www.figma.com/plugin-docs/api/Effect

## Extended by

- [`BlurEffectNormal`](BlurEffectNormal.md)
- [`BlurEffectProgressive`](BlurEffectProgressive.md)

## Properties

### boundVariables?

> `readonly` `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:3723

The variable bound to the radius field on this blur effect

#### radius?

> `optional` **radius**: [`VariableAlias`](VariableAlias.md)

---

### radius

> `readonly` **radius**: `number`

Defined in: figmaPluginTypes.ts:3715

The radius of the blur. Must be >= 0. A lower radius creates a sharper blur. For progressive blurs, this is the end radius of the blur.

---

### type

> `readonly` **type**: `"LAYER_BLUR"` \| `"BACKGROUND_BLUR"`

Defined in: figmaPluginTypes.ts:3711

The string literal representing the type of effect this is. Always check the `type` before reading other properties.

---

### visible

> `readonly` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:3719

Whether this blur is visible.
