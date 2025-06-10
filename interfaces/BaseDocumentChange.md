---

BaseDocumentChange

# Interface: BaseDocumentChange

Defined in: figmaPluginTypes.ts:3032

## See

https://www.figma.com/plugin-docs/api/DocumentChange

## Extended by

- [`BaseNodeChange`](BaseNodeChange.md)
- [`BaseStyleChange`](BaseStyleChange.md)

## Properties

### id

> **id**: `string`

Defined in: figmaPluginTypes.ts:3036

The id of the node / style that is subject to the document change. The same that is on `node.id` or `style.id`

---

### origin

> **origin**: `"LOCAL"` \| `"REMOTE"`

Defined in: figmaPluginTypes.ts:3040

Where the change originates from. If the change is 'LOCAL' it is from the user running the plugin and if it is 'REMOTE' it is from a different user in the file.
