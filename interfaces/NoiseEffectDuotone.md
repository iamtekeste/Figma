---

NoiseEffectDuotone

# Interface: NoiseEffectDuotone

Defined in: figmaPluginTypes.ts:3795

## See

https://www.figma.com/plugin-docs/api/Effect

## Extends

- [`NoiseEffectBase`](NoiseEffectBase.md)

## Properties

### blendMode

> `readonly` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:3772

The blend mode of the noise.

#### Inherited from

[`NoiseEffectBase`](NoiseEffectBase.md).[`blendMode`](NoiseEffectBase.md#blendmode)

---

### density

> `readonly` **density**: `number`

Defined in: figmaPluginTypes.ts:3780

The density of the noise effect.

#### Inherited from

[`NoiseEffectBase`](NoiseEffectBase.md).[`density`](NoiseEffectBase.md#density)

---

### noiseSize

> `readonly` **noiseSize**: `number`

Defined in: figmaPluginTypes.ts:3776

The size of the noise effect.

#### Inherited from

[`NoiseEffectBase`](NoiseEffectBase.md).[`noiseSize`](NoiseEffectBase.md#noisesize)

---

### noiseType

> `readonly` **noiseType**: `"DUOTONE"`

Defined in: figmaPluginTypes.ts:3800

The string literal representing the type of noise this is. Always check the `noiseType` before reading
other properties.

---

### secondaryColor

> `readonly` **secondaryColor**: [`RGBA`](RGBA.md)

Defined in: figmaPluginTypes.ts:3804

The secondary color of the noise effect.

---

### type

> `readonly` **type**: `"NOISE"`

Defined in: figmaPluginTypes.ts:3768

The string literal representing the type of effect this is. Always check the `type` before reading other properties.

#### Inherited from

[`NoiseEffectBase`](NoiseEffectBase.md).[`type`](NoiseEffectBase.md#type)
