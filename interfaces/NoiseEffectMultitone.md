---

NoiseEffectMultitone

# Interface: NoiseEffectMultitone

Defined in: figmaPluginTypes.ts:3809

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

> `readonly` **noiseType**: `"MULTITONE"`

Defined in: figmaPluginTypes.ts:3814

The string literal representing the type of noise this is. Always check the `noiseType` before reading
other properties.

---

### opacity

> `readonly` **opacity**: `number`

Defined in: figmaPluginTypes.ts:3818

The opacity of the noise effect.

---

### type

> `readonly` **type**: `"NOISE"`

Defined in: figmaPluginTypes.ts:3768

The string literal representing the type of effect this is. Always check the `type` before reading other properties.

#### Inherited from

[`NoiseEffectBase`](NoiseEffectBase.md).[`type`](NoiseEffectBase.md#type)
