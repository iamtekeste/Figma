---

ExplicitVariableModesMixin

# Interface: ExplicitVariableModesMixin

Defined in: figmaPluginTypes.ts:8244

## Extended by

- [`SceneNodeMixin`](SceneNodeMixin.md)
- [`PageNode`](PageNode.md)

## Properties

### explicitVariableModes

> **explicitVariableModes**: `object`

Defined in: figmaPluginTypes.ts:8250

The explicitly set modes for this node.
For `SceneNodes`, represents a subset of [SceneNodeMixin.resolvedVariableModes](SceneNodeMixin.md#resolvedvariablemodes).
Note that this does not include [workspace and team-default modes](https://help.figma.com/hc/en-us/articles/12611253730071).

#### Index Signature

\[`collectionId`: `string`\]: `string`

## Methods

### clearExplicitVariableModeForCollection()

#### Call Signature

> **clearExplicitVariableModeForCollection**(`collectionId`): `void`

Defined in: figmaPluginTypes.ts:8258

Clears an explicit mode for the given collection on this node

##### Parameters

###### collectionId

`string`

##### Returns

`void`

##### Deprecated

Use `clearExplicitVariableModeForCollection(VariableCollection)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

#### Call Signature

> **clearExplicitVariableModeForCollection**(`collection`): `void`

Defined in: figmaPluginTypes.ts:8264

Clears an explicit mode for the given collection on this node

##### Parameters

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a variable collection ID is deprecated.

##### Returns

`void`

---

### setExplicitVariableModeForCollection()

#### Call Signature

> **setExplicitVariableModeForCollection**(`collectionId`, `modeId`): `void`

Defined in: figmaPluginTypes.ts:8270

Sets an explicit mode for the given collection on this node

##### Parameters

###### collectionId

`string`

###### modeId

`string`

##### Returns

`void`

##### Deprecated

Use `setExplicitVariableModeForCollection(VariableCollection, Variable)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

#### Call Signature

> **setExplicitVariableModeForCollection**(`collection`, `modeId`): `void`

Defined in: figmaPluginTypes.ts:8277

Sets an explicit mode for the given collection on this node

##### Parameters

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a variable collection ID is deprecated.

###### modeId

`string`

A variable mode ID.

##### Returns

`void`
