---

ImagePaint

# Interface: ImagePaint

Defined in: figmaPluginTypes.ts:3974

## See

https://www.figma.com/plugin-docs/api/Paint

## Properties

### blendMode?

> `readonly` `optional` **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:4005

---

### filters?

> `readonly` `optional` **filters**: [`ImageFilters`](ImageFilters.md)

Defined in: figmaPluginTypes.ts:4002

The values for the image filter slides, equivalent to those in the paint picker. All values default to 0.0 and have range -1.0 to +1.0.

---

### imageHash

> `readonly` **imageHash**: `null` \| `string`

Defined in: figmaPluginTypes.ts:3986

The hash (id) of the image used for this paint, if any. Use [PluginAPI.getImageByHash](PluginAPI.md#getimagebyhash) to get the corresponding image object.

---

### imageTransform?

> `readonly` `optional` **imageTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:3990

Applicable only for `scaleMode == "CROP"`. Determines how the image is positioned (thus, cropped) within the layer.

---

### opacity?

> `readonly` `optional` **opacity**: `number`

Defined in: figmaPluginTypes.ts:4004

---

### rotation?

> `readonly` `optional` **rotation**: `number`

Defined in: figmaPluginTypes.ts:3998

Applicable only for `scaleMode == "TILE" | "FILL" | "FIT"` (automatic for `scaleMode == "CROP"`). Determines the rotation of the image within the layer. Must be in increments of +90.

---

### scaleMode

> `readonly` **scaleMode**: `"FILL"` \| `"FIT"` \| `"CROP"` \| `"TILE"`

Defined in: figmaPluginTypes.ts:3982

How the image is positioned and scaled within the layer. Same as in the properties panel.

---

### scalingFactor?

> `readonly` `optional` **scalingFactor**: `number`

Defined in: figmaPluginTypes.ts:3994

Applicable only for `scaleMode == "TILE"` (automatic for other modes). Determines the scaling (thus, repetition) of the image within the layer.

---

### type

> `readonly` **type**: `"IMAGE"`

Defined in: figmaPluginTypes.ts:3978

The string literal "IMAGE" representing the type of paint this is. Always check the `type` before reading other properties.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:4003
