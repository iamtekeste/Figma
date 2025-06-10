---

BaseStyleMixin

# Interface: BaseStyleMixin

Defined in: figmaPluginTypes.ts:10036

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`PublishableMixin`](PublishableMixin.md).[`PluginDataMixin`](PluginDataMixin.md)

## Extended by

- [`PaintStyle`](PaintStyle.md)
- [`TextStyle`](TextStyle.md)
- [`EffectStyle`](EffectStyle.md)
- [`GridStyle`](GridStyle.md)

## Properties

### ~~consumers~~

> `readonly` **consumers**: [`StyleConsumers`](StyleConsumers.md)[]

Defined in: figmaPluginTypes.ts:10051

The consumers of this style. The `fields` in `StyleConsumers` refers to the field where the style is applied (e.g. a PaintStyle can be applied in `setFillStyleIdAsync` or `setStrokeStyleIdAsync`).

#### Deprecated

Use `getStyleConsumersAsync` instead. Accessing this property will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### description

> **description**: `string`

Defined in: figmaPluginTypes.ts:7052

The plain-text annotation entered by the user for this style/component.

#### Remarks

To set a rich-text description using markdown, see [PublishableMixin.descriptionMarkdown](PublishableMixin.md#descriptionmarkdown)

Caution: ⚠️ There is a currently a bug in Figma where the description field will appear to be missing or not up to date. Until this is fixed, the workaround is to re-publish nodes for which the description is missing.

#### Inherited from

[`PublishableMixin`](PublishableMixin.md).[`description`](PublishableMixin.md#description)

---

### descriptionMarkdown

> **descriptionMarkdown**: `string`

Defined in: figmaPluginTypes.ts:7061

The rich-text annotation entered by the user for this style/component.

#### Remarks

Caution: ⚠️ There is a currently a bug in Figma where the description field will appear to be missing or not up to date. Until this is fixed, the workaround is to re-publish nodes for which the description is missing.

#### Inherited from

[`PublishableMixin`](PublishableMixin.md).[`descriptionMarkdown`](PublishableMixin.md#descriptionmarkdown)

---

### documentationLinks

> **documentationLinks**: readonly [`DocumentationLink`](DocumentationLink.md)[]

Defined in: figmaPluginTypes.ts:7078

The documentation links for this style/component.

#### Remarks

This API currently only supports setting a single documentation link. To clear the documentation links, set to the empty list [].

Example:

```ts
node.documentationLinks = [{ uri: "https://www.figma.com" }];

// clear documentation links
node.documentationLinks = [];
```

#### Inherited from

[`PublishableMixin`](PublishableMixin.md).[`documentationLinks`](PublishableMixin.md#documentationlinks)

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:10040

The unique identifier of the style in the document the plugin is executing from. You can assign this value via `setFillStyleIdAsync`, `setStrokeStyleIdAsync`, `setTextStyleIdAsync`, etc. to make the node properties reflect that of the style node.

---

### key

> `readonly` **key**: `string`

Defined in: figmaPluginTypes.ts:7086

The key to use with [PluginAPI.importComponentByKeyAsync](PluginAPI.md#importcomponentbykeyasync), [PluginAPI.importComponentSetByKeyAsync](PluginAPI.md#importcomponentsetbykeyasync) and [PluginAPI.importStyleByKeyAsync](PluginAPI.md#importstylebykeyasync). Note that while this key is present on local and published components, you can only import components that are already published.

#### Inherited from

[`PublishableMixin`](PublishableMixin.md).[`key`](PublishableMixin.md#key)

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:10055

The name of the style node. Note that setting this also sets "autoRename" to false on [TextNode](TextNode.md).

---

### remote

> `readonly` **remote**: `boolean`

Defined in: figmaPluginTypes.ts:7082

Whether this style/component is a remote style/component that doesn't live in the file (i.e. is from the team library). Remote components are read-only: attempts to change their properties will throw.

#### Inherited from

[`PublishableMixin`](PublishableMixin.md).[`remote`](PublishableMixin.md#remote)

---

### type

> `readonly` **type**: [`StyleType`](../type-aliases/StyleType.md)

Defined in: figmaPluginTypes.ts:10041

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

Defined in: figmaPluginTypes.ts:7090

Gets the status of this style/component in the team library.

#### Returns

`Promise`\<[`PublishStatus`](../type-aliases/PublishStatus.md)\>

#### Inherited from

[`PublishableMixin`](PublishableMixin.md).[`getPublishStatusAsync`](PublishableMixin.md#getpublishstatusasync)

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

### getStyleConsumersAsync()

> **getStyleConsumersAsync**(): `Promise`\<[`StyleConsumers`](StyleConsumers.md)[]\>

Defined in: figmaPluginTypes.ts:10045

The consumers of this style. The `fields` in `StyleConsumers` refers to the field where the style is applied (e.g. a PaintStyle can be applied in `setFillStyleIdAsync` or `setStrokeStyleIdAsync`).

#### Returns

`Promise`\<[`StyleConsumers`](StyleConsumers.md)[]\>

---

### remove()

> **remove**(): `void`

Defined in: figmaPluginTypes.ts:10059

Deletes a local style.

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
