---

BaseNodeChange

# Interface: BaseNodeChange

Defined in: figmaPluginTypes.ts:3045

## See

https://www.figma.com/plugin-docs/api/DocumentChange

## Extends

- [`BaseDocumentChange`](BaseDocumentChange.md)

## Extended by

- [`CreateChange`](CreateChange.md)
- [`DeleteChange`](DeleteChange.md)
- [`PropertyChange`](PropertyChange.md)

## Properties

### id

> **id**: `string`

Defined in: figmaPluginTypes.ts:3036

The id of the node / style that is subject to the document change. The same that is on `node.id` or `style.id`

#### Inherited from

[`BaseDocumentChange`](BaseDocumentChange.md).[`id`](BaseDocumentChange.md#id)

---

### node

> **node**: [`SceneNode`](../type-aliases/SceneNode.md) \| [`RemovedNode`](RemovedNode.md)

Defined in: figmaPluginTypes.ts:3049

The node that changed in the document. If the node has been removed since the event happened this will be a [RemovedNode](RemovedNode.md)

---

### origin

> **origin**: `"LOCAL"` \| `"REMOTE"`

Defined in: figmaPluginTypes.ts:3040

Where the change originates from. If the change is 'LOCAL' it is from the user running the plugin and if it is 'REMOTE' it is from a different user in the file.

#### Inherited from

[`BaseDocumentChange`](BaseDocumentChange.md).[`origin`](BaseDocumentChange.md#origin)
