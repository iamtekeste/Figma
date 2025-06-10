---

ExportSettingsSVG

# Interface: ExportSettingsSVG

Defined in: figmaPluginTypes.ts:4231

## See

https://www.figma.com/plugin-docs/api/ExportSettings

## Extends

- [`ExportSettingsSVGBase`](ExportSettingsSVGBase.md)

## Properties

### colorProfile?

> `readonly` `optional` **colorProfile**: `"DOCUMENT"` \| `"SRGB"` \| `"DISPLAY_P3_V4"`

Defined in: figmaPluginTypes.ts:4226

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`colorProfile`](ExportSettingsSVGBase.md#colorprofile)

---

### contentsOnly?

> `readonly` `optional` **contentsOnly**: `boolean`

Defined in: figmaPluginTypes.ts:4207

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`contentsOnly`](ExportSettingsSVGBase.md#contentsonly)

---

### format

> `readonly` **format**: `"SVG"`

Defined in: figmaPluginTypes.ts:4236

The string literal "SVG" representing the export format.
When reading [ExportMixin.exportSettings](ExportMixin.md#exportsettings), always check the `format` before reading other properties.

---

### suffix?

> `readonly` `optional` **suffix**: `string`

Defined in: figmaPluginTypes.ts:4209

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`suffix`](ExportSettingsSVGBase.md#suffix)

---

### svgIdAttribute?

> `readonly` `optional` **svgIdAttribute**: `boolean`

Defined in: figmaPluginTypes.ts:4221

Whether to include layer names as ID attributes in the SVG. This can be useful as a way to reference particular elements, but increases the size of the SVG. SVG features that require IDs to function, such as masks and gradients, will always have IDs. Defaults to `false`.

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`svgIdAttribute`](ExportSettingsSVGBase.md#svgidattribute)

---

### svgOutlineText?

> `readonly` `optional` **svgOutlineText**: `boolean`

Defined in: figmaPluginTypes.ts:4217

Whether text elements are rendered as outlines (vector paths) or as `<text>` elements in SVGs. Defaults to `true`.

Rendering text elements as outlines guarantees that the text looks exactly the same in the SVG as it does in the browser/inside Figma.

Exporting as `<text>` allows text to be selectable inside SVGs and generally makes the SVG easier to read. However, this relies on the browser’s rendering engine which can vary between browsers and/or operating systems. As such, visual accuracy is not guaranteed as the result could look different than in Figma.

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`svgOutlineText`](ExportSettingsSVGBase.md#svgoutlinetext)

---

### svgSimplifyStroke?

> `readonly` `optional` **svgSimplifyStroke**: `boolean`

Defined in: figmaPluginTypes.ts:4225

Whether to export inside and outside strokes as an approximation of the original to simplify the output. Otherwise, it uses a more precise but more bloated masking technique. This is needed because SVGs only support center strokes. Defaults to `true`.

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`svgSimplifyStroke`](ExportSettingsSVGBase.md#svgsimplifystroke)

---

### useAbsoluteBounds?

> `readonly` `optional` **useAbsoluteBounds**: `boolean`

Defined in: figmaPluginTypes.ts:4208

#### Inherited from

[`ExportSettingsSVGBase`](ExportSettingsSVGBase.md).[`useAbsoluteBounds`](ExportSettingsSVGBase.md#useabsolutebounds)
