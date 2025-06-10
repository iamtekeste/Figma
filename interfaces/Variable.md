---

Variable

# Interface: Variable

Defined in: figmaPluginTypes.ts:9321

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`PluginDataMixin`](PluginDataMixin.md)

## Properties

### codeSyntax

> `readonly` **codeSyntax**: `object`

Defined in: figmaPluginTypes.ts:9487

Code syntax definitions for this variable. Supported platforms are `'WEB'`, `'ANDROID'`, and `'iOS'`.

#### ANDROID?

> `optional` **ANDROID**: `string`

#### iOS?

> `optional` **iOS**: `string`

#### WEB?

> `optional` **WEB**: `string`

---

### description

> **description**: `string`

Defined in: figmaPluginTypes.ts:9329

Description of this variable.

---

### hiddenFromPublishing

> **hiddenFromPublishing**: `boolean`

Defined in: figmaPluginTypes.ts:9338

Whether this variable is hidden when publishing the current file as a library. Can only true if [Variable.remote](#remote) is false (e.g. this is a local variable).

#### Remarks

If the parent [VariableCollection](VariableCollection.md) is marked as `hiddenFromPublishing`, then this variable will also be hidden from publishing via the UI.
`hiddenFromPublishing` is independently toggled for a variable and collection, however both must be true for a given variable to be publishable.

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:9325

The unique identifier of this variable.

---

### key

> `readonly` **key**: `string`

Defined in: figmaPluginTypes.ts:9350

The key to use with [VariablesAPI.importVariableByKeyAsync](VariablesAPI.md#importvariablebykeyasync). Note that while this key is present on local and published variables, you can only import variables that are already published.

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:9327

The name of this variable.

---

### remote

> `readonly` **remote**: `boolean`

Defined in: figmaPluginTypes.ts:9344

Whether this variable is remote or local.

---

### resolvedType

> `readonly` **resolvedType**: [`VariableResolvedDataType`](../type-aliases/VariableResolvedDataType.md)

Defined in: figmaPluginTypes.ts:9352

The resolved type of the variable.

---

### scopes

> **scopes**: [`VariableScope`](../type-aliases/VariableScope.md)[]

Defined in: figmaPluginTypes.ts:9485

An array of scopes in the UI where this variable is shown. Setting this property will show/hide this variable in the variable picker UI for different fields.

#### Remarks

Setting scopes for a variable does not prevent that variable from being bound in other scopes (for example, via the Plugin API). This only limits the variables that are shown in pickers within the Figma UI.

---

### valuesByMode

> `readonly` **valuesByMode**: `object`

Defined in: figmaPluginTypes.ts:9473

The values for each mode of this variable. Note that this will not resolve any aliases. To return fully resolved values in all cases, consider using [Variable.resolveForConsumer](#resolveforconsumer).

#### Index Signature

\[`modeId`: `string`\]: [`VariableValue`](../type-aliases/VariableValue.md)

---

### variableCollectionId

> `readonly` **variableCollectionId**: `string`

Defined in: figmaPluginTypes.ts:9346

The ID of the collection that contains this variable.

## Methods

### getPluginData()

> **getPluginData**(`key`): `string`

Defined in: figmaPluginTypes.ts:5031

Retrieves custom information that was stored on this node or style using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). If there is no data stored for the provided key, an empty string is returned.

#### Parameters

##### key

`string`

#### Returns

`string`

#### Inherited from

[`PluginDataMixin`](PluginDataMixin.md).[`getPluginData`](PluginDataMixin.md#getplugindata)

---

### getPluginDataKeys()

> **getPluginDataKeys**(): `string`[]

Defined in: figmaPluginTypes.ts:5053

Retrieves a list of all keys stored on this node or style using using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). This enables iterating through all data stored privately on a node or style by your plugin.

#### Returns

`string`[]

#### Inherited from

[`PluginDataMixin`](PluginDataMixin.md).[`getPluginDataKeys`](PluginDataMixin.md#getplugindatakeys)

---

### getPublishStatusAsync()

> **getPublishStatusAsync**(): `Promise`\<[`PublishStatus`](../type-aliases/PublishStatus.md)\>

Defined in: figmaPluginTypes.ts:9342

Returns the publishing status of this variable in the current file.

#### Returns

`Promise`\<[`PublishStatus`](../type-aliases/PublishStatus.md)\>

---

### getSharedPluginData()

> **getSharedPluginData**(`namespace`, `key`): `string`

Defined in: figmaPluginTypes.ts:5057

Retrieves custom information that was stored on this node or style using [PluginDataMixin.setSharedPluginData](PluginDataMixin.md#setsharedplugindata). If there is no data stored for the provided namespace and key, an empty string is returned.

#### Parameters

##### namespace

`string`

##### key

`string`

#### Returns

`string`

#### Inherited from

[`PluginDataMixin`](PluginDataMixin.md).[`getSharedPluginData`](PluginDataMixin.md#getsharedplugindata)

---

### getSharedPluginDataKeys()

> **getSharedPluginDataKeys**(`namespace`): `string`[]

Defined in: figmaPluginTypes.ts:5079

Retrieves a list of all keys stored on this node or style using [PluginDataMixin.setSharedPluginData](PluginDataMixin.md#setsharedplugindata). This enables iterating through all data stored in a given namespace.

#### Parameters

##### namespace

`string`

#### Returns

`string`[]

#### Inherited from

[`PluginDataMixin`](PluginDataMixin.md).[`getSharedPluginDataKeys`](PluginDataMixin.md#getsharedplugindatakeys)

---

### remove()

> **remove**(): `void`

Defined in: figmaPluginTypes.ts:9477

Removes this variable from the document.

#### Returns

`void`

---

### removeVariableCodeSyntax()

> **removeVariableCodeSyntax**(`platform`): `void`

Defined in: figmaPluginTypes.ts:9523

Remove a platform definition from [Variable.codeSyntax](#codesyntax). Acceptable parameters are `'WEB'`, `'ANDROID'`, and `'iOS'` if previously defined.

#### Parameters

##### platform

[`CodeSyntaxPlatform`](../type-aliases/CodeSyntaxPlatform.md)

#### Returns

`void`

---

### resolveForConsumer()

> **resolveForConsumer**(`consumer`): `object`

Defined in: figmaPluginTypes.ts:9462

Retrieves the resolved value for this variable if it was bound to `consumer`.

#### Parameters

##### consumer

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

`object`

##### resolvedType

> **resolvedType**: [`VariableResolvedDataType`](../type-aliases/VariableResolvedDataType.md)

##### value

> **value**: [`VariableValue`](../type-aliases/VariableValue.md)

#### Remarks

The value that a variable resolves to depends on the following:

- The node consuming the variable and which of the collection's modes is [currently selected in the node](https://help.figma.com/hc/en-us/articles/15343816063383)
- The variable's value for the selected mode
- If that value is an alias, then the resolved value is determined using the selected modes of each collection in the alias chain

Note: It is not possible to statically determine the resolved value of a variable when there are multiple modes involved (either in the variable itself or in any variables in the alias chain).

The consuming node can have any combination of explicit or inherited variable modes per collection assigned to it.

Here are some examples illustrating how variables can resolve to different values depending on the consuming node. These examples do not work if the current file is on the Starter plan, which is limited to a single mode.

For a variable in a collection with two modes, it can resolve to up to two different values:

```ts title="Simple variable value resolution without aliasing"
// Create a collection with two modes and a variable with a different
// float value for each mode
const collection = figma.variables.createVariableCollection("Collection");
const mode1Id = collection.modes[0].modeId;
const mode2Id = collection.addMode("Mode 2");
const variable = figma.variables.createVariable(
  "My Variable",
  collection,
  "FLOAT"
);
variable.setValueForMode(mode1Id, 1);
variable.setValueForMode(mode2Id, 2);

const frame = figma.createFrame();
frame.setExplicitVariableModeForCollection(collection, mode1Id);
// Output: {value: 1, resolvedType: 'FLOAT'}
console.log(variable.resolveForConsumer(frame));

frame.setExplicitVariableModeForCollection(collection, mode2Id);
// Output: {value: 2, resolvedType: 'FLOAT'}
console.log(variable.resolveForConsumer(frame));
```

For a variable in a collection with two modes with each value aliasing to different variables in another collection with two modes, it can resolve to up to four different values.

```ts title="Variable value resolution with aliasing"
// Create two collections:
// 1. A collection with two modes and two float variables
// 2. A collection with two modes and a variable aliasing to
//    different variables in the first collection
const collection1 = figma.variables.createVariableCollection("Collection 1");
const collection1Mode1Id = collection1.modes[0].modeId;
const collection1Mode2Id = collection1.addMode("Mode 2");
const collection1Var1 = figma.variables.createVariable(
  "Variable 1",
  collection1,
  "FLOAT"
);
collection1Var1.setValueForMode(collection1Mode1Id, 1);
collection1Var1.setValueForMode(collection1Mode2Id, 2);
const collection1Var2 = figma.variables.createVariable(
  "Variable 2",
  collection1,
  "FLOAT"
);
collection1Var2.setValueForMode(collection1Mode1Id, 3);
collection1Var2.setValueForMode(collection1Mode2Id, 4);

const collection2 = figma.variables.createVariableCollection("Collection 2");
const collection2Mode1Id = collection2.modes[0].modeId;
const collection2Mode2Id = collection2.addMode("Mode 2");
const collection2Var = figma.variables.createVariable(
  "Variable 1",
  collection2,
  "FLOAT"
);
collection2Var.setValueForMode(
  collection2Mode1Id,
  figma.variables.createVariableAlias(collection1Var1)
);
collection2Var.setValueForMode(
  collection2Mode2Id,
  figma.variables.createVariableAlias(collection1Var2)
);

const frame = figma.createFrame();

frame.setExplicitVariableModeForCollection(collection1, collection1Mode1Id);
frame.setExplicitVariableModeForCollection(collection2, collection2Mode1Id);
// Output: {value: 1, resolvedType: 'FLOAT'}
console.log(collection2Var.resolveForConsumer(frame));

frame.setExplicitVariableModeForCollection(collection1, collection1Mode2Id);
frame.setExplicitVariableModeForCollection(collection2, collection2Mode1Id);
// Output: {value: 2, resolvedType: 'FLOAT'}
console.log(collection2Var.resolveForConsumer(frame));

frame.setExplicitVariableModeForCollection(collection1, collection1Mode1Id);
frame.setExplicitVariableModeForCollection(collection2, collection2Mode2Id);
// Output: {value: 3, resolvedType: 'FLOAT'}
console.log(collection2Var.resolveForConsumer(frame));

frame.setExplicitVariableModeForCollection(collection1, collection1Mode2Id);
frame.setExplicitVariableModeForCollection(collection2, collection2Mode2Id);
// Output: {value: 4, resolvedType: 'FLOAT'}
console.log(collection2Var.resolveForConsumer(frame));
```

---

### setPluginData()

> **setPluginData**(`key`, `value`): `void`

Defined in: figmaPluginTypes.ts:5049

Lets you store custom information on any node or style, **private** to your plugin. The total size of your entry (`pluginId`, `key`, `value`) cannot exceed 100 kB.

#### Parameters

##### key

`string`

The key under which to store the data. This is similar to writing to a plain object via `obj[key] = value`.

##### value

`string`

The data you want to store. If you want to store a value type other than a string, encode it as a JSON string first via `JSON.stringify` and `JSON.parse`. If you set the value to the empty string (""), the key/value pair is removed.

#### Returns

`void`

#### Remarks

The data is specific to your plugin ID. Plugins with other IDs won't be able to read this data. You can retrieve it later by calling `getPluginData` with the same key. To find all data stored on a node or style by your plugin use `getPluginDataKeys`.

Caution: ⚠ The data is stored privately for **stability**, not **security**. It prevents other plugins from accessing with your data. It does not, however, prevent users from seeing the data given sufficient effort. For example, they could export the document as a .fig file and try to decode it.

Caution: ⚠ Data will become inaccessible if your plugin ID changes.

Caution: ⚠ Total entry size cannot exceed 100 kB.

#### Inherited from

[`PluginDataMixin`](PluginDataMixin.md).[`setPluginData`](PluginDataMixin.md#setplugindata)

---

### setSharedPluginData()

> **setSharedPluginData**(`namespace`, `key`, `value`): `void`

Defined in: figmaPluginTypes.ts:5075

Lets you store custom information on any node or style, **public** to all plugins. The total size of your entry (`namespace`, `key`, `value`) cannot exceed 100 kB.

#### Parameters

##### namespace

`string`

A unique string to identify your plugin and avoid key collisions with other plugins. The namespace must be at least 3 alphanumeric characters.

##### key

`string`

The key under which to store the data. This is similar to writing to a plain object via `obj[key] = value`.

##### value

`string`

The data you want to store. If you want to store a value type other than a string, encode it as a JSON string first via `JSON.stringify` and `JSON.parse`. If you set the value to the empty string (""), the key/value pair is removed.

#### Returns

`void`

#### Remarks

This lets you store custom information on any node or style. You can retrieve it later by calling [PluginDataMixin.getSharedPluginData](PluginDataMixin.md#getsharedplugindata) with the same namespace and key. To find all data stored on a node or style in a particular namespace, use [PluginDataMixin.getSharedPluginDataKeys](PluginDataMixin.md#getsharedplugindatakeys).

Any data you write using this API will be readable by any plugin. The intent is to allow plugins to interoperate with each other. Use [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata) instead if you don't want other plugins to be able to read your data.

You must also provide a `namespace` argument to avoid key collisions with other plugins. This argument is mandatory to prevent multiple plugins from using generic key names like `data` and overwriting one another. We recommend passing a value that identifies your plugin. This namespace can be given to authors of other plugins so that they can read data from your plugin.

Caution: ⚠ Total entry size cannot exceed 100 kB.

#### Inherited from

[`PluginDataMixin`](PluginDataMixin.md).[`setSharedPluginData`](PluginDataMixin.md#setsharedplugindata)

---

### setValueForMode()

> **setValueForMode**(`modeId`, `newValue`): `void`

Defined in: figmaPluginTypes.ts:9469

Sets the value of this variable for the provided mode.

#### Parameters

##### modeId

`string`

##### newValue

[`VariableValue`](../type-aliases/VariableValue.md)

#### Returns

`void`

---

### setVariableCodeSyntax()

> **setVariableCodeSyntax**(`platform`, `value`): `void`

Defined in: figmaPluginTypes.ts:9519

Add or modify a platform definition on [Variable.codeSyntax](#codesyntax). Acceptable platforms are `'WEB'`, `'ANDROID'`, and `'iOS'`.

#### Parameters

##### platform

[`CodeSyntaxPlatform`](../type-aliases/CodeSyntaxPlatform.md)

##### value

`string`

#### Returns

`void`

#### Remarks

Here’s an example of adding code syntax definitions to a variable:

```ts
const collection =
  figma.variables.createVariableCollection("Example Collection");
const variable = figma.variables.createVariable(
  "ExampleVariableName",
  collection,
  "STRING"
);
variable.setVariableCodeSyntax("WEB", "example-variable-name");
variable.setVariableCodeSyntax("ANDROID", "exampleVariableName");
variable.setVariableCodeSyntax("iOS", "exampleVariableName");

// Output:
// {
//   WEB: 'example-variable-name',
//   ANDROID: 'exampleVariableName',
//   iOS: 'exampleVariableName'
// }

console.log(variable.codeSyntax);
```
