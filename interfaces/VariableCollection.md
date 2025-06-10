---

VariableCollection

# Interface: VariableCollection

Defined in: figmaPluginTypes.ts:9525

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`PluginDataMixin`](PluginDataMixin.md)

## Properties

### defaultModeId

> `readonly` **defaultModeId**: `string`

Defined in: figmaPluginTypes.ts:9556

The default mode ID for this collection.

---

### hiddenFromPublishing

> **hiddenFromPublishing**: `boolean`

Defined in: figmaPluginTypes.ts:9535

Whether this variable collection is hidden when publishing the current file as a library. Can only true if [VariableCollection.remote](#remote) is false (e.g. this is a local variable collection).

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:9529

The unique identifier of this variable collection.

---

### key

> `readonly` **key**: `string`

Defined in: figmaPluginTypes.ts:9562

The key to use with [TeamLibraryAPI.getVariablesInLibraryCollectionAsync](TeamLibraryAPI.md#getvariablesinlibrarycollectionasync).

Note that while this key is present on local and published variable collections, `TeamLibaryAPI` can only be used to query the variables of variable collections that are already published.

---

### modes

> `readonly` **modes**: `object`[]

Defined in: figmaPluginTypes.ts:9543

The list of modes defined for this variable collection.

#### modeId

> **modeId**: `string`

#### name

> **name**: `string`

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:9531

The name of this variable collection.

---

### remote

> `readonly` **remote**: `boolean`

Defined in: figmaPluginTypes.ts:9541

Whether this variable is remote or local.

---

### variableIds

> `readonly` **variableIds**: `string`[]

Defined in: figmaPluginTypes.ts:9554

The list of variables contained in this variable collection.

Note that the order of these variables is roughly the same as what is shown in Figma Design,
however it does not account for groups. As a result, the order of these variables may not
exactly reflect the exact ordering and grouping shown in the authoring UI.

## Methods

### addMode()

> **addMode**(`name`): `string`

Defined in: figmaPluginTypes.ts:9577

Adds a new mode with the given name to this collection. Returns the newly created mode ID.

Note: This API is limited by the current file's pricing tier.
If limited the current pricing tier, this method will throw an error with the message
`in addMode: Limited to N modes only`, where N is the mode limit.

See [Figma plans and features](https://help.figma.com/hc/en-us/articles/360040328273) for more information.

#### Parameters

##### name

`string`

#### Returns

`string`

---

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

Defined in: figmaPluginTypes.ts:9539

Returns the publishing status of this variable collection in the current file.

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

Defined in: figmaPluginTypes.ts:9564

Removes this variable collection and all of its variables from the document.

#### Returns

`void`

---

### removeMode()

> **removeMode**(`modeId`): `void`

Defined in: figmaPluginTypes.ts:9566

Removes the given mode by ID.

#### Parameters

##### modeId

`string`

#### Returns

`void`

---

### renameMode()

> **renameMode**(`modeId`, `newName`): `void`

Defined in: figmaPluginTypes.ts:9579

Renames the given mode.

#### Parameters

##### modeId

`string`

##### newName

`string`

#### Returns

`void`

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
