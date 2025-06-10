---

StyleDeleteChange

# Interface: StyleDeleteChange

Defined in: figmaPluginTypes.ts:3120

## See

https://www.figma.com/plugin-docs/api/DocumentChange

## Extends

- [`BaseStyleChange`](BaseStyleChange.md)

## Properties

### id

> **id**: `string`

Defined in: figmaPluginTypes.ts:3036

The id of the node / style that is subject to the document change. The same that is on `node.id` or `style.id`

#### Inherited from

[`BaseStyleChange`](BaseStyleChange.md).[`id`](BaseStyleChange.md#id)

---

### origin

> **origin**: `"LOCAL"` \| `"REMOTE"`

Defined in: figmaPluginTypes.ts:3040

Where the change originates from. If the change is 'LOCAL' it is from the user running the plugin and if it is 'REMOTE' it is from a different user in the file.

#### Inherited from

[`BaseStyleChange`](BaseStyleChange.md).[`origin`](BaseStyleChange.md#origin)

---

### style

> **style**: `null`

Defined in: figmaPluginTypes.ts:3125

The style that has been updated in the document. This is null for StyleDeleteChange.

#### Overrides

[`BaseStyleChange`](BaseStyleChange.md).[`style`](BaseStyleChange.md#style)

---

### type

> **type**: `"STYLE_DELETE"`

Defined in: figmaPluginTypes.ts:3124

The string literal "STYLE_DELETE" representing the type of document change this is. Always check the type before reading other properties. In this case, the returned style is null.
