---

ExportSettingsPDF

# Interface: ExportSettingsPDF

Defined in: figmaPluginTypes.ts:4250

## See

https://www.figma.com/plugin-docs/api/ExportSettings

## Properties

### colorProfile?

> `readonly` `optional` **colorProfile**: `"DOCUMENT"` \| `"SRGB"` \| `"DISPLAY_P3_V4"`

Defined in: figmaPluginTypes.ts:4259

---

### contentsOnly?

> `readonly` `optional` **contentsOnly**: `boolean`

Defined in: figmaPluginTypes.ts:4256

---

### format

> `readonly` **format**: `"PDF"`

Defined in: figmaPluginTypes.ts:4255

The string literal "PDF" representing the export format.
When reading [ExportMixin.exportSettings](ExportMixin.md#exportsettings), always check the `format` before reading other properties.

---

### suffix?

> `readonly` `optional` **suffix**: `string`

Defined in: figmaPluginTypes.ts:4258

---

### useAbsoluteBounds?

> `readonly` `optional` **useAbsoluteBounds**: `boolean`

Defined in: figmaPluginTypes.ts:4257
