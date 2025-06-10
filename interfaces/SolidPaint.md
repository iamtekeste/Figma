---

SolidPaint

# Interface: SolidPaint

Defined in: figmaPluginTypes.ts:3899

## See

https://www.figma.com/plugin-docs/api/Paint

## Properties

### blendMode?

> `readonly` `optional` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:3943

Determines how the color of this paint blends with the colors underneath it. Defaults to "NORMAL".

---

### boundVariables?

> `readonly` `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:3947

The variables bound to a particular field on this paint

#### color?

> `optional` **color**: [`VariableAlias`](VariableAlias.md)

---

### color

> `readonly` **color**: [`RGB`](RGB.md)

Defined in: figmaPluginTypes.ts:3919

The color of the paint. This does not have a alpha property, use `opacity` instead.

You can use the [UtilAPI.solidPaint](UtilAPI.md#solidpaint) utility function to set both `color` and `opacity` using CSS color strings:

```
// Create a new SolidPaint
const paint = figma.util.solidPaint('#FF00FF88')

// Modify an existing SolidPaint
if (node.fills[0].type === 'SOLID') {
  const updated = figma.util.solidPaint('#FF00FF88', node.fills[0])
}
```

---

### opacity?

> `readonly` `optional` **opacity**: `number`

Defined in: figmaPluginTypes.ts:3939

The opacity of the paint. Must be a value between 0 and 1. Defaults to 1.

You can use the [UtilAPI.solidPaint](UtilAPI.md#solidpaint) utility function to set both `color` and `opacity` using CSS color strings:

```
// Create a new SolidPaint
const paint = figma.util.solidPaint('#FF00FF88')

// Modify an existing SolidPaint
if (node.fills[0].type === 'SOLID') {
  const updated = figma.util.solidPaint('#FF00FF88', node.fills[0])
}
```

---

### type

> `readonly` **type**: `"SOLID"`

Defined in: figmaPluginTypes.ts:3903

The string literal "SOLID" representing the type of paint this is. Always check the `type` before reading other properties.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:3923

Whether the paint is visible. Defaults to true.
