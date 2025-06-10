---

DevResourceWithNodeId

# Interface: DevResourceWithNodeId

Defined in: figmaPluginTypes.ts:2663

## See

https://www.figma.com/plugin-docs/api/DevResource

## Extends

- [`DevResource`](DevResource.md)

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

#### Inherited from

[`DevResource`](DevResource.md).[`inheritedNodeId`](DevResource.md#inheritednodeid)

---

### name

> `readonly` **name**: `string`

Defined in: figmaPluginTypes.ts:2644

The name of the resource.

#### Inherited from

[`DevResource`](DevResource.md).[`name`](DevResource.md#name)

---

### nodeId

> **nodeId**: `string`

Defined in: figmaPluginTypes.ts:2667

The ID of the node that this link is attached to.

---

### url

> `readonly` **url**: `string`

Defined in: figmaPluginTypes.ts:2648

The URL of the resource. This is considered the unique identifier of the resource.

#### Inherited from

[`DevResource`](DevResource.md).[`url`](DevResource.md#url)
