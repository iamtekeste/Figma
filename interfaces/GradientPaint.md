---

GradientPaint

# Interface: GradientPaint

Defined in: figmaPluginTypes.ts:3954

## See

https://www.figma.com/plugin-docs/api/Paint

## Properties

### blendMode?

> `readonly` `optional` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:3969

---

### gradientStops

> `readonly` **gradientStops**: readonly [`ColorStop`](ColorStop.md)[]

Defined in: figmaPluginTypes.ts:3966

Array of colors and their position within the gradient.

---

### gradientTransform

> `readonly` **gradientTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:3962

The positioning of the gradient within the layer.

---

### opacity?

> `readonly` `optional` **opacity**: `number`

Defined in: figmaPluginTypes.ts:3968

---

### type

> `readonly` **type**: `"GRADIENT_LINEAR"` \| `"GRADIENT_RADIAL"` \| `"GRADIENT_ANGULAR"` \| `"GRADIENT_DIAMOND"`

Defined in: figmaPluginTypes.ts:3958

The string literal representing the type of paint this is. Always check the `type` before reading other properties.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:3967
