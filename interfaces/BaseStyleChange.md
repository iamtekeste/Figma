---

BaseStyleChange

# Interface: BaseStyleChange

Defined in: figmaPluginTypes.ts:3102

## See

https://www.figma.com/plugin-docs/api/DocumentChange

## Extends

- [`BaseDocumentChange`](BaseDocumentChange.md)

## Extended by

- [`StyleCreateChange`](StyleCreateChange.md)
- [`StyleDeleteChange`](StyleDeleteChange.md)
- [`StylePropertyChange`](StylePropertyChange.md)

## Properties

### id

> **id**: `string`

Defined in: figmaPluginTypes.ts:3036

The id of the node / style that is subject to the document change. The same that is on `node.id` or `style.id`

#### Inherited from

[`BaseDocumentChange`](BaseDocumentChange.md).[`id`](BaseDocumentChange.md#id)

---

### origin

> **origin**: `"LOCAL"` \| `"REMOTE"`

Defined in: figmaPluginTypes.ts:3040

Where the change originates from. If the change is 'LOCAL' it is from the user running the plugin and if it is 'REMOTE' it is from a different user in the file.

#### Inherited from

[`BaseDocumentChange`](BaseDocumentChange.md).[`origin`](BaseDocumentChange.md#origin)

---

### style

> **style**: `null` \| [`BaseStyle`](../type-aliases/BaseStyle.md)

Defined in: figmaPluginTypes.ts:3106

The style that has been updated in the document. This is null for StyleDeleteChange.
