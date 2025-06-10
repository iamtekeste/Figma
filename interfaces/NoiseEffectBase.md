---

NoiseEffectBase

# Interface: NoiseEffectBase

Defined in: figmaPluginTypes.ts:3764

## See

https://www.figma.com/plugin-docs/api/Effect

## Extended by

- [`NoiseEffectMonotone`](NoiseEffectMonotone.md)
- [`NoiseEffectDuotone`](NoiseEffectDuotone.md)
- [`NoiseEffectMultitone`](NoiseEffectMultitone.md)

## Properties

### blendMode

> `readonly` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:3772

The blend mode of the noise.

---

### density

> `readonly` **density**: `number`

Defined in: figmaPluginTypes.ts:3780

The density of the noise effect.

---

### noiseSize

> `readonly` **noiseSize**: `number`

Defined in: figmaPluginTypes.ts:3776

The size of the noise effect.

---

### type

> `readonly` **type**: `"NOISE"`

Defined in: figmaPluginTypes.ts:3768

The string literal representing the type of effect this is. Always check the `type` before reading other properties.
