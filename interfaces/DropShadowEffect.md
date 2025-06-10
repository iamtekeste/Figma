---

DropShadowEffect

# Interface: DropShadowEffect

Defined in: figmaPluginTypes.ts:3625

## See

https://www.figma.com/plugin-docs/api/Effect

## Properties

### blendMode

> `readonly` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:3653

Determines how the color of this shadow blends with the colors underneath it. The typical default value is "NORMAL".

---

### boundVariables?

> `readonly` `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:3661

The variables bound to a particular field on this shadow effect

#### color?

> `optional` **color**: [`VariableAlias`](VariableAlias.md)

#### offsetX?

> `optional` **offsetX**: [`VariableAlias`](VariableAlias.md)

#### offsetY?

> `optional` **offsetY**: [`VariableAlias`](VariableAlias.md)

#### radius?

> `optional` **radius**: [`VariableAlias`](VariableAlias.md)

#### spread?

> `optional` **spread**: [`VariableAlias`](VariableAlias.md)

---

### color

> `readonly` **color**: [`RGBA`](RGBA.md)

Defined in: figmaPluginTypes.ts:3633

The color of the shadow, including its opacity.

---

### offset

> `readonly` **offset**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:3637

The offset of the shadow relative to its object. Use this property to simulate the direction of the light.

---

### radius

> `readonly` **radius**: `number`

Defined in: figmaPluginTypes.ts:3641

The blur radius of the shadow. Must be >= 0. A lower radius creates a sharper shadow.

---

### showShadowBehindNode?

> `readonly` `optional` **showShadowBehindNode**: `boolean`

Defined in: figmaPluginTypes.ts:3657

Whether the drop shadow should show behind translucent or transparent pixels within the node's geometry. Defaults to `false`.

---

### spread?

> `readonly` `optional` **spread**: `number`

Defined in: figmaPluginTypes.ts:3645

The distance by which to expand (or contract) the shadow. For drop shadows, a positive spread value creates a shadow larger than the node, whereas a negative value creates a shadow smaller than the node. For inner shadows, a positive `spread` value contracts the shadow. `spread` values are only accepted on rectangles and ellipses, or on frames, components, and instances with visible fill paints and `clipsContent` enabled. When left unspecified, the default value is 0.

---

### type

> `readonly` **type**: `"DROP_SHADOW"`

Defined in: figmaPluginTypes.ts:3629

The string literal representing the type of effect this is. Always check the `type` before reading other properties.

---

### visible

> `readonly` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:3649

Whether this shadow is visible.
