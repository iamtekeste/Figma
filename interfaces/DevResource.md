---

DevResource

# Interface: DevResource

Defined in: figmaPluginTypes.ts:2640

## See

https://www.figma.com/plugin-docs/api/DevResource

## Extended by

- [`DevResourceWithNodeId`](DevResourceWithNodeId.md)

## Properties

### inheritedNodeId?

> `readonly` `optional` **inheritedNodeId**: `string`

Defined in: figmaPluginTypes.ts:2658

`inheritedNodeId` is a field only relevant to links on `INSTANCE` nodes. If `inheritedNodeId` is defined, the link is inherited from a main component or a component set. If you want to edit or delete the inherited link, you will need to go to the main node to do so. For example:

```ts
const devResource = { ..., inheritedNodeId: '1:2' }
const node = await figma.getNodeByIdAsync(devResource.inheritedNodeId)
await node.editDevResourceAsync(...)
```

---

### name

> `readonly` **name**: `string`

Defined in: figmaPluginTypes.ts:2644

The name of the resource.

---

### url

> `readonly` **url**: `string`

Defined in: figmaPluginTypes.ts:2648

The URL of the resource. This is considered the unique identifier of the resource.
