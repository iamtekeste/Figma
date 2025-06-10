---

VariablesAPI

# Interface: VariablesAPI

Defined in: figmaPluginTypes.ts:1876

## See

https://www.figma.com/plugin-docs/api/figma-variables

## Methods

### createVariable()

#### Call Signature

> **createVariable**(`name`, `collectionId`, `resolvedType`): [`Variable`](Variable.md)

Defined in: figmaPluginTypes.ts:1935

Creates a variable with a given name and resolved type inside a collection.

##### Parameters

###### name

`string`

the name of the newly created variable

###### collectionId

`string`

the ID of a collection object

###### resolvedType

[`VariableResolvedDataType`](../type-aliases/VariableResolvedDataType.md)

the resolved type of this variable

##### Returns

[`Variable`](Variable.md)

##### Deprecated

Use `createVariable(string, VariableCollection, VariableResolvedDataType)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

#### Call Signature

> **createVariable**(`name`, `collection`, `resolvedType`): [`Variable`](Variable.md)

Defined in: figmaPluginTypes.ts:1947

Creates a variable with a given name and resolved type inside a collection.

##### Parameters

###### name

`string`

the name of the newly created variable

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a collection ID is deprecated.

###### resolvedType

[`VariableResolvedDataType`](../type-aliases/VariableResolvedDataType.md)

the resolved type of this variable

##### Returns

[`Variable`](Variable.md)

---

### createVariableAlias()

> **createVariableAlias**(`variable`): [`VariableAlias`](VariableAlias.md)

Defined in: figmaPluginTypes.ts:1963

Helper function to create a variable alias.

This should be used with functions such as `node.setProperties()` to
assign component properties to variables.

#### Parameters

##### variable

[`Variable`](Variable.md)

#### Returns

[`VariableAlias`](VariableAlias.md)

---

### createVariableAliasByIdAsync()

> **createVariableAliasByIdAsync**(`variableId`): `Promise`\<[`VariableAlias`](VariableAlias.md)\>

Defined in: figmaPluginTypes.ts:1970

Helper function to create a variable alias.

This should be used with functions such as `node.setProperties()` to
assign component properties to variables.

#### Parameters

##### variableId

`string`

#### Returns

`Promise`\<[`VariableAlias`](VariableAlias.md)\>

---

### createVariableCollection()

> **createVariableCollection**(`name`): [`VariableCollection`](VariableCollection.md)

Defined in: figmaPluginTypes.ts:1956

Creates a new variable collection with the given name.

#### Parameters

##### name

`string`

the name of the newly created variable collection.

#### Returns

[`VariableCollection`](VariableCollection.md)

---

### ~~getLocalVariableCollections()~~

> **getLocalVariableCollections**(): [`VariableCollection`](VariableCollection.md)[]

Defined in: figmaPluginTypes.ts:1925

Returns all local variable collections in the current file.

#### Returns

[`VariableCollection`](VariableCollection.md)[]

#### Deprecated

Use [VariablesAPI.getLocalVariableCollectionsAsync](#getlocalvariablecollectionsasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### getLocalVariableCollectionsAsync()

> **getLocalVariableCollectionsAsync**(): `Promise`\<[`VariableCollection`](VariableCollection.md)[]\>

Defined in: figmaPluginTypes.ts:1919

Returns all local variable collections in the current file.

#### Returns

`Promise`\<[`VariableCollection`](VariableCollection.md)[]\>

---

### ~~getLocalVariables()~~

> **getLocalVariables**(`type?`): [`Variable`](Variable.md)[]

Defined in: figmaPluginTypes.ts:1915

Returns all local variables in the current file, optionally filtering by resolved type.

#### Parameters

##### type?

[`VariableResolvedDataType`](../type-aliases/VariableResolvedDataType.md)

Filters the returned variables to only be of the given resolved type.

#### Returns

[`Variable`](Variable.md)[]

#### Deprecated

Use [VariablesAPI.getLocalVariablesAsync](#getlocalvariablesasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### getLocalVariablesAsync()

> **getLocalVariablesAsync**(`type?`): `Promise`\<[`Variable`](Variable.md)[]\>

Defined in: figmaPluginTypes.ts:1908

Returns all local variables in the current file, optionally filtering by resolved type.

#### Parameters

##### type?

[`VariableResolvedDataType`](../type-aliases/VariableResolvedDataType.md)

Filters the returned variables to only be of the given resolved type.

#### Returns

`Promise`\<[`Variable`](Variable.md)[]\>

---

### ~~getVariableById()~~

> **getVariableById**(`id`): `null` \| [`Variable`](Variable.md)

Defined in: figmaPluginTypes.ts:1889

Finds a variable by ID. If not found or the provided ID is invalid, returns `null`.

#### Parameters

##### id

`string`

The variable ID to search for, which represents a unique identifier for the variable.

#### Returns

`null` \| [`Variable`](Variable.md)

#### Deprecated

Use [VariablesAPI.getVariableByIdAsync](#getvariablebyidasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### getVariableByIdAsync()

> **getVariableByIdAsync**(`id`): `Promise`\<`null` \| [`Variable`](Variable.md)\>

Defined in: figmaPluginTypes.ts:1882

Finds a variable by ID. If not found or the provided ID is invalid, returns a promise containing `null`.

#### Parameters

##### id

`string`

The variable ID to search for, which represents a unique identifier for the variable.

#### Returns

`Promise`\<`null` \| [`Variable`](Variable.md)\>

---

### ~~getVariableCollectionById()~~

> **getVariableCollectionById**(`id`): `null` \| [`VariableCollection`](VariableCollection.md)

Defined in: figmaPluginTypes.ts:1902

Finds a variable collection by ID. If not found or the provided ID is invalid, returns `null`.

#### Parameters

##### id

`string`

The variable collection ID to search for, which represents a unique identifier for the variable collection.

#### Returns

`null` \| [`VariableCollection`](VariableCollection.md)

#### Deprecated

Use [VariablesAPI.getVariableCollectionByIdAsync](#getvariablecollectionbyidasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### getVariableCollectionByIdAsync()

> **getVariableCollectionByIdAsync**(`id`): `Promise`\<`null` \| [`VariableCollection`](VariableCollection.md)\>

Defined in: figmaPluginTypes.ts:1895

Finds a variable collection by ID. If not found or the provided ID is invalid, returns a promise containing `null`.

#### Parameters

##### id

`string`

The variable collection ID to search for, which represents a unique identifier for the variable collection.

#### Returns

`Promise`\<`null` \| [`VariableCollection`](VariableCollection.md)\>

---

### importVariableByKeyAsync()

> **importVariableByKeyAsync**(`key`): `Promise`\<[`Variable`](Variable.md)\>

Defined in: figmaPluginTypes.ts:2013

Loads a variable from the team library. Promise is rejected if there is
no published variable with that key or if the request fails.

#### Parameters

##### key

`string`

the key of the variable to import.

#### Returns

`Promise`\<[`Variable`](Variable.md)\>

---

### setBoundVariableForEffect()

> **setBoundVariableForEffect**(`effect`, `field`, `variable`): [`Effect`](../type-aliases/Effect.md)

Defined in: figmaPluginTypes.ts:1990

Helper function to bind a variable to an [Effect](../type-aliases/Effect.md).

If `null` is provided as the `variable`, the given `field` will be unbound from any variables.

#### Parameters

##### effect

[`Effect`](../type-aliases/Effect.md)

##### field

[`VariableBindableEffectField`](../type-aliases/VariableBindableEffectField.md)

##### variable

`null` | [`Variable`](Variable.md)

#### Returns

[`Effect`](../type-aliases/Effect.md)

a copy of the effect which is now bound to the provided variable.

---

### setBoundVariableForLayoutGrid()

> **setBoundVariableForLayoutGrid**(`layoutGrid`, `field`, `variable`): [`LayoutGrid`](../type-aliases/LayoutGrid.md)

Defined in: figmaPluginTypes.ts:2002

Helper function to bind a variable to a [LayoutGrid](../type-aliases/LayoutGrid.md).

If `null` is provided as the `variable`, the given `field` will be unbound from any variables.

#### Parameters

##### layoutGrid

[`LayoutGrid`](../type-aliases/LayoutGrid.md)

##### field

[`VariableBindableLayoutGridField`](../type-aliases/VariableBindableLayoutGridField.md)

##### variable

`null` | [`Variable`](Variable.md)

#### Returns

[`LayoutGrid`](../type-aliases/LayoutGrid.md)

a copy of the layout grid which is now bound to the provided variable.

---

### setBoundVariableForPaint()

> **setBoundVariableForPaint**(`paint`, `field`, `variable`): [`SolidPaint`](SolidPaint.md)

Defined in: figmaPluginTypes.ts:1978

Helper function to bind a variable to a [SolidPaint](SolidPaint.md).

If `null` is provided as the `variable`, the given `field` will be unbound from any variables.

#### Parameters

##### paint

[`SolidPaint`](SolidPaint.md)

##### field

`"color"`

##### variable

`null` | [`Variable`](Variable.md)

#### Returns

[`SolidPaint`](SolidPaint.md)

a copy of the paint which is now bound to the provided variable.
