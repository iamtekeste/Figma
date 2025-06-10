---

ExportSettingsImage

# Interface: ExportSettingsImage

Defined in: figmaPluginTypes.ts:4158

## See

https://www.figma.com/plugin-docs/api/ExportSettings

## Properties

### colorProfile?

> `readonly` `optional` **colorProfile**: `"DOCUMENT"` \| `"SRGB"` \| `"DISPLAY_P3_V4"`

Defined in: figmaPluginTypes.ts:4204

Color profile of the export.

Defaults to `'DOCUMENT'`

- `"DOCUMENT"`: Use the color profile of [DocumentNode.documentColorProfile](DocumentNode.md#documentcolorprofile).
- `"SRGB"`: Use sRGB colors. This was the previous behavior of Figma before [color management](https://help.figma.com/hc/en-us/articles/360039825114).
- `"DISPLAY_P3_V4"`: Use Display P3 colors.

---

### constraint?

> `readonly` `optional` **constraint**: [`ExportSettingsConstraints`](ExportSettingsConstraints.md)

Defined in: figmaPluginTypes.ts:4193

Constraint on the image size when exporting.

```ts
interface ExportSettingsConstraints {
  type: "SCALE" | "WIDTH" | "HEIGHT";
  value: number;
}
```

Defaults to 100% of image size `{ type: "SCALE", value: 1 }`.

- `"SCALE"`: The size of the exported image is proportional to the size of the exported layer in Figma. A `value` of 1 means the export is 100% of the layer size.
- `"WIDTH"`: The exported image is scaled to have a fixed width of `value`.
- `"HEIGHT"`: The exported image is scaled to have a fixed height of `value`.

---

### contentsOnly?

> `readonly` `optional` **contentsOnly**: `boolean`

Defined in: figmaPluginTypes.ts:4167

Whether only the contents of the node are exported, or any overlapping layer in the same area. Defaults to `true`.

---

### format

> `readonly` **format**: `"JPG"` \| `"PNG"`

Defined in: figmaPluginTypes.ts:4163

The string literal representing the export format.
When reading [ExportMixin.exportSettings](ExportMixin.md#exportsettings), always check the `format` before reading other properties.

---

### suffix?

> `readonly` `optional` **suffix**: `string`

Defined in: figmaPluginTypes.ts:4175

Suffix appended to the file name when exporting. Defaults to empty string.

---

### useAbsoluteBounds?

> `readonly` `optional` **useAbsoluteBounds**: `boolean`

Defined in: figmaPluginTypes.ts:4171

Use the full dimensions of the node regardless of whether or not it is cropped or the space around it is empty. Use this to export text nodes without cropping. Defaults to `false`.
