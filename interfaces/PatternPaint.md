---

PatternPaint

# Interface: PatternPaint

Defined in: figmaPluginTypes.ts:4046

## See

https://www.figma.com/plugin-docs/api/Paint

## Properties

### blendMode?

> `readonly` `optional` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:4073

---

### horizontalAlignment

> `readonly` **horizontalAlignment**: `"CENTER"` \| `"START"` \| `"END"`

Defined in: figmaPluginTypes.ts:4070

The horizontal alignment of the pattern

---

### opacity?

> `readonly` `optional` **opacity**: `number`

Defined in: figmaPluginTypes.ts:4072

---

### scalingFactor

> `readonly` **scalingFactor**: `number`

Defined in: figmaPluginTypes.ts:4062

The scaling factor of the pattern

---

### sourceNodeId

> `readonly` **sourceNodeId**: `string`

Defined in: figmaPluginTypes.ts:4054

The node id of the source node for the pattern

---

### spacing

> `readonly` **spacing**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:4066

The spacing of the pattern

---

### tileType

> `readonly` **tileType**: `"RECTANGULAR"` \| `"HORIZONTAL_HEXAGONAL"` \| `"VERTICAL_HEXAGONAL"`

Defined in: figmaPluginTypes.ts:4058

The way the pattern is tiled

---

### type

> `readonly` **type**: `"PATTERN"`

Defined in: figmaPluginTypes.ts:4050

The string literal representing the type of paint this is. Always check the `type` before reading other properties.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:4071
