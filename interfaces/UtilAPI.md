---

UtilAPI

# Interface: UtilAPI

Defined in: figmaPluginTypes.ts:2370

## See

https://www.figma.com/plugin-docs/api/figma-util

## Methods

### normalizeMarkdown()

> **normalizeMarkdown**(`markdown`): `string`

Defined in: figmaPluginTypes.ts:2473

Normalizes the markdown string to verify what markdown will render with Figma's rich-text editors.

Examples:

```ts
const md = "# Hello, world!\n\nThis is a **bold** text.";
const normalizedMd = figma.util.normalizeMarkdown(md);

// Set an component description with descriptionMarkdown
component.descriptionMarkdown = normalizedMd;
```

#### Parameters

##### markdown

`string`

A markdown string to normalize.

#### Returns

`string`

---

### rgb()

> **rgb**(`color`): [`RGB`](RGB.md)

Defined in: figmaPluginTypes.ts:2394

Creates an `RGB` color object from a variety of common color encodings.

**Note**: since `RGB` colors are primarily used for creating `SolidPaint` objects, you might want to use [UtilAPI.solidPaint](#solidpaint) instead.

Accepted color formats include CSS color strings with hex, `rgb()`, `hsl()`, or `lab()` encodings, as well as `RGB` and `RGBA` objects. Alpha values in the input will be ignored. If a string encoding cannot be parsed, an error will be thrown.

Examples:

```ts
const color1 = figma.util.rgb("#FF00FF");
const color2 = figma.util.rgb("hsl(25% 50% 75%)");
```

You can alias this function for more concise code:

```ts
const rgb = figma.util.rgb;
const color = rgb("#FF00FF");
```

#### Parameters

##### color

A CSS color string, `RGB` object, or `RGBA` object. The input color's alpha value, if any, will be ignored.

`string` | [`RGB`](RGB.md) | [`RGBA`](RGBA.md)

#### Returns

[`RGB`](RGB.md)

---

### rgba()

> **rgba**(`color`): [`RGBA`](RGBA.md)

Defined in: figmaPluginTypes.ts:2419

Creates an `RGBA` color object from a variety of common color encodings.

Accepted color formats include CSS color strings with hex, `rgb()`, `hsl()`, or `lab()` encodings, as well as `RGB` and `RGBA` objects. Alpha defaults to 1 (opaque) if not provided in the input. If a string encoding cannot be parsed, an error will be thrown.

Examples:

```ts
const layoutGrid = {
  pattern: "GRID",
  sectionSize: 1,
  color: figma.util.rgba("rgb(25% 25% 25% / 0.5)"),
};
```

You can alias this function for more concise code:

```ts
const rgba = figma.util.rgba;
const color = rgba("rgb(25% 25% 25% / 0.5)");
```

#### Parameters

##### color

A CSS color string, `RGB` object, or `RGBA` object.

`string` | [`RGB`](RGB.md) | [`RGBA`](RGBA.md)

#### Returns

[`RGBA`](RGBA.md)

---

### solidPaint()

> **solidPaint**(`color`, `overrides?`): [`SolidPaint`](SolidPaint.md)

Defined in: figmaPluginTypes.ts:2456

Creates a `SolidPaint` object, assigning color and opacity from a variety of common color encodings.

Accepted color formats include CSS color strings with hex, `rgb()`, `hsl()`, or `lab()` encodings, as well as `RGB` and `RGBA` objects. The resulting alpha value will be applied to the `SolidPaint`'s `opacity` property, which defaults to 1 (opaque) if not specified. If a string encoding cannot be parsed, an error will be thrown.

Optionally, you can provide a set of overrides for any of the non-color properties of the `SolidPaint` object. This is useful for modifying the color of an existing `SolidPaint` while preserving its other properties.

Examples:

```ts
// Set the current page background to red
figma.currentPage.backgrounds = [figma.util.solidPaint("#FF0000")];

// Modify an existing SolidPaint with new color and opacity
if (node.fills[0].type === "SOLID") {
  const updated = figma.util.solidPaint("#FF00FF88", node.fills[0]);
}
```

You can alias this function for more concise code:

```ts
const solidPaint = figma.util.solidPaint;

// Set the current page background to red
figma.currentPage.backgrounds = [solidPaint("#FF0000")];

// Modify an existing SolidPaint with new color and opacity
if (node.fills[0].type === "SOLID") {
  const updated = solidPaint("#FF00FF88", node.fills[0]);
}
```

#### Parameters

##### color

A CSS color string, `RGB` object, or `RGBA` object.

`string` | [`RGB`](RGB.md) | [`RGBA`](RGBA.md)

##### overrides?

`Partial`\<[`SolidPaint`](SolidPaint.md)\>

An optional object that allows you to specify additional `SolidPaint` properties, aside from color. This is useful for modifying the color of a pre-existing `SolidPaint` object.

#### Returns

[`SolidPaint`](SolidPaint.md)
