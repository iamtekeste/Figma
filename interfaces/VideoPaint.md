---

VideoPaint

# Interface: VideoPaint

Defined in: figmaPluginTypes.ts:4010

## See

https://www.figma.com/plugin-docs/api/Paint

## Properties

### blendMode?

> `readonly` `optional` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:4041

---

### filters?

> `readonly` `optional` **filters**: [`ImageFilters`](ImageFilters.md)

Defined in: figmaPluginTypes.ts:4038

The values for the video filter slides, equivalent to those in the paint picker. All values default to 0.0 and have range -1.0 to +1.0.

---

### opacity?

> `readonly` `optional` **opacity**: `number`

Defined in: figmaPluginTypes.ts:4040

---

### rotation?

> `readonly` `optional` **rotation**: `number`

Defined in: figmaPluginTypes.ts:4034

Applicable only for `scaleMode == "TILE" | "FILL" | "FIT"` (automatic for `scaleMode == "CROP"`). Determines the rotation of the video within the layer. Must be in increments of +90.

---

### scaleMode

> `readonly` **scaleMode**: `"FILL"` \| `"FIT"` \| `"CROP"` \| `"TILE"`

Defined in: figmaPluginTypes.ts:4018

How the image is positioned and scaled within the layer. Same as in the properties panel.

---

### scalingFactor?

> `readonly` `optional` **scalingFactor**: `number`

Defined in: figmaPluginTypes.ts:4030

Applicable only for `scaleMode == "TILE"` (automatic for other modes). Determines the scaling (thus, repetition) of the video within the layer.

---

### type

> `readonly` **type**: `"VIDEO"`

Defined in: figmaPluginTypes.ts:4014

The string literal "VIDEO" representing the type of paint this is. Always check the `type` before reading other properties.

---

### videoHash

> `readonly` **videoHash**: `null` \| `string`

Defined in: figmaPluginTypes.ts:4022

The hash (id) of the video used for this paint, if any.

---

### videoTransform?

> `readonly` `optional` **videoTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:4026

Applicable only for `scaleMode == "CROP"`. Determines how the video is positioned (thus, cropped) within the layer.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:4039
