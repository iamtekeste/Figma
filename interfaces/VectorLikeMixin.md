---

VectorLikeMixin

# Interface: VectorLikeMixin

Defined in: figmaPluginTypes.ts:6848

## Extended by

- [`VectorNode`](VectorNode.md)
- [`HighlightNode`](HighlightNode.md)

## Properties

### handleMirroring

> **handleMirroring**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`HandleMirroring`](../type-aliases/HandleMirroring.md)

Defined in: figmaPluginTypes.ts:6866

Whether the vector handles are mirrored or independent.

---

### vectorNetwork

> **vectorNetwork**: [`VectorNetwork`](VectorNetwork.md)

Defined in: figmaPluginTypes.ts:6854

Exposes a complete, but more complex representation of vectors as a network of edges between vectices. See [VectorNetwork](VectorNetwork.md).

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setVectorNetworkAsync` to update the value.

---

### vectorPaths

> **vectorPaths**: [`VectorPaths`](../type-aliases/VectorPaths.md)

Defined in: figmaPluginTypes.ts:6862

Exposes a simple, but incomplete representation of vectors as path. See [VectorPaths](../type-aliases/VectorPaths.md)

## Methods

### setVectorNetworkAsync()

> **setVectorNetworkAsync**(`vectorNetwork`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:6858

Updates the vector network.

#### Parameters

##### vectorNetwork

[`VectorNetwork`](VectorNetwork.md)

#### Returns

`Promise`\<`void`\>
