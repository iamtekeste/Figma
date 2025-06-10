---

ExportSettingsSVGBase

# Interface: ExportSettingsSVGBase

Defined in: figmaPluginTypes.ts:4206

## Extended by

- [`ExportSettingsSVG`](ExportSettingsSVG.md)
- [`ExportSettingsSVGString`](ExportSettingsSVGString.md)

## Properties

### colorProfile?

> `readonly` `optional` **colorProfile**: `"DOCUMENT"` \| `"SRGB"` \| `"DISPLAY_P3_V4"`

Defined in: figmaPluginTypes.ts:4226

---

### contentsOnly?

> `readonly` `optional` **contentsOnly**: `boolean`

Defined in: figmaPluginTypes.ts:4207

---

### suffix?

> `readonly` `optional` **suffix**: `string`

Defined in: figmaPluginTypes.ts:4209

---

### svgIdAttribute?

> `readonly` `optional` **svgIdAttribute**: `boolean`

Defined in: figmaPluginTypes.ts:4221

Whether to include layer names as ID attributes in the SVG. This can be useful as a way to reference particular elements, but increases the size of the SVG. SVG features that require IDs to function, such as masks and gradients, will always have IDs. Defaults to `false`.

---

### svgOutlineText?

> `readonly` `optional` **svgOutlineText**: `boolean`

Defined in: figmaPluginTypes.ts:4217

Whether text elements are rendered as outlines (vector paths) or as `<text>` elements in SVGs. Defaults to `true`.

Rendering text elements as outlines guarantees that the text looks exactly the same in the SVG as it does in the browser/inside Figma.

Exporting as `<text>` allows text to be selectable inside SVGs and generally makes the SVG easier to read. However, this relies on the browser’s rendering engine which can vary between browsers and/or operating systems. As such, visual accuracy is not guaranteed as the result could look different than in Figma.

---

### svgSimplifyStroke?

> `readonly` `optional` **svgSimplifyStroke**: `boolean`

Defined in: figmaPluginTypes.ts:4225

Whether to export inside and outside strokes as an approximation of the original to simplify the output. Otherwise, it uses a more precise but more bloated masking technique. This is needed because SVGs only support center strokes. Defaults to `true`.

---

### useAbsoluteBounds?

> `readonly` `optional` **useAbsoluteBounds**: `boolean`

Defined in: figmaPluginTypes.ts:4208
