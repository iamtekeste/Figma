---

EmbedData

# Interface: EmbedData

Defined in: figmaPluginTypes.ts:9692

## Properties

### canonicalUrl

> **canonicalUrl**: `null` \| `string`

Defined in: figmaPluginTypes.ts:9704

The canonicalUrl of an embed is the URL that will be navigated to when the embed is opened in an external tab

#### Example

```ts
https://www.example.com/items/abcdefg
```

---

### description

> **description**: `null` \| `string`

Defined in: figmaPluginTypes.ts:9712

The description of the embed, as displayed on the canvas

---

### provider

> **provider**: `null` \| `string`

Defined in: figmaPluginTypes.ts:9718

The name of the provider of an embed.

ex. 'Spotify', 'YouTube'

---

### srcUrl

> **srcUrl**: `string`

Defined in: figmaPluginTypes.ts:9698

The srcUrl of an embed is the URL that will be loaded in an iFrame when the embed is activated

#### Example

```ts
https://www.example.com/embed/items/abcdefg
```

---

### title

> **title**: `null` \| `string`

Defined in: figmaPluginTypes.ts:9708

The title of the embed, as displayed on the canvas
