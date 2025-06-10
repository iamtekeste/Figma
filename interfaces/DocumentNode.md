---

DocumentNode

# Interface: DocumentNode

Defined in: figmaPluginTypes.ts:8120

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`BaseNodeMixin`](BaseNodeMixin.md)

## Properties

### children

> `readonly` **children**: readonly [`PageNode`](PageNode.md)[]

Defined in: figmaPluginTypes.ts:8128

The list of children. For `DocumentNode`s, children are always [PageNode](PageNode.md)s.

---

### documentColorProfile

> `readonly` **documentColorProfile**: `"SRGB"` \| `"LEGACY"` \| `"DISPLAY_P3"`

Defined in: figmaPluginTypes.ts:8132

The color profile of this document. This will be "LEGACY" for documents created before color management was launched.

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:4878

The unique identifier of a node. For example, `1:3`. The node id can be used with methods such as [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync), but plugins typically don't need to use this since you can usually just access a node directly.

#### Remarks

One possible use case for using the `id` is to have a serializable representation of a Figma node. To "deserialize" an id back into a node, pass it to [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync). This will return null if the node is no longer present in the document.

In the URLs for Figma files, node ids are hyphenated. However, for use with the API, node ids must use colons. For example, if a Figma file URL has the node id `1-3`, you must convert it to `1:3`.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`id`](BaseNodeMixin.md#id)

---

### isAsset

> `readonly` **isAsset**: `boolean`

Defined in: figmaPluginTypes.ts:5010

Returns true if Figma detects that a node is an asset, otherwise returns false. An asset is is either an icon or a raster image.

This property is useful if you’re building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

Note: This property uses a set of heuristics to determine if a node is an asset. At a high level an icon is a small vector graphic and an image is a node with an image fill.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`isAsset`](BaseNodeMixin.md#isasset)

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:4898

The name of the layer that appears in the layers panel. Calling `figma.root.name` will return the name, read-only, of the current file.

#### Remarks

If the node is a [TextNode](TextNode.md), the name will update automatically by default based on the `characters` property (`autoRename` is true). If you manually override the text node's name, it will set `autoRename` to false. This matches the behavior in the editor.

If the node is a [PageNode](PageNode.md) with no children and the name is a page divider name, it will set `isPageDivider` to true. A page divider name consists of all asterisks, all en dashes, all em dashes, or all spaces.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`name`](BaseNodeMixin.md#name)

---

### parent

> `readonly` **parent**: `null` \| BaseNode & ChildrenMixin

Defined in: figmaPluginTypes.ts:4888

Returns the parent of this node, if any. This property is not meant to be directly edited. To reparent, see [ChildrenMixin.appendChild](ChildrenMixin.md#appendchild).

#### Remarks

The root node (i.e. `figma.root`) doesn't have a parent.

Components accessed via [instance.getMainComponentAsync()](InstanceNode.md#getmaincomponentasync) or [instance.mainComponent](InstanceNode.md#maincomponent) do not always have a parent. They could be remote components or soft-deleted components.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`parent`](BaseNodeMixin.md#parent)

---

### removed

> `readonly` **removed**: `boolean`

Defined in: figmaPluginTypes.ts:4911

Returns true if this node has been removed since it was first accessed. If your plugin stays open for a while and stores references to nodes, you should write your code defensively and check that the nodes haven't been removed by the user.

#### Remarks

A node can be removed for any number of reasons. Some examples:

- Your plugin called node.remove() on it
- Someone else deleted the node using multiplayer
- The user triggered an undo action and the node was removed
- The user simply deleted the node
- You removed all children out of a group, and the group auto-deleted itself

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`removed`](BaseNodeMixin.md#removed)

---

### type

> `readonly` **type**: `"DOCUMENT"`

Defined in: figmaPluginTypes.ts:8124

The type of this node, represented by the string literal "DOCUMENT"

## Methods

### addDevResourceAsync()

> **addDevResourceAsync**(`url`, `name?`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5100

Adds a dev resource to a node. This will fail if the node already has a dev resource with the same url.

#### Parameters

##### url

`string`

The url of the dev resource.

##### name?

`string`

The name of the dev resource. If not provided, Figma will get the name from the url.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`addDevResourceAsync`](BaseNodeMixin.md#adddevresourceasync)

---

### appendChild()

> **appendChild**(`child`): `void`

Defined in: figmaPluginTypes.ts:8136

Adds a new page to the end of the `children` array.

#### Parameters

##### child

[`PageNode`](PageNode.md)

#### Returns

`void`

---

### deleteDevResourceAsync()

> **deleteDevResourceAsync**(`url`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5122

Deletes a dev resource on a node. This will fail if the node does not have a dev resource with the same url.

#### Parameters

##### url

`string`

The url of the dev resource.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`deleteDevResourceAsync`](BaseNodeMixin.md#deletedevresourceasync)

---

### editDevResourceAsync()

> **editDevResourceAsync**(`currentUrl`, `newValue`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5109

Edits a dev resource on a node. This will fail if the node does not have a dev resource with the same url.

#### Parameters

##### currentUrl

`string`

The current url of the dev resource.

##### newValue

The new name and/or url of the dev resource.

###### name?

`string`

###### url?

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`editDevResourceAsync`](BaseNodeMixin.md#editdevresourceasync)

---

### findAll()

> **findAll**(`callback?`): ([`PageNode`](PageNode.md) \| [`SceneNode`](../type-aliases/SceneNode.md))[]

Defined in: figmaPluginTypes.ts:8193

Searches the entire document tree. Returns all nodes for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, you must first call [PluginAPI.loadAllPagesAsync](PluginAPI.md#loadallpagesasync) to access this function.

#### Parameters

##### callback?

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`. If this argument is omitted, `findAll` returns all nodes in the subtree.

#### Returns

([`PageNode`](PageNode.md) \| [`SceneNode`](../type-aliases/SceneNode.md))[]

#### Remarks

Nodes are included in **back-to-front** order. Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

This traversal method is known as ["pre-order traversal"](<https://en.wikipedia.org/wiki/Tree_traversal#Pre-order_(NLR)>).

Note that the root node itself is **not included**.

Example: find all nodes whose name is "Color":

```ts
await figma.loadAllPagesAsync(); // call this once when the plugin runs
const colors = figma.root.findAll((n) => n.name === "Color");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

---

### findAllWithCriteria()

> **findAllWithCriteria**\<`T`\>(`criteria`): `object` & PageNode \| SceneNode[]

Defined in: figmaPluginTypes.ts:8224

Searches the entire document tree. Returns all nodes that satisfy all of specified criteria.

If the manifest contains `"documentAccess": "dynamic-page"`, you must first call [PluginAPI.loadAllPagesAsync](PluginAPI.md#loadallpagesasync) to access this function.

Similar to [ChildrenMixin.findAllWithCriteria](ChildrenMixin.md#findallwithcriteria) with the main difference being that this searches all the nodes in the document, which also includes [PageNode](PageNode.md) objects.

#### Type Parameters

##### T

`T` _extends_ (`"TEXT"` \| `"DOCUMENT"` \| `"PAGE"` \| `"SLICE"` \| `"FRAME"` \| `"GROUP"` \| `"COMPONENT_SET"` \| `"COMPONENT"` \| `"INSTANCE"` \| `"BOOLEAN_OPERATION"` \| `"VECTOR"` \| `"STAR"` \| `"LINE"` \| `"ELLIPSE"` \| `"POLYGON"` \| `"RECTANGLE"` \| `"TEXT_PATH"` \| `"TRANSFORM_GROUP"` \| `"STICKY"` \| `"CONNECTOR"` \| `"SHAPE_WITH_TEXT"` \| `"CODE_BLOCK"` \| `"STAMP"` \| `"WIDGET"` \| `"EMBED"` \| `"LINK_UNFURL"` \| `"MEDIA"` \| `"SECTION"` \| `"HIGHLIGHT"` \| `"WASHI_TAPE"` \| `"TABLE"` \| `"SLIDE"` \| `"SLIDE_ROW"` \| `"SLIDE_GRID"` \| `"INTERACTIVE_SLIDE_ELEMENT"`)[]

#### Parameters

##### criteria

[`FindAllCriteria`](FindAllCriteria.md)\<`T`\>

#### Returns

`object` & PageNode \| SceneNode[]

---

### findChild()

> **findChild**(`callback`): `null` \| [`PageNode`](PageNode.md)

Defined in: figmaPluginTypes.ts:8168

Searches the immediate children of this node (i.e. all page nodes, not including their children). Returns the first page for which `callback` returns true.

#### Parameters

##### callback

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`.

#### Returns

`null` \| [`PageNode`](PageNode.md)

#### Remarks

This function returns `null` if no matching node is found.

Example: find the first page matching a certain name scheme

```ts
const firstTemplate = figma.root.findChild((n) => n.name.includes("template"));
```

---

### findChildren()

> **findChildren**(`callback?`): [`PageNode`](PageNode.md)[]

Defined in: figmaPluginTypes.ts:8153

Searches the immediate children of this node (i.e. all page nodes, not including their children). Returns all pages for which `callback` returns true.

#### Parameters

##### callback?

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`. If this argument is omitted, `findChildren` returns `node.children`.

#### Returns

[`PageNode`](PageNode.md)[]

#### Remarks

Example: find pages matching a certain name scheme

```ts
const templates = figma.root.findChildren((n) => n.name.includes("template"));
```

---

### findOne()

> **findOne**(`callback`): `null` \| [`PageNode`](PageNode.md) \| [`SceneNode`](../type-aliases/SceneNode.md)

Defined in: figmaPluginTypes.ts:8216

Searches this entire page (this node's children, its children's children, etc.). Returns the first node for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, you must first call [PluginAPI.loadAllPagesAsync](PluginAPI.md#loadallpagesasync) to access this function.

#### Parameters

##### callback

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`.

#### Returns

`null` \| [`PageNode`](PageNode.md) \| [`SceneNode`](../type-aliases/SceneNode.md)

#### Remarks

This function returns `null` if no matching node is found. The traversal order is the same as in [ChildrenMixin.findAll](ChildrenMixin.md#findall).

Note that the root node itself is **not included**.

Example: find one node whose name is "Template":

```ts
await figma.loadAllPagesAsync(); // call this once when the plugin runs
const template = figma.root.findOne((n) => n.name === "Template");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

---

### findWidgetNodesByWidgetId()

> **findWidgetNodesByWidgetId**(`widgetId`): [`WidgetNode`](WidgetNode.md)[]

Defined in: figmaPluginTypes.ts:8242

Searches the entire document tree. Returns all widget nodes that match the provided `widgetId`.

If the manifest contains `"documentAccess": "dynamic-page"`, you must first call [PluginAPI.loadAllPagesAsync](PluginAPI.md#loadallpagesasync) to access this function.

#### Parameters

##### widgetId

`string`

The widget ID to search for, which represents unique identifier for the widget.

#### Returns

[`WidgetNode`](WidgetNode.md)[]

#### Remarks

`node.widgetId` is not to be confused with `node.id`, which is the unique identifier for the node on the canvas. In other words, if you clone a widget, the cloned widget will have a matching `widgetId` but a different `id`.

---

### getCSSAsync()

> **getCSSAsync**(): `Promise`\<\{[`key`: `string`]: `string`; \}\>

Defined in: figmaPluginTypes.ts:5014

Resolves to a JSON object of CSS properties of the node. This is the same CSS that Figma shows in the inspect panel and is helpful if you are building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

#### Returns

`Promise`\<\{[`key`: `string`]: `string`; \}\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getCSSAsync`](BaseNodeMixin.md#getcssasync)

---

### getDevResourcesAsync()

> **getDevResourcesAsync**(`options?`): `Promise`\<[`DevResourceWithNodeId`](DevResourceWithNodeId.md)[]\>

Defined in: figmaPluginTypes.ts:5091

Gets all of the dev resources on a node. This includes any inherited dev resources from components and component sets.

#### Parameters

##### options?

An optional parameter to include getting all of the dev resources on the children of the node. Defaults to false.

###### includeChildren?

`boolean`

#### Returns

`Promise`\<[`DevResourceWithNodeId`](DevResourceWithNodeId.md)[]\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getDevResourcesAsync`](BaseNodeMixin.md#getdevresourcesasync)

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

[`BaseNodeMixin`](BaseNodeMixin.md).[`getPluginData`](BaseNodeMixin.md#getplugindata)

---

### getPluginDataKeys()

> **getPluginDataKeys**(): `string`[]

Defined in: figmaPluginTypes.ts:5053

Retrieves a list of all keys stored on this node or style using using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). This enables iterating through all data stored privately on a node or style by your plugin.

#### Returns

`string`[]

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getPluginDataKeys`](BaseNodeMixin.md#getplugindatakeys)

---

### getRelaunchData()

> **getRelaunchData**(): `object`

Defined in: figmaPluginTypes.ts:5000

Retreives the reluanch data stored on this node using [BaseNodeMixin.setRelaunchData](BaseNodeMixin.md#setrelaunchdata)

#### Returns

`object`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getRelaunchData`](BaseNodeMixin.md#getrelaunchdata)

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

[`BaseNodeMixin`](BaseNodeMixin.md).[`getSharedPluginData`](BaseNodeMixin.md#getsharedplugindata)

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

[`BaseNodeMixin`](BaseNodeMixin.md).[`getSharedPluginDataKeys`](BaseNodeMixin.md#getsharedplugindatakeys)

---

### getTopLevelFrame()

> **getTopLevelFrame**(): `undefined` \| [`FrameNode`](FrameNode.md)

Defined in: figmaPluginTypes.ts:5022

Returns the top-most frame that contains this node. If the node is not inside a frame, this will return undefined.

Note: This function will only work in Figma Design and will throw an error if called in FigJam or Slides.

#### Returns

`undefined` \| [`FrameNode`](FrameNode.md)

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getTopLevelFrame`](BaseNodeMixin.md#gettoplevelframe)

---

### insertChild()

> **insertChild**(`index`, `child`): `void`

Defined in: figmaPluginTypes.ts:8140

Adds a new page at the specified index in the `children` array.

#### Parameters

##### index

`number`

##### child

[`PageNode`](PageNode.md)

#### Returns

`void`

---

### remove()

> **remove**(): `void`

Defined in: figmaPluginTypes.ts:4933

Removes this node and **all of its children** from the document.

#### Returns

`void`

#### Remarks

If you want to only remove this node but not its children, you will have to first move them to another node before calling `remove()`.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`remove`](BaseNodeMixin.md#remove)

---

### setDevResourcePreviewAsync()

> **setDevResourcePreviewAsync**(`url`, `preview`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5127

Caution: This is a private API only available to [Figma partners](https://www.figma.com/partners/)

#### Parameters

##### url

`string`

##### preview

[`PlainTextElement`](../type-aliases/PlainTextElement.md)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setDevResourcePreviewAsync`](BaseNodeMixin.md#setdevresourcepreviewasync)

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

[`BaseNodeMixin`](BaseNodeMixin.md).[`setPluginData`](BaseNodeMixin.md#setplugindata)

---

### setRelaunchData()

> **setRelaunchData**(`data`): `void`

Defined in: figmaPluginTypes.ts:4996

Sets state on the node to show a button and description when the node is selected. Clears the button and description when `relaunchData` is `{}`.

Note: In Figma and Dev Mode, this shows up in the properties panel. In FigJam, this shows up in the property menu. See [here](https://www.figma.com/plugin-docs/api/properties/nodes-setrelaunchdata#example-figma-design-ui) for examples.

#### Parameters

##### data

```ts
{
  [command: string]: string // description
}
```

e.g. `data = { myCommand: 'Short description' }`

#### Returns

`void`

#### Remarks

Each call to this method sets entirely new relaunch data, removing any relaunch data and associated buttons/descriptions from before. To maintain buttons from a previous call one can store the button information using [setPluginData](https://www.figma.com/plugin-docs/api/properties/nodes-setplugindata/) and later fetch it with [getPluginData](https://www.figma.com/plugin-docs/api/PageNode/#getplugindata) before passing it on to `setRelaunchData`.

To use this API, the plugin manifest must include a `relaunchButtons` section: see the [manifest guide](https://www.figma.com/plugin-docs/manifest#relaunchbuttons) for more information.

Note: Note that if the `command` passed to this method does not match a command in the manifest, nothing will be displayed. Similarly if the name of a command in the manifest changes or is removed, then all buttons with that command will disappear. This behavior can be used to remove buttons when a particular action is no longer supported by the plugin.

In Figma design, the relaunch data can also be placed on the [PageNode](PageNode.md) or DocumentNode, to show a button and description when nothing is selected. Relaunch buttons added to the [PageNode](PageNode.md) will be displayed on that page, combined with buttons from the DocumentNode that show on every page. This is not supported in FigJam.

## Examples

```ts title="manifest.json"
// With the following in the manifest:
"relaunchButtons": [
  {"command": "edit", "name": "Edit shape"},
  {"command": "open", "name": "Open Shaper", "multipleSelection": true}
]
```

```ts title="code.ts"
// Add two buttons (ordered by the above array from the manifest):
// * an "Edit shape" button with a description of "Edit this trapezoid
//   with Shaper" that runs the plugin with `figma.command === 'edit'`.
// * an "Open Shaper" button with no description that runs the plugin with
//   `figma.command === 'open'`.
node.setRelaunchData({ edit: 'Edit this trapezoid with Shaper', open: '' })

// With the following in the manifest:
"relaunchButtons": [
  {"command": "relaunch", "name": "Run again", "multipleSelection": true}
]

// Pass an empty description to show only a button
node.setRelaunchData({ relaunch: '' })

// Remove the button and description
node.setRelaunchData({})
```

### Example Figma Design UI

![Relaunch UI in Figma Design](https://www.figma.com/plugin-docs/img/relaunch_ui_design.png)

### Example FigJam UI

![Relaunch UI in FigJam](https://www.figma.com/plugin-docs/img/relaunch_ui_figjam.png)

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setRelaunchData`](BaseNodeMixin.md#setrelaunchdata)

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

[`BaseNodeMixin`](BaseNodeMixin.md).[`setSharedPluginData`](BaseNodeMixin.md#setsharedplugindata)

---

### toString()

> **toString**(): `string`

Defined in: figmaPluginTypes.ts:4925

Returns a string representation of the node. For debugging purposes only, do not rely on the exact output of this string in production code.

#### Returns

`string`

#### Remarks

This currently returns a string of the form `[Node ID]` where `ID` is the id of the node. This is just for debugging convenience so the node displays something useful when converted to a string. We recommend not relying on this in production.

Example:

```ts
// e.g. [Node 0:5]
console.log(`Current selected node ${figma.currentPage.selection[0]}`);
```

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`toString`](BaseNodeMixin.md#tostring)
