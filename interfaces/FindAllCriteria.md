---

FindAllCriteria

# Interface: FindAllCriteria\<T\>

Defined in: figmaPluginTypes.ts:10258

## See

https://www.figma.com/plugin-docs/api/FindAllCriteria

## Type Parameters

### T

`T` _extends_ [`NodeType`](../type-aliases/NodeType.md)[]

## Properties

### pluginData?

> `optional` **pluginData**: `object`

Defined in: figmaPluginTypes.ts:10284

If specified, the search will match nodes that have [PluginData](PluginDataMixin.md#getplugindata) stored for your plugin.

```ts
// Find children that have plugin data stored.
node.findAllWithCriteria({ pluginData: {} });

// Find children that have plugin data stored with keys
// "a" or "b"
node.findAllWithCriteria({
  pluginData: {
    keys: ["a", "b"],
  },
});
```

#### keys?

> `optional` **keys**: `string`[]

---

### sharedPluginData?

> `optional` **sharedPluginData**: `object`

Defined in: figmaPluginTypes.ts:10309

If specified, the search will match nodes that have [SharedPluginData](PluginDataMixin.md#getsharedplugindata) stored on the given `namespace` and `keys`.

```ts
// Find children that have shared plugin data
// on the "foo" namespace.
node.findAllWithCriteria({
  sharedPluginData: {
    namespace: "foo",
  },
});

// Find children that have shared plugin data
// on the "foo" namespace with keys "a" or "b"
node.findAllWithCriteria({
  sharedPluginData: {
    namespace: "foo",
    keys: ["a", "b"],
  },
});
```

#### keys?

> `optional` **keys**: `string`[]

#### namespace

> **namespace**: `string`

---

### types?

> `optional` **types**: `T`

Defined in: figmaPluginTypes.ts:10267

If specified, the search will match nodes that have one of the given types.

```ts
// Find children of type text or frame.
node.findAllWithCriteria({ types: ["TEXT", "FRAME"] });
```
