---

Image

# Interface: Image

Defined in: figmaPluginTypes.ts:10179

## Properties

### hash

> `readonly` **hash**: `string`

Defined in: figmaPluginTypes.ts:10183

A unique hash of the contents of the image file.

## Methods

### getBytesAsync()

> **getBytesAsync**(): `Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

Defined in: figmaPluginTypes.ts:10187

The contents of the corresponding image file. This returns a promise because the image may still need to be downloaded (images in Figma are loaded separately from the rest of the document).

#### Returns

`Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

---

### getSizeAsync()

> **getSizeAsync**(): `Promise`\<\{ `height`: `number`; `width`: `number`; \}\>

Defined in: figmaPluginTypes.ts:10191

The width and height of the image in pixels. This returns a promise because the image may still need to be downloaded (images in Figma are loaded separately from the rest of the document).

#### Returns

`Promise`\<\{ `height`: `number`; `width`: `number`; \}\>
