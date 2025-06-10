---

StylePropertyChange

# Interface: StylePropertyChange

Defined in: figmaPluginTypes.ts:3130

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

### properties

> **properties**: [`StyleChangeProperty`](../type-aliases/StyleChangeProperty.md)[]

Defined in: figmaPluginTypes.ts:3138

Array of properties that have been changed on the node.

---

### style

> **style**: `null` \| [`BaseStyle`](../type-aliases/BaseStyle.md)

Defined in: figmaPluginTypes.ts:3106

The style that has been updated in the document. This is null for StyleDeleteChange.

#### Inherited from

[`BaseStyleChange`](BaseStyleChange.md).[`style`](BaseStyleChange.md#style)

---

### type

> **type**: `"STYLE_PROPERTY_CHANGE"`

Defined in: figmaPluginTypes.ts:3134

The string literal "STYLE_PROPERTY_CHANGE" representing the type of document change this is. Always check the type before reading other properties.
