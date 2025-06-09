# Interface: PluginAPI

Defined in: figmaPluginTypes.ts:22

## See

https://www.figma.com/plugin-docs/api/figma

## Properties

### activeUsers

> `readonly` **activeUsers**: [`ActiveUser`](ActiveUser.md)[]

Defined in: figmaPluginTypes.ts:142

Note: This API is only available in FigJam.

`activeusers` must be specified in the permissions array in `manifest.json` to access this property.

This property contains details about the active users in the file. `figma.activeUsers[0]` will match `figma.currentUser` for the `id`, `name`, `photoUrl`, `color`, and `sessionId` properties.

***

### annotations

> `readonly` **annotations**: [`AnnotationsAPI`](AnnotationsAPI.md)

Defined in: figmaPluginTypes.ts:448

This property contains methods to work with annotations.

***

### apiVersion

> `readonly` **apiVersion**: `"1.0.0"`

Defined in: figmaPluginTypes.ts:26

The version of the Figma API this plugin is running on, as defined in your `manifest.json` in the `"api"` field.

***

### clientStorage

> `readonly` **clientStorage**: [`ClientStorageAPI`](ClientStorageAPI.md)

Defined in: figmaPluginTypes.ts:412

This property contains methods to store persistent data on the user's local machine.

Read more in the [client storage section](https://www.figma.com/plugin-docs/api/figma-clientStorage).

***

### codegen

> `readonly` **codegen**: [`CodegenAPI`](CodegenAPI.md)

Defined in: figmaPluginTypes.ts:154

This property contains methods used to integrate with the Dev Mode codegen functionality.

Read more in the [codegen section](https://www.figma.com/plugin-docs/api/figma-codegen).

***

### command

> `readonly` **command**: `string`

Defined in: figmaPluginTypes.ts:30

The currently executing command from the `manifest.json` file. It is the command string in the `ManifestMenuItem` (more details in the [manifest guide](https://www.figma.com/plugin-docs/manifest)). If the plugin does not have any menu item, this property is undefined.

***

### constants

> `readonly` **constants**: [`ConstantsAPI`](ConstantsAPI.md)

Defined in: figmaPluginTypes.ts:406

This property contains constants that can be accessed by the plugin API.

Read more in the [constants section](https://www.figma.com/plugin-docs/api/figma-constants).

***

### currentPage

> **currentPage**: [`PageNode`](PageNode.md)

Defined in: figmaPluginTypes.ts:458

The page that the user currently viewing. You can set this value to a [PageNode](PageNode.md) to switch pages.

* If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use [PluginAPI.setCurrentPageAsync](#setcurrentpageasync) to update the value.

***

### currentUser

> `readonly` **currentUser**: `null` \| [`User`](User.md)

Defined in: figmaPluginTypes.ts:134

Note: `currentuser` must be specified in the permissions array in `manifest.json` to access this property.

This property contains details about the current user.

***

### devResources?

> `readonly` `optional` **devResources**: [`DevResourcesAPI`](DevResourcesAPI.md)

Defined in: figmaPluginTypes.ts:164

Caution: This is a private API only available to [Figma partners](https://www.figma.com/partners/)

***

### editorType

> `readonly` **editorType**: `"figma"` \| `"figjam"` \| `"dev"` \| `"slides"`

Defined in: figmaPluginTypes.ts:34

The current editor type this plugin is running in. See also [Setting editor type](https://www.figma.com/plugin-docs/setting-editor-type/).

***

### fileKey

> `readonly` **fileKey**: `undefined` \| `string`

Defined in: figmaPluginTypes.ts:84

The file key of the current file this plugin is running on.
**Only [private plugins](https://help.figma.com/hc/en-us/articles/4404228629655-Create-private-organization-plugins) and Figma-owned resources (such as the Jira and Asana widgets) have access to this.**
To enable this behavior, you need to specify `enablePrivatePluginApi` in your `manifest.json`.

***

### hasMissingFont

> `readonly` **hasMissingFont**: `boolean`

Defined in: figmaPluginTypes.ts:1566

Returns true if the document contains text with missing fonts.

***

### mixed

> `readonly` **mixed**: *typeof* [`mixed`](#mixed)

Defined in: figmaPluginTypes.ts:877

This a constant value that some node properties return when they are a mix of multiple values. An example might be font size: a single text node can use multiple different font sizes for different character ranges. For those properties, you should always compare against `figma.mixed`.

#### Remarks

Example:

```ts title="Check if property is a mix of multiple values"
if (node.type === 'RECTANGLE') {
  if (node.cornerRadius !== figma.mixed) {
    console.log(`Single corner radius: ${node.cornerRadius}`)
  } else {
    console.log(`Mixed corner radius: ${node.topLeftRadius}, ${node.topRightRadius}, ${node.bottomLeftRadius}, ${node.bottomRightRadius}`)
  }
}
```

Note: Your plugin never needs to know what the actual value of `figma.mixed` is, only that it is a unique, constant value that can be compared against. That being said, this value returns an object of type `symbol` which is a more advanced feature of Javascript. [Read more about symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol). It works in TypeScript via the `unique symbol` [subtype](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-7.html#unique-symbol).

***

### mode

> `readonly` **mode**: `"default"` \| `"textreview"` \| `"inspect"` \| `"codegen"` \| `"linkpreview"` \| `"auth"`

Defined in: figmaPluginTypes.ts:70

Return the context the plugin is current running in.

- `default` - The plugin is running as a normal plugin.
- `textreview` - The plugin is running to provide text review functionality.
- `inspect` - The plugin is running in the Inspect panel in Dev Mode.
- `codegen` - The plugin is running in the Code section of the Inspect panel in Dev Mode.
- `linkpreview` - The plugin is generating a link preview for a [Dev resource](https://help.figma.com/hc/en-us/articles/15023124644247#Add_external_links_and_resources_for_developers) in Dev Mode.
- `auth` - The plugin is running to authenticate a user in Dev Mode.

Caution: The `linkpreview` and `auth` modes are only available to partner and Figma-owned plugins.

#### Remarks

Here’s a simplified example where you can create an if statement in a plugin that has one set of functionality when it is run in `Dev Mode`, and another set of functionality when run in Figma design:
```ts title="Code sample to determine editorType and mode"
if (figma.editorType === "dev") {
  // Read the document and listen to API events
  if (figma.mode === "inspect") {
    // Running in inspect panel mode
  } else if (figma.mode === "codegen") {
    // Running in codegen mode
  }
} else if (figma.editorType === "figma") {
  // If the plugin is run in Figma design, edit the document
  if (figma.mode === 'textreview') {
    // Running in text review mode
  }
} else if (figma.editorType === "figjam") {
  // Do FigJam only operations
  if (figma.mode === 'textreview') {
    // Running in text review mode
  }
}
```

***

### parameters

> `readonly` **parameters**: [`ParametersAPI`](ParametersAPI.md)

Defined in: figmaPluginTypes.ts:416

This property contains methods to handle user inputs when a plugin is launched in query mode. See [Accepting Parameters as Input](https://www.figma.com/plugin-docs/plugin-parameters) for more details.

***

### payments?

> `readonly` `optional` **payments**: [`PaymentsAPI`](PaymentsAPI.md)

Defined in: figmaPluginTypes.ts:170

Note: `payments` must be specified in the permissions array in `manifest.json` to access this property.

This property contains methods for plugins that require payment.

***

### pluginId?

> `readonly` `optional` **pluginId**: `string`

Defined in: figmaPluginTypes.ts:74

The value specified in the `manifest.json` "id" field. This only exists for Plugins.

***

### root

> `readonly` **root**: [`DocumentNode`](DocumentNode.md)

Defined in: figmaPluginTypes.ts:452

The root of the entire Figma document. This node is used to access other pages. Each child is a [PageNode](PageNode.md).

***

### skipInvisibleInstanceChildren

> **skipInvisibleInstanceChildren**: `boolean`

Defined in: figmaPluginTypes.ts:114

When enabled, causes all node properties and methods to skip over invisible nodes (and their descendants) inside [instances](InstanceNode.md).
This makes operations like document traversal much faster.

Note: Defaults to true in Figma Dev Mode and false in Figma and FigJam

#### Remarks

Accessing and modifying invisible nodes and their descendants inside instances can be slow with the plugin API.
This is especially true in large documents with tens of thousands of nodes where a call to [ChildrenMixin.findAll](ChildrenMixin.md#findall) might come across many of these invisible instance children.

If your plugin does not need access to these nodes, we recommend setting `figma.skipInvisibleInstanceChildren = true` as that often makes document traversal significantly faster.

When this flag is enabled, it will not be possible to access invisible nodes (and their descendants) inside instances. This has the following effects:

- [ChildrenMixin.children](ChildrenMixin.md#children) and methods such as [ChildrenMixin.findAll](ChildrenMixin.md#findall) will exclude these nodes.
- [PluginAPI.getNodeByIdAsync](#getnodebyidasync) will return a promise containing null.
- [PluginAPI.getNodeById](#getnodebyid) will return null.
- Accessing a property on an existing node object for an invisible node will throw an error.

For example, suppose that a portion of the document tree looks like this:

Frame (visible) → Instance (visible) → Frame (invisible) → Text (visible)

The last two frame and text nodes cannot be accessed after setting `figma.skipInvisibleInstanceChildren = true`.

The benefit of enabling this flag is that document traversal methods, [ChildrenMixin.findAll](ChildrenMixin.md#findall) and [ChildrenMixin.findOne](ChildrenMixin.md#findone), can be up to several times faster in large documents that have invisible instance children.
[ChildrenMixin.findAllWithCriteria](ChildrenMixin.md#findallwithcriteria) can be up to hundreds of times faster in large documents.

***

### teamLibrary

> `readonly` **teamLibrary**: [`TeamLibraryAPI`](TeamLibraryAPI.md)

Defined in: figmaPluginTypes.ts:443

This property contains methods to work with assets residing in a team library.

***

### textreview?

> `readonly` `optional` **textreview**: [`TextReviewAPI`](TextReviewAPI.md)

Defined in: figmaPluginTypes.ts:148

Note: `textreview` must be specified in the capabilities array in `manifest.json` to access this property.

This property contains methods that enable text review features in your plugin.

***

### timer?

> `readonly` `optional` **timer**: [`TimerAPI`](TimerAPI.md)

Defined in: figmaPluginTypes.ts:122

Note: This API is only available in FigJam

This property contains methods used to read, set, and modify the built in FigJam timer.

Read more in the [timer section](https://www.figma.com/plugin-docs/api/figma-timer).

***

### ui

> `readonly` **ui**: [`UIAPI`](UIAPI.md)

Defined in: figmaPluginTypes.ts:394

This property contains methods used to modify and communicate with the UI created via `figma.showUI(...)`.

Read more in the [UI section](https://www.figma.com/plugin-docs/api/figma-ui).

***

### util

> `readonly` **util**: [`UtilAPI`](UtilAPI.md)

Defined in: figmaPluginTypes.ts:400

This property contains convenience functions for common operations.

Read more in the [util section](https://www.figma.com/plugin-docs/api/figma-util).

***

### variables

> `readonly` **variables**: [`VariablesAPI`](VariablesAPI.md)

Defined in: figmaPluginTypes.ts:441

This property contains methods to work with Variables and Variable Collections within Figma.

***

### viewport

> `readonly` **viewport**: [`ViewportAPI`](ViewportAPI.md)

Defined in: figmaPluginTypes.ts:128

This property contains methods used to read and set the viewport, the user-visible area of the current page.

Read more in the [viewport section](https://www.figma.com/plugin-docs/api/figma-viewport).

***

### vscode?

> `readonly` `optional` **vscode**: [`VSCodeAPI`](VSCodeAPI.md)

Defined in: figmaPluginTypes.ts:160

This property contains methods used to integrate with the Figma for VS Code extension. If `undefined`, the plugin is not running in VS Code.

Read more in [Dev Mode plugins in Visual Studio Code](https://www.figma.com/plugin-docs/working-in-dev-mode/#dev-mode-plugins-in-visual-studio-code)

***

### widgetId?

> `readonly` `optional` **widgetId**: `string`

Defined in: figmaPluginTypes.ts:78

Similar to `figma.pluginId` but for widgets. The value specified in the `manifest.json` "id" field. This only exists for Widgets.

## Methods

### base64Decode()

> **base64Decode**(`data`): `Uint8Array`

Defined in: figmaPluginTypes.ts:1786

Decodes and returns a Uint8Array from the base64-encoded string `data`.

#### Parameters

##### data

`string`

#### Returns

`Uint8Array`

***

### base64Encode()

> **base64Encode**(`data`): `string`

Defined in: figmaPluginTypes.ts:1782

Returns a base64-encoded string from the Uint8Array `data`.

#### Parameters

##### data

`Uint8Array`

#### Returns

`string`

***

### closePlugin()

> **closePlugin**(`message?`): `void`

Defined in: figmaPluginTypes.ts:230

Closes the plugin. You should always call this function once your plugin is done running. When called, any UI that's open will be closed and any `setTimeout` or `setInterval` timers will be cancelled.

#### Parameters

##### message?

`string`

Optional -- display a visual bell toast with the message after the plugin closes.

#### Returns

`void`

#### Remarks

Calling `figma.closePlugin()` disables callbacks and Figma APIs. It does not, however, abort the plugin. Any lines of Javascript after this call will also run. For example, consider the following plugin that expects the user to have one layer selected:

```ts title="Simple closePlugin"
if (figma.currentPage.selection.length !== 1) {
  figma.closePlugin()
}
figma.currentPage.selection[0].opacity = 0.5
```

This will not work. The last line will still run, but will throw an exception because access to `figma.currentPage` has been disabled. As such, it is not recommended to run any code after calling `figma.closePlugin()`.

A simple way to easily exit your plugin is to wrap your plugin in a function, instead of running code at the top-level, and always follow `figma.closePlugin()` with a `return` statement:

```ts title="Early return"
function main() {
  if (figma.currentPage.selection.length !== 1) {
    figma.closePlugin()
    return
  }
  figma.currentPage.selection[0].opacity = 0.5
}
main()
```

It's good practice to have all input validation done at the start of the plugin. However, there may be cases where the plugin may need to close after a chain of multiple function calls. If you expect to have to close the plugin deep within your code, but don't want to necessarily want the user to see an error, the example above will not be sufficient.

One alternative is to use a top-level try-catch statement. However, you will need to be responsible for making sure that there are no usages of try-catch between the top-level try-catch and the call to `figma.closePlugin()`, or to pass along the close command if necessary. Example:

```ts title="Top-level try-catch"
const CLOSE_PLUGIN_MSG = "_CLOSE_PLUGIN_"
function someNestedFunctionCallThatClosesThePlugin() {
  throw CLOSE_PLUGIN_MSG
}

function main() {
  someNestedFunctionCallThatClosesThePlugin()
}

try {
  main()
} catch (e) {
  if (e === CLOSE_PLUGIN_MSG) {
    figma.closePlugin()
  } else {
    // >> DO NOT LEAVE THIS OUT <<
    // If we caught any other kind of exception,
    // it's a real error and should be passed along.
    throw e
  }
}
```

***

### combineAsVariants()

> **combineAsVariants**(`nodes`, `parent`, `index?`): [`ComponentSetNode`](ComponentSetNode.md)

Defined in: figmaPluginTypes.ts:1686

Note: This API is only available in Figma Design

Creates a new [ComponentSetNode](ComponentSetNode.md) by combining all the nodes in `nodes`, which should all have type [ComponentNode](ComponentNode.md).

#### Parameters

##### nodes

readonly [`ComponentNode`](ComponentNode.md)[]

The list of nodes in the new component set. This list must be non-empty, and must consist of only component nodes.

##### parent

[`BaseNode`](../type-aliases/BaseNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

The node under which the new component set will be created. This is similar to `parent.appendChild(componentSet)`, but must be specified at the time that the group is created rather than later.

##### index?

`number`

An optional index argument that specifies where inside `parent` the new component set will be created. When this argument is not provided, it will default to appending the component set as the last (topmost) child. This is similar to the index argument in `parent.insertChild(index, componentSet)`.

#### Returns

[`ComponentSetNode`](ComponentSetNode.md)

#### Remarks

This API is roughly the equivalent of pressing the "Combine as Variants" button in the editor, but combines the specified list of nodes rather than the current selection. You may still, of course, combine the current selection as variants by passing it as an argument:

```ts title="Combining variants"
figma.combineAsVariants(figma.currentPage.selection, parent)
```

Note: Why is there no `figma.createComponentSet()` function? It would create an empty component set, and empty component sets are not supported in Figma.

Since combining as variants involves moving nodes to a different parent, this operation is subject to many reparenting restrictions:

***

### commitUndo()

> **commitUndo**(): `void`

Defined in: figmaPluginTypes.ts:299

Commits actions to undo history. This does not trigger an undo.

#### Returns

`void`

#### Remarks

By default, plugin actions are not committed to undo history. Call `figma.commitUndo()` so that triggered
undos can revert a subset of plugin actions.

For example, after running the following plugin code, the first triggered undo will undo both the rectangle and the ellipse:
```ts
figma.createRectangle();
figma.createEllipse();
figma.closePlugin();
```
Whereas if we call `commitUndo()` in our plugin, the first triggered undo will only undo the ellipse:
```ts
figma.createRectangle();
figma.commitUndo();
figma.createEllipse();
figma.closePlugin();
```

***

### ~~createBooleanOperation()~~

> **createBooleanOperation**(): [`BooleanOperationNode`](BooleanOperationNode.md)

Defined in: figmaPluginTypes.ts:1398

#### Returns

[`BooleanOperationNode`](BooleanOperationNode.md)

#### Remarks

Using this function is not recommended because empty boolean operation nodes can have surprising, unpredictable behavior. It will eventually be remove. Use one of the functions listed above instead.

Creates a new, empty boolean operation node. The particular kind of operation is set via `.booleanOperation`. By default, the value is `"UNION"`.

This snippet, for example, creates a boolean operation node that is a union of a rectangle and an ellipse.

```ts title="Create a boolean operation node"
const node = figma.createBooleanOperation()
node.appendChild(figma.createRectangle())
node.appendChild(figma.createEllipse())
```

#### Deprecated

Use [PluginAPI.union](#union), [PluginAPI.subtract](#subtract), [PluginAPI.intersect](#intersect), [PluginAPI.exclude](#exclude) instead.

***

### createCodeBlock()

> **createCodeBlock**(): [`CodeBlockNode`](CodeBlockNode.md)

Defined in: figmaPluginTypes.ts:1266

Note: This API is only available in FigJam

Creates a new code block.

#### Returns

[`CodeBlockNode`](CodeBlockNode.md)

***

### createComponent()

> **createComponent**(): [`ComponentNode`](ComponentNode.md)

Defined in: figmaPluginTypes.ts:1070

Note: This API is only available in Figma Design

Creates a new, empty component.

#### Returns

[`ComponentNode`](ComponentNode.md)

#### Remarks

By default, the new node has width and height both at 100, and is parented under `figma.currentPage`.

This function creates a brand new component. To create a component from an existing node, use [PluginAPI.createComponentFromNode](#createcomponentfromnode).

```ts title="Create a component"
const component = figma.createComponent()
```

***

### createComponentFromNode()

> **createComponentFromNode**(`node`): [`ComponentNode`](ComponentNode.md)

Defined in: figmaPluginTypes.ts:1088

Note: This API is only available in Figma Design

Creates a component from an existing node, preserving all of its properties and children. The behavior is similar to using the **Create component** button in the toolbar.

#### Parameters

##### node

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

[`ComponentNode`](ComponentNode.md)

#### Remarks

To create a brand new component instead, use [PluginAPI.createComponent](#createcomponent).

There are many restrictions on what nodes can be turned into components. For example, the node cannot be a component or component set and cannot be inside a component, component set, or instance.

If you try to create a component from a node that cannot be turned into a component, then the function will throw a `Cannot create component from node` error.

```ts title="Create a component from a node"
const frame = figma.createFrame()
const component = figma.createComponentFromNode(frame)

***

### createConnector()

> **createConnector**(): [`ConnectorNode`](ConnectorNode.md)

Defined in: figmaPluginTypes.ts:1239

Note: This API is only available in FigJam

Creates a new connector. The behavior is similar to using the `Shift-C` shortcut followed by a click.

#### Returns

[`ConnectorNode`](ConnectorNode.md)

#### Remarks

By default, the new node has a width of 200, and is parented under `figma.currentPage`.

```ts title="Add a connector between two stickies"
// Create two stickies
const stickyLeft = figma.createSticky()
stickyLeft.x = -200

const stickyRight = figma.createSticky()
stickyRight.x = 200

// Connect the two stickies
const connector = figma.createConnector()
connector.connectorStart = {
  endpointNodeId: stickyLeft.id,
  magnet: 'AUTO'
}

connector.connectorEnd = {
  endpointNodeId: stickyRight.id,
  magnet: 'AUTO'
}
```

***

### createEffectStyle()

> **createEffectStyle**(): [`EffectStyle`](EffectStyle.md)

Defined in: figmaPluginTypes.ts:1416

Note: This API is only available in Figma Design

Creates a new Effect style.

#### Returns

[`EffectStyle`](EffectStyle.md)

***

### createEllipse()

> **createEllipse**(): [`EllipseNode`](EllipseNode.md)

Defined in: figmaPluginTypes.ts:948

Creates a new ellipse. The behavior is similar to using the `O` shortcut followed by a click.

#### Returns

[`EllipseNode`](EllipseNode.md)

#### Remarks

By default, the new node has a default fill, width and height both at 100, and is parented under `figma.currentPage`.

```ts title="Create a red, U-shaped half donut"
const ellipse = figma.createEllipse()

// Move to (50, 50)
ellipse.x = 50
ellipse.y = 50

// Set size to 200 x 100
ellipse.resize(200, 100)

// Set solid red fill
ellipse.fills = [{ type: 'SOLID', color: { r: 1, g: 0, b: 0 } }]

// Arc from 0° to 180° clockwise
ellipse.arcData = {startingAngle: 0, endingAngle: Math.PI, innerRadius: 0.5}
```

***

### createFrame()

> **createFrame**(): [`FrameNode`](FrameNode.md)

Defined in: figmaPluginTypes.ts:1054

Creates a new frame. The behavior is similar to using the `F` shortcut followed by a click.

#### Returns

[`FrameNode`](FrameNode.md)

#### Remarks

By default, the new node has a white background, width and height both at 100, and is parented under `figma.currentPage`.

```ts title="Create a frame"
const frame = figma.createFrame()

// Move to (50, 50)
frame.x = 50
frame.y = 50

// Set size to 1280 x 720
frame.resize(1280, 720)
```

***

### createGif()

> **createGif**(`hash`): [`MediaNode`](MediaNode.md)

Defined in: figmaPluginTypes.ts:1664

Note: This API is only available in FigJam

Creates a new GIF with the given `Image` hash.

#### Parameters

##### hash

`string`

#### Returns

[`MediaNode`](MediaNode.md)

#### Remarks

This API is only available in FigJam

***

### createGridStyle()

> **createGridStyle**(): [`GridStyle`](GridStyle.md)

Defined in: figmaPluginTypes.ts:1422

Note: This API is only available in Figma Design

Creates a new Grid style.

#### Returns

[`GridStyle`](GridStyle.md)

***

### createImage()

> **createImage**(`data`): [`Image`](Image.md)

Defined in: figmaPluginTypes.ts:1578

Creates an `Image` object from the raw bytes of a file content. Note that `Image` objects **are not nodes**. They are handles to images stored by Figma. Frame backgrounds, or fills of shapes (e.g. a rectangle) may contain images.
[Example: how to work with images](https://www.figma.com/plugin-docs/working-with-images).

#### Parameters

##### data

`Uint8Array`

#### Returns

[`Image`](Image.md)

#### Remarks

The `data` passed in must be encoded as a PNG, JPEG, or GIF. Images have a maximum size of 4096 pixels (4K) in width and height. Invalid images will throw an error.

***

### createImageAsync()

> **createImageAsync**(`src`): `Promise`\<[`Image`](Image.md)\>

Defined in: figmaPluginTypes.ts:1614

Creates an `Image` object from a src URL. Note that `Image` objects **are not nodes**. They are handles to images stored by Figma. Frame backgrounds, or fills of shapes (e.g. a rectangle) may contain images.

#### Parameters

##### src

`string`

#### Returns

`Promise`\<[`Image`](Image.md)\>

#### Remarks

The `src` passed in must be a URL to a PNG, JPEG, or GIF. Images have a maximum size of 4096 pixels (4K) in width and height. Invalid images will reject and log the reason in the console.

```ts title="Example usage of createImageAsync"

 figma.createImageAsync(
     'https://picsum.photos/200'
   ).then(async (image: Image) => {
     // Create node
     const node = figma.createRectangle()

     // Resize the node to match the image's width and height
     const { width, height } = await image.getSizeAsync()
     node.resize(width, height)

     // Set the fill on the node
     node.fills = [
       {
         type: 'IMAGE',
         imageHash: image.hash,
         scaleMode: 'FILL'
       }
     ]

     figma.closePlugin()
   }).catch((error: any) => {
     console.log(error)
     figma.closePlugin()
   })
```

***

### createLine()

> **createLine**(): [`LineNode`](LineNode.md)

Defined in: figmaPluginTypes.ts:923

Creates a new line.

#### Returns

[`LineNode`](LineNode.md)

#### Remarks

By default, the new node is 100 in width, has a black stroke, with weight 1, and is parented under `figma.currentPage`.

```ts title="Create a line and set basic styles"
const line = figma.createLine()

// Move to (50, 50)
line.x = 50
line.y = 50

// Make line 200px long
line.resize(200, 0)

// 4px thick red line with arrows at each end
line.strokeWeight = 4
line.strokes = [{ type: 'SOLID', color: { r: 1, g: 0, b: 0 } }]
line.strokeCap = 'ARROW_LINES'
```

***

### createLinkPreviewAsync()

> **createLinkPreviewAsync**(`url`): `Promise`\<[`EmbedNode`](EmbedNode.md) \| [`LinkUnfurlNode`](LinkUnfurlNode.md)\>

Defined in: figmaPluginTypes.ts:1652

Note: This API is only available in FigJam.

Resolves link metadata from a URL, and inserts either an embed or a unfurled preview of the link into the document
An embed will be inserted if the URL is a valid OEmbed provider (has a `<link type="application/json+oembed" ... />` tag). The returned `<iframe>` source will be converted into an EmbedNode.

Otherwise, the title, description, thumbnail, and favicon will be parsed from the HTML markup of the URL using standard `og` or `twitter` meta tags. This information will be converted into a LinkUnfurlNode.

#### Parameters

##### url

`string`

#### Returns

`Promise`\<[`EmbedNode`](EmbedNode.md) \| [`LinkUnfurlNode`](LinkUnfurlNode.md)\>

#### Remarks

This API is only available in FigJam

```ts title="Creating embeds and link unfurl nodes"
(async () => {
  // Creates an EmbedNode
  const youtubeEmbed = await figma.createLinkPreviewAsync('https://www.youtube.com/watch?v=4G9RHt2OyuY')

  // Creates a LinkUnfurlNode
  const unfurledLink = await figma.createLinkPreviewAsync('https://www.figma.com/community/plugins')
})()
```

***

### createNodeFromJSXAsync()

> **createNodeFromJSXAsync**(`jsx`): `Promise`\<[`SceneNode`](../type-aliases/SceneNode.md)\>

Defined in: figmaPluginTypes.ts:1380

This API creates a new node using the JSX API used by widgets.

#### Parameters

##### jsx

`any`

#### Returns

`Promise`\<[`SceneNode`](../type-aliases/SceneNode.md)\>

#### Remarks

This API is a convenient and ergonomic way to bulk create nodes:

```tsx
const {Image, AutoLayout} = figma.widget;

const node = await figma.createNodeFromJSXAsync(
 <AutoLayout fill="#F00" padding={20}>
   <Image src="https://picsum.photos/200" width={200} height={200}/>
 </AutoLayout>
)
```

Note: The JSX API does not support all features that exist on the equivalent SceneNode.
For example we don't support setting style ids or rendering instances via JSX.
You can always use `createNodeFromJSXAsync` to create a node and then set the properties you need on the created nodes.

Note that to use this API you must configure your build system to compile tsx.

There are 3 steps that you need to do to use this API in your plugin.

1. Install the `@figma/widget-typings` package.
2. Add the appropriate compiler options to your `tsconfig.json` file
3. Make sure that the file name for you code ends with the `.tsx` extension

Note: If you are building a widget these should already be done for you.

### Install the widget typings

In the directory of your plugin run the following command to install the widget typings:

```bash
npm i --save-dev @figma/widget-typings
```

### Add compiler options to your `tsconfig.json` file

You need to make sure that you add the following properties to your `tsconfig.json` file.
This configures typescript to transpile any jsx that you use into a way that our plugin runtime understands.

```json
"jsx": "react",
"jsxFactory": "figma.widget.h",
"jsxFragmentFactory": "figma.widget.Fragment",
```

Here is an example completed `tsconfig.json` file with the appropriate properties
added.

```json
{
  "compilerOptions": {
    "jsx": "react",
    "jsxFactory": "figma.widget.h",
    "jsxFragmentFactory": "figma.widget.Fragment",
    "target": "es6",
    "lib": [
      "es6"
    ],
    "strict": true,
    "typeRoots": [
      "./node_modules/@types",
      "./node_modules/@figma"
    ]
  }
}

```
Note: If you are using a build system (ex babel, vite, esbuild). You might have to configure the jsx options for your build system.

### Change file extension

For plugins our default template puts your code in a `code.ts` file. You should rename this to `code.tsx` so that you can use jsx in your plugin.

***

### createNodeFromSvg()

> **createNodeFromSvg**(`svg`): [`FrameNode`](FrameNode.md)

Defined in: figmaPluginTypes.ts:1570

Creates a new node from an SVG string. This is equivalent to the SVG import feature in the editor. See the [official documentation on SVG paths](https://www.w3.org/TR/SVG/paths.html) for more details.

#### Parameters

##### svg

`string`

#### Returns

[`FrameNode`](FrameNode.md)

***

### createPage()

> **createPage**(): [`PageNode`](PageNode.md)

Defined in: figmaPluginTypes.ts:1105

Note: This API is only available in Figma Design

Creates a new page, appended to the document's list of children.

#### Returns

[`PageNode`](PageNode.md)

#### Remarks

A page node can be the parent of all types of nodes except for the document node and other page nodes.

Files in a Starter team are limited to three pages. When a plugin tries to create more than three pages in a Starter team file, it triggers the following error:

```text title="Page limit error"
The Starter plan only comes with 3 pages. Upgrade to
Professional for unlimited pages.
```

***

### createPageDivider()

> **createPageDivider**(`dividerName?`): [`PageNode`](PageNode.md)

Defined in: figmaPluginTypes.ts:1115

Creates a new page divider, appended to the document's list of children. A page divider is a [PageNode](PageNode.md) with `isPageDivider` true.

#### Parameters

##### dividerName?

`string`

An optional argument to specify the name of the page divider node. It won't change how the page divider appears in the UI, but it specifies the name of the underlying node. The dividerName must be a page divider name (all asterisks, all en dashes, all em dashes, or all spaces). If no dividerName is specified, the default name for the created page divider node is "---".

#### Returns

[`PageNode`](PageNode.md)

#### Remarks

A page divider is always the child of the document node and cannot have any children.

***

### createPaintStyle()

> **createPaintStyle**(): [`PaintStyle`](PaintStyle.md)

Defined in: figmaPluginTypes.ts:1404

Note: This API is only available in Figma Design

Creates a new Paint style. This might be referred to as a Color style, or Fill style more colloquially. However, since this type of style may contain images, and may be used for backgrounds, strokes, and fills, it is called a Paint.

#### Returns

[`PaintStyle`](PaintStyle.md)

***

### createPolygon()

> **createPolygon**(): [`PolygonNode`](PolygonNode.md)

Defined in: figmaPluginTypes.ts:973

Creates a new polygon (defaults to a triangle).

#### Returns

[`PolygonNode`](PolygonNode.md)

#### Remarks

By default, the new node has three edges (i.e. a triangle), a default fill, width and height both at 100, and is parented under `figma.currentPage`.

```ts title="Create a red octagon"
const polygon = figma.createPolygon()

// Move to (50, 50)
polygon.x = 50
polygon.y = 50

// Set size to 200 x 200
polygon.resize(200, 200)

// Make the polygon 8-sided
polygon.pointCount = 8

// Set solid red fill
polygon.fills = [{ type: 'SOLID', color: { r: 1, g: 0, b: 0 } }]
```

***

### createRectangle()

> **createRectangle**(): [`RectangleNode`](RectangleNode.md)

Defined in: figmaPluginTypes.ts:899

Creates a new rectangle. The behavior is similar to using the `R` shortcut followed by a click.

#### Returns

[`RectangleNode`](RectangleNode.md)

#### Remarks

By default, the new node has a default fill, width and height both at 100, and is parented under `figma.currentPage`.

```ts title="Create a rectangle and set basic styles"
const rect = figma.createRectangle()

// Move to (50, 50)
rect.x = 50
rect.y = 50

// Set size to 200 x 100
rect.resize(200, 100)

// Set solid red fill
rect.fills = [{ type: 'SOLID', color: { r: 1, g: 0, b: 0 } }]
```

***

### createSection()

> **createSection**(): [`SectionNode`](SectionNode.md)

Defined in: figmaPluginTypes.ts:1271

Creates a new section

#### Returns

[`SectionNode`](SectionNode.md)

***

### createShapeWithText()

> **createShapeWithText**(): [`ShapeWithTextNode`](ShapeWithTextNode.md)

Defined in: figmaPluginTypes.ts:1260

Note: This API is only available in FigJam

Creates a new shape with text.

#### Returns

[`ShapeWithTextNode`](ShapeWithTextNode.md)

#### Remarks

By default, the new node has a width and height of 208, and is parented under `figma.currentPage`.

```ts title="Create a rounded rectangle shape with text"
(async () => {
  const shape = figma.createShapeWithText()
  shape.shapeType = 'ROUNDED_RECTANGLE'

  // Load the font before setting characters
  await figma.loadFontAsync(shape.text.fontName)
  shape.text.characters = 'Hello world!'
})()
```

***

### createSlice()

> **createSlice**(): [`SliceNode`](SliceNode.md)

Defined in: figmaPluginTypes.ts:1150

Creates a new slice object.

#### Returns

[`SliceNode`](SliceNode.md)

#### Remarks

By default, the new node is parented under `figma.currentPage`.

```ts title="Create a slice and export as PNG"
(async () => {
  const slice = figma.createSlice()

  // Move to (50, 50)
  slice.x = 50
  slice.y = 50

  // Set size to 500 x 500
  slice.resize(500, 500)

  // Export a PNG of this region of the canvas
  const bytes = await slice.exportAsync()

  // Add the image onto the canvas as an image fill in a frame
  const image = figma.createImage(bytes)
  const frame = figma.createFrame()
  frame.resize(500, 500)
  frame.fills = [{
    imageHash: image.hash,
    scaleMode: "FILL",
    scalingFactor: 1,
    type: "IMAGE",
  }]
})()
```

***

### createSlide()

> **createSlide**(`row?`, `col?`): [`SlideNode`](SlideNode.md)

Defined in: figmaPluginTypes.ts:1168

Note: This API is only available in Figma Slides

#### Parameters

##### row?

`number`

##### col?

`number`

#### Returns

[`SlideNode`](SlideNode.md)

#### Remarks

By default, the slide gets appended to the end of the presentation (the last child in the last Slide Row).

```ts title="Create a slide"
const slide = figma.createSlide()
```

To specify a position in the Slide Grid, pass a row and column index to the function.

```ts title="Create a slide at index 0, 0"
const slide = figma.createSlide(0, 0)
```

***

### createSlideRow()

> **createSlideRow**(`row?`): [`SlideRowNode`](SlideRowNode.md)

Defined in: figmaPluginTypes.ts:1188

Note: This API is only available in Figma Slides

Creates a new Slide Row, which automatically gets appended to the Slide Grid.

#### Parameters

##### row?

`number`

#### Returns

[`SlideRowNode`](SlideRowNode.md)

#### Remarks

By default, the row gets appended to the end of the Slide Grid.

```ts title="Create a slide row"
const slideRow = figma.createSlideRow()
```

To specify a position in the Slide Grid, pass a row index to the function.

```ts title="Create a slide row at index 0"
const slideRow = figma.createSlideRow(0)
```

***

### createStar()

> **createStar**(): [`StarNode`](StarNode.md)

Defined in: figmaPluginTypes.ts:1001

Creates a new star.

#### Returns

[`StarNode`](StarNode.md)

#### Remarks

By default, the new node has five points edges (i.e. a canonical star), a default fill, width and height both at 100, and is parented under `figma.currentPage`.

```ts title="Create a red, 7-pointed star"
const star = figma.createStar()

// Move to (50, 50)
star.x = 50
star.y = 50

// Set size to 200 x 200
star.resize(200, 200)

// Make the star 7-pointed
star.pointCount = 7

// Set solid red fill
star.fills = [{ type: 'SOLID', color: { r: 1, g: 0, b: 0 } }]

// Make the angles of each point less acute
star.innerRadius = 0.6
```

***

### createSticky()

> **createSticky**(): [`StickyNode`](StickyNode.md)

Defined in: figmaPluginTypes.ts:1208

Note: This API is only available in FigJam

Creates a new sticky. The behavior is similar to using the `S` shortcut followed by a click.

#### Returns

[`StickyNode`](StickyNode.md)

#### Remarks

By default, the new node has constant width and height both at 240, and is parented under `figma.currentPage`.

```ts title="Create a sticky with text"
(async () => {
  const sticky = figma.createSticky()

  // Load the font before setting characters
  await figma.loadFontAsync(sticky.text.fontName)
  sticky.text.characters = 'Hello world!'
})()
```

***

### createTable()

> **createTable**(`numRows?`, `numColumns?`): [`TableNode`](TableNode.md)

Defined in: figmaPluginTypes.ts:1301

Note: This API is only available in FigJam

Creates a new table.

#### Parameters

##### numRows?

`number`

##### numColumns?

`number`

#### Returns

[`TableNode`](TableNode.md)

#### Remarks

By default, a table has two rows and two columns, and is parented under `figma.currentPage`.

```ts title="Create a table and add text to cells inside"
(async () => {
  // Create a table with 2 rows and 3 columns
  const table = figma.createTable(2, 3)

  // Load the font before setting characters
  await figma.loadFontAsync(table.cellAt(0, 0).text.fontName)

  // Sets characters for the table cells:
  // A B C
  // 1 2 3
  table.cellAt(0, 0).text.characters = 'A'
  table.cellAt(0, 1).text.characters = 'B'
  table.cellAt(0, 2).text.characters = 'C'
  table.cellAt(1, 0).text.characters = '1'
  table.cellAt(1, 1).text.characters = '2'
  table.cellAt(1, 2).text.characters = '3'
})()
```

***

### createText()

> **createText**(): [`TextNode`](TextNode.md)

Defined in: figmaPluginTypes.ts:1035

Creates a new, empty text node.

#### Returns

[`TextNode`](TextNode.md)

#### Remarks

By default, parented under `figma.currentPage`. Without setting additional properties, the text has no characters. You can assign a string, to the [`characters`](https://www.figma.com/plugin-docs/api/properties/TextNode-characters) property of the returned node to provide it with text.

```ts title="Create a styled 'Hello world!' text node"
(async () => {
  const text = figma.createText()

  // Move to (50, 50)
  text.x = 50
  text.y = 50

  // Load the font in the text node before setting the characters
  await figma.loadFontAsync(text.fontName)
  text.characters = 'Hello world!'

  // Set bigger font size and red color
  text.fontSize = 18
  text.fills = [{ type: 'SOLID', color: { r: 1, g: 0, b: 0 } }]
})()
```

***

### createTextStyle()

> **createTextStyle**(): [`TextStyle`](TextStyle.md)

Defined in: figmaPluginTypes.ts:1410

Note: This API is only available in Figma Design

Creates a new Text style. By default, the text style has the Figma default text properties (font family Inter Regular, font size 12).

#### Returns

[`TextStyle`](TextStyle.md)

***

### createVector()

> **createVector**(): [`VectorNode`](VectorNode.md)

Defined in: figmaPluginTypes.ts:1009

Creates a new, empty vector network with no vertices.

#### Returns

[`VectorNode`](VectorNode.md)

#### Remarks

By default, parented under `figma.currentPage`. Without setting additional properties, the vector has a bounding box but doesn’t have any vertices. There are two ways to assign vertices to a vector node - [`vectorPaths`](https://www.figma.com/plugin-docs/api/VectorNode#vectorpaths) and [`setVectorNetworkAsync`](https://www.figma.com/plugin-docs/api/VectorNode#setvectornetworkasync). Please refer to the documentation of those properties for more details.

***

### createVideoAsync()

> **createVideoAsync**(`data`): `Promise`\<[`Video`](Video.md)\>

Defined in: figmaPluginTypes.ts:1627

Creates a `Video` object from the raw bytes of a file content. Like `Image` objects, `Video` objects **are not nodes**. They are handles to images stored by Figma. Frame backgrounds, or fills of shapes (e.g. a rectangle) may contain videos.

#### Parameters

##### data

`Uint8Array`

#### Returns

`Promise`\<[`Video`](Video.md)\>

#### Remarks

The `data` passed in must be encoded as a .MP4, .MOV, or .WebM. Videos have a maximum size of 100MB. Invalid videos will throw an error.

Video can only be added to files in a paid Education, Professional, and Organization team. Plugins running on files in free Starter teams can edit existing video in a file but not upload video to it.

***

### exclude()

> **exclude**(`nodes`, `parent`, `index?`): [`BooleanOperationNode`](BooleanOperationNode.md)

Defined in: figmaPluginTypes.ts:1762

Creates a new [BooleanOperationNode](BooleanOperationNode.md) using the EXCLUDE operation using the contents of `nodes`. The arguments to `union` are the same as in [PluginAPI.exclude](#exclude).

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

##### parent

[`BaseNode`](../type-aliases/BaseNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

##### index?

`number`

#### Returns

[`BooleanOperationNode`](BooleanOperationNode.md)

***

### flatten()

> **flatten**(`nodes`, `parent?`, `index?`): [`VectorNode`](VectorNode.md)

Defined in: figmaPluginTypes.ts:1730

Flattens every node in nodes into a new vector network.

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

The list of nodes in the new group. This list must be non-empty and cannot include any node that cannot be reparented, such as children of instances. Make a copy of those nodes first if necessary.

##### parent?

BaseNode & ChildrenMixin

The node under which the new vector will be created. This is similar to `parent.appendChild(group)` and defaults to `figma.currentPage` if left unspecified.

##### index?

`number`

An optional index argument that specifies where inside `parent` the new vector will be created. When this argument is not provided, it will default to appending the vector as the last (topmost) child. This is similar to the index argument in `parent.insertChild(index, group)`.

#### Returns

[`VectorNode`](VectorNode.md)

#### Remarks

This API is roughly the equivalent of pressing Ctrl-E/⌘E in the editor, but flattens the specified list of nodes rather than the current selection. You may still, of course, flatten the current selection by passing it as an argument:

```ts title="Flatten nodes"
figma.flatten(figma.currentPage.selection, parent)
```

Since flattening involves moving nodes to a different parent, this operation is subject to many reparenting restrictions:

***

### ~~getFileThumbnailNode()~~

> **getFileThumbnailNode**(): `null` \| [`FrameNode`](FrameNode.md) \| [`ComponentSetNode`](ComponentSetNode.md) \| [`ComponentNode`](ComponentNode.md) \| [`SectionNode`](SectionNode.md)

Defined in: figmaPluginTypes.ts:1798

#### Returns

`null` \| [`FrameNode`](FrameNode.md) \| [`ComponentSetNode`](ComponentSetNode.md) \| [`ComponentNode`](ComponentNode.md) \| [`SectionNode`](SectionNode.md)

#### Deprecated

Use [PluginAPI.getFileThumbnailNodeAsync](#getfilethumbnailnodeasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

Gets the node that is currently being used for file thumbnail, or null if the default thumbnail is used.

***

### getFileThumbnailNodeAsync()

> **getFileThumbnailNodeAsync**(): `Promise`\<`null` \| [`FrameNode`](FrameNode.md) \| [`ComponentSetNode`](ComponentSetNode.md) \| [`ComponentNode`](ComponentNode.md) \| [`SectionNode`](SectionNode.md)\>

Defined in: figmaPluginTypes.ts:1790

Gets the node that is currently being used for file thumbnail, or null if the default thumbnail is used.

#### Returns

`Promise`\<`null` \| [`FrameNode`](FrameNode.md) \| [`ComponentSetNode`](ComponentSetNode.md) \| [`ComponentNode`](ComponentNode.md) \| [`SectionNode`](SectionNode.md)\>

***

### getImageByHash()

> **getImageByHash**(`hash`): `null` \| [`Image`](Image.md)

Defined in: figmaPluginTypes.ts:1618

This gets the corresponding `Image` object for a given image hash, which can then be used to obtain the bytes of the image. This hash is found in a node's fill property as part of the ImagePaint object. If there is no image with this hash, returns null.

#### Parameters

##### hash

`string`

#### Returns

`null` \| [`Image`](Image.md)

***

### ~~getLocalEffectStyles()~~

> **getLocalEffectStyles**(): [`EffectStyle`](EffectStyle.md)[]

Defined in: figmaPluginTypes.ts:1452

#### Returns

[`EffectStyle`](EffectStyle.md)[]

#### Deprecated

Use [PluginAPI.getLocalEffectStylesAsync](#getlocaleffectstylesasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

Returns the list of local effect styles.

***

### getLocalEffectStylesAsync()

> **getLocalEffectStylesAsync**(): `Promise`\<[`EffectStyle`](EffectStyle.md)[]\>

Defined in: figmaPluginTypes.ts:1446

Returns the list of local effect styles.

#### Returns

`Promise`\<[`EffectStyle`](EffectStyle.md)[]\>

***

### ~~getLocalGridStyles()~~

> **getLocalGridStyles**(): [`GridStyle`](GridStyle.md)[]

Defined in: figmaPluginTypes.ts:1462

Returns the list of local grid styles.

#### Returns

[`GridStyle`](GridStyle.md)[]

#### Deprecated

Use [PluginAPI.getLocalGridStylesAsync](#getlocalgridstylesasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

***

### getLocalGridStylesAsync()

> **getLocalGridStylesAsync**(): `Promise`\<[`GridStyle`](GridStyle.md)[]\>

Defined in: figmaPluginTypes.ts:1456

Returns the list of local grid styles.

#### Returns

`Promise`\<[`GridStyle`](GridStyle.md)[]\>

***

### ~~getLocalPaintStyles()~~

> **getLocalPaintStyles**(): [`PaintStyle`](PaintStyle.md)[]

Defined in: figmaPluginTypes.ts:1432

#### Returns

[`PaintStyle`](PaintStyle.md)[]

#### Deprecated

Use [PluginAPI.getLocalPaintStylesAsync](#getlocalpaintstylesasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

Returns the list of local paint styles.

***

### getLocalPaintStylesAsync()

> **getLocalPaintStylesAsync**(): `Promise`\<[`PaintStyle`](PaintStyle.md)[]\>

Defined in: figmaPluginTypes.ts:1426

Returns the list of local paint styles.

#### Returns

`Promise`\<[`PaintStyle`](PaintStyle.md)[]\>

***

### ~~getLocalTextStyles()~~

> **getLocalTextStyles**(): [`TextStyle`](TextStyle.md)[]

Defined in: figmaPluginTypes.ts:1442

#### Returns

[`TextStyle`](TextStyle.md)[]

#### Deprecated

Use [PluginAPI.getLocalTextStylesAsync](#getlocaltextstylesasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

Returns the list of local text styles.

***

### getLocalTextStylesAsync()

> **getLocalTextStylesAsync**(): `Promise`\<[`TextStyle`](TextStyle.md)[]\>

Defined in: figmaPluginTypes.ts:1436

Returns the list of local text styles.

#### Returns

`Promise`\<[`TextStyle`](TextStyle.md)[]\>

***

### ~~getNodeById()~~

> **getNodeById**(`id`): `null` \| [`BaseNode`](../type-aliases/BaseNode.md)

Defined in: figmaPluginTypes.ts:426

#### Parameters

##### id

`string`

#### Returns

`null` \| [`BaseNode`](../type-aliases/BaseNode.md)

#### Deprecated

Use [PluginAPI.getNodeByIdAsync](#getnodebyidasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

Finds a node by its id in the current document. Every node has an `id` property, which is unique within the document. If the id is invalid, or the node cannot be found (e.g. removed), returns null.

***

### getNodeByIdAsync()

> **getNodeByIdAsync**(`id`): `Promise`\<`null` \| [`BaseNode`](../type-aliases/BaseNode.md)\>

Defined in: figmaPluginTypes.ts:420

Finds a node by its id in the current document. Every node has an `id` property, which is unique within the document. If the id is invalid, or the node cannot be found (e.g. removed), returns a promise containing null.

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`null` \| [`BaseNode`](../type-aliases/BaseNode.md)\>

***

### getSelectionColors()

> **getSelectionColors**(): `null` \| \{ `paints`: [`Paint`](../type-aliases/Paint.md)[]; `styles`: [`PaintStyle`](PaintStyle.md)[]; \}

Defined in: figmaPluginTypes.ts:1477

Returns all of the colors in a user’s current selection. This
returns the same values that are shown in Figma's native selection
colors feature. This can be useful for getting a list of colors and
styles in the current selection and converting them into a different
code format (like CSS variables for a user’s codebase).

If there are colors in a selection it will return an object with a
`paints` property, which is an array of `Paint[]`, and a `styles`
property, which is an array of `PaintStyle[]`.

Note: `getSelectionColors()` returns `null` if there is no selection, or
if there are too many colors in the selection (>1000).

#### Returns

`null` \| \{ `paints`: [`Paint`](../type-aliases/Paint.md)[]; `styles`: [`PaintStyle`](PaintStyle.md)[]; \}

***

### getSlideGrid()

> **getSlideGrid**(): [`SlideNode`](SlideNode.md)[][]

Defined in: figmaPluginTypes.ts:1843

Note: This API is only available in Figma Slides

#### Returns

[`SlideNode`](SlideNode.md)[][]

#### Remarks

The slide grid provides structure to both single slide view and grid view.
The order of Slides within a presentation is a key part of updating and editing a deck.
To visualize the slide nodes in a 2D array, you can call this function.

```ts
const grid = figma.getSlideGrid()
```

The returned grid is a 2D array of SlideNodes. For example:

```ts
[
  [SlideNode, SlideNode],
  [SlideNode, SlideNode, SlideNode, SlideNode, SlideNode],
  [SlideNode, SlideNode, SlideNode, SlideNode, SlideNode],
  [SlideNode, SlideNode, SlideNode],
]
```

***

### ~~getStyleById()~~

> **getStyleById**(`id`): `null` \| [`BaseStyle`](../type-aliases/BaseStyle.md)

Defined in: figmaPluginTypes.ts:436

#### Parameters

##### id

`string`

#### Returns

`null` \| [`BaseStyle`](../type-aliases/BaseStyle.md)

#### Deprecated

Use [PluginAPI.getStyleByIdAsync](#getstylebyidasync) instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

Finds a style by its id in the current document. If not found, returns null.

***

### getStyleByIdAsync()

> **getStyleByIdAsync**(`id`): `Promise`\<`null` \| [`BaseStyle`](../type-aliases/BaseStyle.md)\>

Defined in: figmaPluginTypes.ts:430

Finds a style by its id in the current document. If not found, returns a promise containing null.

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`null` \| [`BaseStyle`](../type-aliases/BaseStyle.md)\>

***

### group()

> **group**(`nodes`, `parent`, `index?`): [`GroupNode`](GroupNode.md)

Defined in: figmaPluginTypes.ts:1712

Creates new group containing all the nodes in `nodes`. There is no `createGroup` function -- use this instead. Group nodes have many quirks, like auto-resizing, that you can read about in the [FrameNode](FrameNode.md) section.

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

The list of nodes in the new group. This list must be non-empty as Figma does not support empty groups. This list cannot include any node that cannot be reparented, such as children of instances.

##### parent

[`BaseNode`](../type-aliases/BaseNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

The node under which the new group will be created. This is similar to `parent.appendChild(group)`, but must be specified at the time that the group is created rather than later.

##### index?

`number`

An optional index argument that specifies where inside `parent` the new group will be created. When this argument is not provided, it will default to appending the group as the last (topmost) child. This is similar to the index argument in `parent.insertChild(index, group)`.

#### Returns

[`GroupNode`](GroupNode.md)

#### Remarks

This API is roughly the equivalent of pressing Ctrl-G/⌘G in the editor, but groups the specified list of nodes rather than the current selection. You may still, of course, group the current selection by passing it as an argument:

```ts title="Group nodes"
figma.group(figma.currentPage.selection, parent)
```

Note: Why is there no `figma.createGroup()` function? It would create an empty group, and empty groups are not supported in Figma.

Note: Why do we require `figma.group(...)` to specify the parent, rather let you call `parent.appendChild(group)` separately? It allows you to create the new group while keeping all the grouped layers in the same absolute x/y locations. The method `.appendChild` preserves the *relative* position of a node, so if you use `.appendChild` to populate a group, you would need to do additional work to put them back in their original location if that was the desired behavior.

Since grouping involves moving nodes to a different parent, this operation is subject to many reparenting restrictions:

***

### importComponentByKeyAsync()

> **importComponentByKeyAsync**(`key`): `Promise`\<[`ComponentNode`](ComponentNode.md)\>

Defined in: figmaPluginTypes.ts:1532

Loads a component node from the team library. Promise is rejected if there is no published component with that key or if the request fails.

#### Parameters

##### key

`string`

#### Returns

`Promise`\<[`ComponentNode`](ComponentNode.md)\>

***

### importComponentSetByKeyAsync()

> **importComponentSetByKeyAsync**(`key`): `Promise`\<[`ComponentSetNode`](ComponentSetNode.md)\>

Defined in: figmaPluginTypes.ts:1536

Loads a component set node from the team library. Promise is rejected if there is no published component set with that key or if the request fails.

#### Parameters

##### key

`string`

#### Returns

`Promise`\<[`ComponentSetNode`](ComponentSetNode.md)\>

***

### importStyleByKeyAsync()

> **importStyleByKeyAsync**(`key`): `Promise`\<[`BaseStyle`](../type-aliases/BaseStyle.md)\>

Defined in: figmaPluginTypes.ts:1540

Loads a style from the team library. Promise is rejected if there is no style with that key or if the request fails.

#### Parameters

##### key

`string`

#### Returns

`Promise`\<[`BaseStyle`](../type-aliases/BaseStyle.md)\>

***

### intersect()

> **intersect**(`nodes`, `parent`, `index?`): [`BooleanOperationNode`](BooleanOperationNode.md)

Defined in: figmaPluginTypes.ts:1754

Creates a new [BooleanOperationNode](BooleanOperationNode.md) using the INTERSECT operation using the contents of `nodes`. The arguments to `union` are the same as in [PluginAPI.intersect](#intersect).

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

##### parent

[`BaseNode`](../type-aliases/BaseNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

##### index?

`number`

#### Returns

[`BooleanOperationNode`](BooleanOperationNode.md)

***

### listAvailableFontsAsync()

> **listAvailableFontsAsync**(): `Promise`\<[`Font`](Font.md)[]\>

Defined in: figmaPluginTypes.ts:1544

Returns the lists of currently available fonts. This should be the same list as the one you'd see if you manually used the font picker.

#### Returns

`Promise`\<[`Font`](Font.md)[]\>

***

### loadAllPagesAsync()

> **loadAllPagesAsync**(): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:1818

Loads all pages of the document into memory. This enables the use of the following features:

- The `documentchange` event for [PluginAPI.on](#on)
- [DocumentNode.findAll](DocumentNode.md#findall)
- [DocumentNode.findOne](DocumentNode.md#findone)
- [DocumentNode.findAllWithCriteria](DocumentNode.md#findallwithcriteria)
- [DocumentNode.findWidgetNodesByWidgetId](DocumentNode.md#findwidgetnodesbywidgetid)

Calling this method may be slow for large documents, and should be avoided unless absolutely necessary.

This method is only necessary if the plugin manifest contains `"documentAccess": "dynamic-page"`. Without this manifest setting, the full document is loaded automatically when the plugin or widget runs.

#### Returns

`Promise`\<`void`\>

***

### loadFontAsync()

> **loadFontAsync**(`fontName`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:1562

Makes a font available _in the plugin_ for use when creating and modifying text. Calling this function is **necessary** to modify any property of a text node that may cause the rendered text to change, including `.characters`, `.fontSize`, `.fontName`, etc.

You can either pass in a hardcoded font, a font loaded via `listAvailableFontsAsync`, or the font stored on an existing text node.

Read more about how to work with fonts, when to load them, and how to load them in the [Working with Text](https://www.figma.com/plugin-docs/working-with-text) page.

#### Parameters

##### fontName

[`FontName`](FontName.md)

#### Returns

`Promise`\<`void`\>

#### Remarks

This function only works to load fonts _already accessible in the Figma editor_ available to _plugins_. It does not load fonts from the internet.

Tip: to load multiple fonts at the same time, you may find [Promise.all](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all) helpful.

A common question is whether a plugin needs to be careful about calling `loadFontAsync(font)` for the same font multiple times. The answer is somewhat nuanced. The result of loading a font is cached, so calling `loadFontAsync` won't re-fetch the same font from disk. Therefore, calling `loadFontAsync` on every frame would be perfectly ok.

However, note that `loadFontAsync` returns a Promise. Even a Promise resolves immediately, it still needs to round-trip to the JavaScript event loop. So you probably shouldn't call `loadFontAsync` on the same font repeatedly inside a loop.

***

### moveLocalEffectFolderAfter()

> **moveLocalEffectFolderAfter**(`targetFolder`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1522

Note: This API is only available in Figma Design

Reorders a target folder after the specified reference folder (if provided) or to be first in the parent folder if reference is null. The target and reference folders must have the same parent folder. The target and reference folders must contain effect styles. When referring to nested folders, the full delimited folder name must be used. See the [BaseStyle](../type-aliases/BaseStyle.md) section for more info.

#### Parameters

##### targetFolder

`string`

##### reference

`null` | `string`

#### Returns

`void`

***

### moveLocalEffectStyleAfter()

> **moveLocalEffectStyleAfter**(`targetNode`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1498

Note: This API is only available in Figma Design

Reorders a target node after the specified reference node (if provided) or to be first if reference is null. The target and reference nodes must live in the same folder. The target and reference nodes must be local effect styles.

#### Parameters

##### targetNode

[`EffectStyle`](EffectStyle.md)

##### reference

`null` | [`EffectStyle`](EffectStyle.md)

#### Returns

`void`

***

### moveLocalGridFolderAfter()

> **moveLocalGridFolderAfter**(`targetFolder`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1528

Note: This API is only available in Figma Design

Reorders a target folder after the specified reference folder (if provided) or to be first in the parent folder if reference is null. The target and reference folders must have the same parent folder. The target and reference folders must contain grid styles. When referring to nested folders, the full delimited folder name must be used. See the [BaseStyle](../type-aliases/BaseStyle.md) section for more info.

#### Parameters

##### targetFolder

`string`

##### reference

`null` | `string`

#### Returns

`void`

***

### moveLocalGridStyleAfter()

> **moveLocalGridStyleAfter**(`targetNode`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1504

Note: This API is only available in Figma Design

Reorders a target node after the specified reference node (if provided) or to be first if reference is null. The target and reference nodes must live in the same folder. The target and reference nodes must be local grid styles.

#### Parameters

##### targetNode

[`GridStyle`](GridStyle.md)

##### reference

`null` | [`GridStyle`](GridStyle.md)

#### Returns

`void`

***

### moveLocalPaintFolderAfter()

> **moveLocalPaintFolderAfter**(`targetFolder`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1510

Note: This API is only available in Figma Design

Reorders a target folder after the specified reference folder (if provided) or to be first in the parent folder if reference is null. The target and reference folders must have the same parent folder. The target and reference folders must contain paint styles. When referring to nested folders, the full delimited folder name must be used. See the [BaseStyle](../type-aliases/BaseStyle.md) section for more info.

#### Parameters

##### targetFolder

`string`

##### reference

`null` | `string`

#### Returns

`void`

***

### moveLocalPaintStyleAfter()

> **moveLocalPaintStyleAfter**(`targetNode`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1486

Note: This API is only available in Figma Design

Reorders a target node after the specified reference node (if provided) or to be first if reference is null. The target and reference nodes must live in the same folder. The target and reference nodes must be local paint styles.

#### Parameters

##### targetNode

[`PaintStyle`](PaintStyle.md)

##### reference

`null` | [`PaintStyle`](PaintStyle.md)

#### Returns

`void`

***

### moveLocalTextFolderAfter()

> **moveLocalTextFolderAfter**(`targetFolder`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1516

Note: This API is only available in Figma Design

Reorders a target folder after the specified reference folder (if provided) or to be first in the parent folder if reference is null. The target and reference folders must have the same parent folder. The target and reference folders must contain text styles. When referring to nested folders, the full delimited folder name must be used. See the [BaseStyle](../type-aliases/BaseStyle.md) section for more info.

#### Parameters

##### targetFolder

`string`

##### reference

`null` | `string`

#### Returns

`void`

***

### moveLocalTextStyleAfter()

> **moveLocalTextStyleAfter**(`targetNode`, `reference`): `void`

Defined in: figmaPluginTypes.ts:1492

Note: This API is only available in Figma Design

Reorders a target node after the specified reference node (if provided) or to be first if reference is null. The target and reference nodes must live in the same folder. The target and reference nodes must be local text styles.

#### Parameters

##### targetNode

[`TextStyle`](TextStyle.md)

##### reference

`null` | [`TextStyle`](TextStyle.md)

#### Returns

`void`

***

### notify()

> **notify**(`message`, `options?`): [`NotificationHandler`](NotificationHandler.md)

Defined in: figmaPluginTypes.ts:276

Shows a notification on the bottom of the screen.

#### Parameters

##### message

`string`

The message to show. It is limited to 100 characters. Longer messages will be truncated.

##### options?

[`NotificationOptions`](NotificationOptions.md)

An optional argument with the following optional parameters:

```ts
interface NotificationOptions {
  timeout?: number;
  error?: boolean;
  onDequeue?: (reason: NotifyDequeueReason) => void
  button?: {
    text: string
    action: () => boolean | void
  }
}
```

- `timeout`: How long the notification stays up in milliseconds before closing. Defaults to 3 seconds when not specified. Set the timeout to `Infinity` to make the notification show indefinitely until the plugin is closed.
- `error`: If true, display the notification as an error message, with a different color.
- `onDequeue`: A function that will run when the notification is dequeued. This can happen due to the timeout being reached, the notification being dismissed by the user or Figma, or the user clicking the notification's `button`.
  - The function is passed a `NotifyDequeueReason`, which is defined as the following:
```ts
 type NotifyDequeueReason = 'timeout' | 'dismiss' | 'action_button_click'
 ```
- `button`: An object representing an action button that will be added to the notification.
   - `text`: The message to display on the action button.
   - `action`: The function to execute when the user clicks the button. If this function returns `false`, the message will remain when the button is clicked. Otherwise, clicking the action button dismisses the notify message.

#### Returns

[`NotificationHandler`](NotificationHandler.md)

#### Remarks

The `notify` API is a convenient way to show a message to the user. These messages can be queued.

If the message includes a custom action button, it will be closed automatically when the plugin closes.

Calling `figma.notify` returns a `NotificationHandler` object. This object contains a single `handler.cancel()` method that can be used to remove the notification before it times out by itself. This is useful if the notification becomes no longer relevant.

```ts
interface NotificationHandler {
  cancel: () => void
}
```

An alternative way to show a message to the user is to pass a message to the [PluginAPI.closePlugin](#closeplugin) function.

***

### off()

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:848

Removes a callback added with `figma.on` or `figma.once`.

##### Parameters

###### type

[`ArgFreeEventType`](../type-aliases/ArgFreeEventType.md)

###### callback

() => `void`

##### Returns

`void`

##### Remarks

The callback needs to be the same object that was originally added. For example, you can do this:

```ts title="Correct way to remove a callback"
let fn = () => { console.log("selectionchanged") }
figma.on("selectionchange", fn)
figma.off("selectionchange", fn)
```

whereas the following won't work, because the function objects are different:

```ts title="Incorrect way to remove a callback"
figma.on("selectionchange", () => { console.log("selectionchanged") })
figma.off("selectionchange", () => { console.log("selectionchanged") })
```

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:849

##### Parameters

###### type

`"run"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:850

##### Parameters

###### type

`"drop"`

###### callback

(`event`) => `boolean`

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:851

##### Parameters

###### type

`"documentchange"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:852

##### Parameters

###### type

`"slidesviewchange"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:853

##### Parameters

###### type

`"textreview"`

###### callback

(`event`) => [`TextReviewRange`](../type-aliases/TextReviewRange.md)[] \| `Promise`\<[`TextReviewRange`](../type-aliases/TextReviewRange.md)[]\>

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:857

##### Parameters

###### type

`"stylechange"`

###### callback

(`event`) => `void`

##### Returns

`void`

***

### on()

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:805

Registers an callback that will be called when an event happens in the editor. Current supported events are:
- The selection on the current page changed.
- The current page changed.
- The document has changed.
- An object from outside Figma is dropped onto the canvas
- The plugin has started running.
- The plugin closed.
- The plugin has started running.
- The timer has started running.
- The timer has paused.
- The timer has stopped.
- The timer is done.
- The timer has resumed.

##### Parameters

###### type

[`ArgFreeEventType`](../type-aliases/ArgFreeEventType.md)

A string identifying the type of event that the callback will be called on.

This is either an `ArgFreeEventType`, `run`, `drop`, or `documentchange`. The `run` event callback will be passed a `RunEvent`. The `drop` event callback will be passed a `DropEvent`. The `documentchange` event callback will be passed a `DocumentChangeEvent`.

```ts
type ArgFreeEventType =
  "selectionchange" |
  "currentpagechange" |
  "close" |
  "timerstart" |
  "timerstop" |
  "timerpause" |
  "timerresume" |
  "timeradjust" |
  "timerdone"
```

###### callback

() => `void`

A function that will be called when the event happens.
If `type` is 'run', then this function will be passed a `RunEvent`.
If `type` is 'drop', then this function will be passed a `DropEvent`.
If `type` is 'documentchange', then this function will be passed a `DocumentChangeEvent`.

Otherwise nothing will be passed in.

##### Returns

`void`

##### Remarks

This API tries to match Node.js conventions around similar `.on` APIs.

It's important to understand that the `.on` API runs the callbacks **asynchronously**. For example:

```ts
figma.on("selectionchange", () => { console.log("changed") })
console.log("before")
figma.currentPage.selection = []
console.log("after")

// Output:
// "before"
// "after"
// "changed"
```

The asynchronous nature of these APIs have a few other implications.

The callback will not necessarily be called each time the event happens. For example, this will only trigger the event once:

```ts
figma.currentPage.selection = [figma.createRectangle()]
figma.currentPage.selection = [figma.createFrame()]
```

Nor will the ordering of the event trigger and event registration affect whether the callback is called.

```ts
figma.currentPage.selection = [figma.createFrame()]
figma.on("selectionchange", () => { "this will get called!" })
```

## Available event types

### `"currentpagechange"`

This event will trigger when the user navigates to a different page, or when the plugin changes the value of `figma.currentPage`.

### `"selectionchange"`

This event will trigger when the selection of the **current page** changes. This can happen:
- By user action.
- Due to plugin code.
- When the current page changes (a `"currentpagechange"` event always triggers a `"selectionchange"` event).
- When a selected node is deleted.
- When a selected node becomes the child of another selected node (in which case it is considered indirectly selected, and is no longer in `figma.currentPage.selection`)

Note also that changing the selection via the plugin API, then changing it back to its previous value immediately still triggers the event.

### `"documentchange"`

If the plugin manifest contains `"documentAccess": "dynamic-page"`, you must first call [PluginAPI.loadAllPagesAsync](#loadallpagesasync) to access this event. Because this may introduce a loading delay, consider using more granular alternatives, such as the `"stylechange"` event, or using [PageNode.on](PageNode.md#on) with the `"nodechange"` event.

This event will trigger when a change is made to the currently open file. The event will be called when nodes/styles are either added, removed, or changed in a document.

The callback will be passed with a DocumentChangeEvent with the below interface:

```ts
interface DocumentChangeEvent {
  documentChanges: DocumentChange[]
}
```

Note: Note that `DocumentChangeEvent` has a `documentChanges` property with an array of `DocumentChange`s. Figma will not call the 'documentchange' callback synchronously and will instead batch the updates and send them to the callback periodically.

There are 6 different [DocumentChange](../type-aliases/DocumentChange.md) types that we currently notify on and we might add more in the future. Each of these changes has a `type` property to distinguish them:

| Change                                                           | `type` property           | Description                                                                                                                                                                                                        |
|------------------------------------------------------------------|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [`CreateChange`](https://www.figma.com/plugin-docs/api/DocumentChange#createchange)               | `'CREATE'`                | A node has been created in the document. If a node with nested children is being added to the document a `CreateChange` will only be made for the highest level parent that was added to the document.             |
| [`DeleteChange`](https://www.figma.com/plugin-docs/api/DocumentChange#deletechange)               | `'DELETE'`                | A node has been removed from the document. If a node with nested children is being removed from the document a  `DeleteChange`  will only be made for the highest level parent that was removed from the document. |
| [`PropertyChange`](https://www.figma.com/plugin-docs/api/DocumentChange#propertychange)           | `'PROPERTY_CHANGE'`       | A property of a node has changed.                                                                                                                                                                                  |
| [`StyleCreateChange`](https://www.figma.com/plugin-docs/api/DocumentChange#stylecreatechange)     | `'STYLE_CREATE'`          | A style has been added to the document.                                                                                                                                                                            |
| [`StyleDeleteChange`](https://www.figma.com/plugin-docs/api/DocumentChange#styledeletechange)     | `'STYLE_DELETE'`          | A style has been removed from the document.                                                                                                                                                                        |
| [`StylePropertyChange`](https://www.figma.com/plugin-docs/api/DocumentChange#stylepropertychange) | `'STYLE_PROPERTY_CHANGE'` | A style has had a property changed.                                                                                                                                                                                |

#### Special cases

We currently never notify a `'documentchange'` listener in the following scenarios:
- if the change was caused directly by your plugin in a `documentchange` callback
- if an instance sublayer was updated by a change to a main component
- if a node was updated as a result of a style changing

#### Example
Here is an example of exhaustively checking changes to the document and logging them to the console.

```ts
figma.on("documentchange", (event) => {
for (const change of event.documentChanges) {
  switch (change.type) {
    case "CREATE":
      console.log(
        `Node ${change.id} created by a ${change.origin.toLowerCase()} user`
      );
      break;

    case "DELETE":
      console.log(
        `Node ${change.id} deleted by a ${change.origin.toLowerCase()} user`
      );
      break;

    case "PROPERTY_CHANGE":
      for (const prop of change.properties) {
        console.log(
          `Node ${
            change.id
          } had ${prop} changed by a ${change.origin.toLowerCase()} user`
        );
      }
      break;

    case "STYLE_CREATE":
      console.log(
        `Style ${change.id} created by a ${change.origin.toLowerCase()} user`
      );
      break;

    case "STYLE_DELETE":
      console.log(
        `Style ${change.id} deleted by a ${change.origin.toLowerCase()} user`
      );
      break;

     case "STYLE_PROPERTY_CHANGE":
       for (const prop of change.properties) {
         console.log(
            `Style ${
              change.id
            } had ${prop} changed by a ${change.origin.toLowerCase()} user`
          );
       }
       break;
    }
  }
});
```

For a more involved example see our [plugin samples on GitHub](https://github.com/figma/plugin-samples/tree/master/document-change).

### `"textreview"`

Note: This event is only available to plugins that have the `"textreview"` capability in their `manifest.json` and the plugin is running in text review mode.

`"textreview"` events allow plugins to review text in a document and act as either a replacement or a supplement to native spell check.

This event is triggered periodically when the user is typing in a text node. The callback will be passed with a TextReviewEvent with the below interface:
```ts
interface TextReviewEvent {
  text: string
}
```

The `text` property is the text that the user has currently typed into the node.

A `"textreview"` event listener should return a promise that resolves to an array of `TextReviewRange` objects. Each `TextReviewRange` object represents a single range of text that should be marked as either an error or a suggestion. The `TextReviewRange` interface is defined as:
```ts
type TextReviewRange = {
  start: number
  end: number
  suggestions: string[]
  color?: 'RED' | 'GREEN' | 'BLUE'
}
```

The `start` property is the index of the first character in the range. The `end` property is the index of the last character in the range. The `suggestions` property is an array of strings that represent the suggestions for the range. The `color` property is optional and can be used to change the color of the underline that is drawn under the range. If no color is specified the underline will be red.

For more information read our in depth guide on [text review plugins](https://www.figma.com/plugin-docs/textreview-plugins).

### `"drop"`

This event will trigger when objects outside Figma (such as elements from other browser windows, or files from the local filesystem) are dropped onto the canvas.

It can also be triggered by a special `pluginDrop` message sent from the UI. See the [Triggering drop events from the UI](https://www.figma.com/plugin-docs/creating-ui#triggering-drop-events-from-the-ui) section for more details.

The callback will be passed a `DropEvent` with the below interface. It should return `false` if it wants to handle the particular drop and stop Figma from performing the default drop behavior.
```ts
interface DropEvent {
  node: BaseNode | SceneNode
  x: number
  y: number
  absoluteX: number
  absoluteY: number
  items: DropItem[]
  files: DropFile[]
  dropMetadata?: any
}
```

- The `node` property contains the node where the drop landed. This will sometimes be the page node if the drop didn't land on anything in the canvas, or if target node is locked or cannot be a parent of another node.
- The `x` and `y` properties are coordinates relative to the node drop target
- The `absoluteX` and `absoluteY` properties are absolute canvas coordinates
- The `items` property is an array of `DropItem` objects. You will see multiple objects if a drop contains multiple, non-file data types. If there are no data items, this array will be empty.
- The `files` property is an array of dropped files represented as `DropFile` objects. If no files are present, this array will be empty.
- The `dropMetadata` property comes from drop events [explicitly triggered by the UI](https://www.figma.com/plugin-docs/creating-ui#triggering-drop-events-from-the-ui).

Items and files will conform to the below interfaces:

```ts
interface DropItem {
  type: string // e.g. "text/html", "text/uri-list", etc...
  data: string
}

interface DropFile {
  name: string // file name
  type: string // e.g. "image/png"
  getBytesAsync(): Promise<Uint8Array> // get raw file bytes
  getTextAsync(): Promise<string> // get text assuming file is UTF8-encoded
}
```

See the Icon Drag-and-Drop and PNG Crop examples in the [figma/plugin-samples](https://github.com/figma/plugin-samples) repository for plugins that implement this API.

#### UI Recommendations

When the plugin registers a drop callback, it should give the user instructions with either text in the plugin UI or [`figma.notify()`](https://www.figma.com/plugin-docs/api/properties/figma-notify) (if the plugin does not show a UI) telling them what to do.

[`figma.notify()`](https://www.figma.com/plugin-docs/api/properties/figma-notify) can be called with the `timeout` option set to `Infinity` to make the notification show for as long as the plugin is open.

### `"close"`

This event will trigger when the plugin is about to close, either from a call to `figma.closePlugin()` or the user closing the plugin via the UI.

This is a good place to run cleanup actions. For example, some plugins add UI elements in the canvas by creating nodes. These UI elements should be deleted when the plugin is closed. Note that you don't need to call `figma.closePlugin()` again in this function.

**You should use this API only if strictly necessary, and run as little code as possible in the callback when doing so**. When a user closes a plugin, they expect it to be closed immediately. Having long-running actions in the closing callback prevents the plugin for closing promptly.

This is also not the place to run any asynchronous actions (e.g. register callbacks, using `await`, etc). The plugin execution environment will be destroyed immediately when all the callbacks have returned, and further callbacks will not be called.

### `"run"`

This event is triggered when a plugin is run. For plugins with parameters, this happens after all parameters have been enter by the user in the quick action UI. For all other plugins this happens immediately after launch.

The callback will be passed a `RunEvent` that looks like:
```ts
interface RunEvent {
  parameters?: ParameterValues
  command: string
}
```

- The `parameters` property is of type [`ParameterValues`](https://www.figma.com/plugin-docs/api/figma-parameters#parametervalues), and contains the value entered for each parameter.
- The `command` argument is the same as [`figma.command`](https://www.figma.com/plugin-docs/api/figma#command), but provided here again for convenience.

Handling the `run` event is only required for plugins with parameters. For all plugins it can still be a convenient spot to put your top level code, since it is called
on every plugin run.

### `"stylechange"`

Triggered when any styles in the document change.

The callback will receive a StyleChangeEvent with the below interface:

```ts
interface StyleChangeEvent {
  styleChanges: StyleChange[]
}
```

There are 3 different [StyleChange](../type-aliases/StyleChange.md) types. Each of these changes has a `type` property to distinguish them:

| Change | `type` property | Description |
| --- | --- | --- |
| [`StyleCreateChange`](https://www.figma.com/plugin-docs/api/StyleChange#stylecreatechange) | `'STYLE_CREATE'` | A style has been added to the document. |
| [`StyleDeleteChange`](https://www.figma.com/plugin-docs/api/StyleChange#styledeletechange) | `'STYLE_DELETE'` | A style has been removed from the document. |
| [`StylePropertyChange`](https://www.figma.com/plugin-docs/api/StyleChange#stylepropertychange) | `'STYLE_PROPERTY_CHANGE'` | A style has had a property changed. |

### `"timerstart"`

This event will trigger when somebody starts a timer in the document. This can happen either by a user (either the current user or a multiplayer user) starting the timer from the UI, or triggered by plugin code. To inspect the current state of the timer when this event fires, use the `figma.timer` interface. For example:
```ts
figma.on("timerstart", () => console.log(figma.timer.remaining))
figma.timer.start(300)

// Output:
// 300
```

### `"timerpause"`

Triggered when a timer that is running is paused.

### `"timerstop"`

Triggered when the timer is stopped.

### `"timerdone"`

Triggered when the timer is running and reaches 0 time remaining.

### `"timerresume"`

Triggered when a timer that is paused is resumed.

### `"timeradjust"`

Triggered when the total time on the timer changes. From the UI, it is only possible to add time to the timer. However, plugin code can both add and remove time from a running timer.

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:806

##### Parameters

###### type

`"run"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:807

##### Parameters

###### type

`"drop"`

###### callback

(`event`) => `boolean`

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:808

##### Parameters

###### type

`"documentchange"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:809

##### Parameters

###### type

`"slidesviewchange"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:810

##### Parameters

###### type

`"textreview"`

###### callback

(`event`) => [`TextReviewRange`](../type-aliases/TextReviewRange.md)[] \| `Promise`\<[`TextReviewRange`](../type-aliases/TextReviewRange.md)[]\>

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:814

##### Parameters

###### type

`"stylechange"`

###### callback

(`event`) => `void`

##### Returns

`void`

***

### once()

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:818

Same as `figma.on`, but the callback will only be called once, the first time the specified event happens.

##### Parameters

###### type

[`ArgFreeEventType`](../type-aliases/ArgFreeEventType.md)

###### callback

() => `void`

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:819

##### Parameters

###### type

`"run"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:820

##### Parameters

###### type

`"drop"`

###### callback

(`event`) => `boolean`

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:821

##### Parameters

###### type

`"documentchange"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:822

##### Parameters

###### type

`"slidesviewchange"`

###### callback

(`event`) => `void`

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:823

##### Parameters

###### type

`"textreview"`

###### callback

(`event`) => [`TextReviewRange`](../type-aliases/TextReviewRange.md)[] \| `Promise`\<[`TextReviewRange`](../type-aliases/TextReviewRange.md)[]\>

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:827

##### Parameters

###### type

`"stylechange"`

###### callback

(`event`) => `void`

##### Returns

`void`

***

### openExternal()

> **openExternal**(`url`): `void`

Defined in: figmaPluginTypes.ts:351

Open a url in a new tab.

#### Parameters

##### url

`string`

#### Returns

`void`

#### Remarks

In the VS Code Extension, this API is required to open a url in the browser. Read more in [Dev Mode plugins in Visual Studio Code](https://www.figma.com/plugin-docs/working-in-dev-mode/#dev-mode-plugins-in-visual-studio-code).

***

### saveVersionHistoryAsync()

> **saveVersionHistoryAsync**(`title`, `description?`): `Promise`\<[`VersionHistoryResult`](VersionHistoryResult.md)\>

Defined in: figmaPluginTypes.ts:343

Saves a new version of the file and adds it to the version history of the file. Returns the new version id.

#### Parameters

##### title

`string`

The title of the version. This must be a non-empty string.

##### description?

`string`

An optional argument to describe the version.

Calling `saveVersionHistoryAsync` returns a promise that resolves to `null` or an instance of `VersionHistoryResult`:

```ts
interface VersionHistoryResult {
  id: string
}
```

- `id`: The version id of this newly saved version.

#### Returns

`Promise`\<[`VersionHistoryResult`](VersionHistoryResult.md)\>

#### Remarks

It is not guaranteed that all changes made before this method is used will be saved to version history.
For example,
 ```ts title="Changes may not all be saved"
 async function example() {
   await figma.createRectangle();
   await figma.saveVersionHistoryAsync('v1');
   figma.closePlugin();
 }
 example().catch((e) => figma.closePluginWithFailure(e))
 ```
The newly created rectangle may not be included in the v1 version. As a work around, you can wait before calling `saveVersionHistoryAsync()`. For example,
 ```ts title="Wait to save"
 async function example() {
   await figma.createRectangle();
   await new Promise(r => setTimeout(r, 1000)); // wait for 1 second
   await figma.saveVersionHistoryAsync('v1');
   figma.closePlugin();
 }
```
Typically, manual changes that precede the execution of `saveVersionHistoryAsync()` will be included. If you want to use `saveVersionHistoryAsync()` before the plugin makes
additional changes, make sure to use the method with an async/await or a Promise.

***

### setCurrentPageAsync()

> **setCurrentPageAsync**(`page`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:462

Switch the active page to the specified [PageNode](PageNode.md).

#### Parameters

##### page

[`PageNode`](PageNode.md)

#### Returns

`Promise`\<`void`\>

***

### setFileThumbnailNodeAsync()

> **setFileThumbnailNodeAsync**(`node`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:1802

Set `node` to be the thumbnail for the file. If `node` is null, then use the default thumbnail.

#### Parameters

##### node

`null` | [`FrameNode`](FrameNode.md) | [`ComponentSetNode`](ComponentSetNode.md) | [`ComponentNode`](ComponentNode.md) | [`SectionNode`](SectionNode.md)

#### Returns

`Promise`\<`void`\>

***

### setSlideGrid()

> **setSlideGrid**(`slideGrid`): `void`

Defined in: figmaPluginTypes.ts:1865

Note: This API is only available in Figma Slides

#### Parameters

##### slideGrid

[`SlideNode`](SlideNode.md)[][]

#### Returns

`void`

#### Remarks

The order of Slides within a presentation is a key part of updating and editing a deck.
Using this method you can manipulate and reorder the grid.

For example:

```ts
const grid = figma.getSlideGrid()
const [firstRow, ...rest] = grid

// move the first row to the end
figma.setSlideGrid([...rest, firstRow])
```

So long as all the Slides in the current grid are passed back to `setSlideGrid` the update will succeed.
Meaning, you can change the amount of rows as you please - flatten all to one row, explode to many rows, etc, and the method will handle all updates for you.

***

### showUI()

> **showUI**(`html`, `options?`): `void`

Defined in: figmaPluginTypes.ts:388

Enables you to render UI to interact with the user, or simply to access browser APIs. This function creates a modal dialog with an `<iframe>` containing the HTML markup in the `html` argument.

#### Parameters

##### html

`string`

The HTML to insert into the iframe. You can pass in the HTML code as a string here, but this will often be the global value [`__html__`](https://www.figma.com/plugin-docs/api/global-objects#html).

##### options?

[`ShowUIOptions`](ShowUIOptions.md)

An object that may contain the following optional parameters:
- `visible`: Whether the UI starts out displayed to the user. Defaults to `true`. You can use `figma.ui.show()` and `figma.ui.hide()` to change the visibility later.
- `width`: The width of the UI. Defaults to 300. Minimum is 70. Can be changed later using `figma.ui.resize(width, height)`
- `height`: The height of the UI. Defaults to 200. Minimum is 0. Can be changed later using `figma.ui.resize(width, height)`
- `title`: The title of the UI window. Defaults to the plugin name.
- `position`: The position of the UI window. Defaults to the last position of the iframe or the center of the viewport. If specified, expects an X/Y coordinate in the canvas space (i.e matches x/y values returned by `<PluginNode>.x` and `<PluginNode>.y`)
- `themeColors`: Defaults to `false`. When enabled, CSS variables will be added to the plugin iframe to allow [support for light and dark themes](https://www.figma.com/plugin-docs/css-variables).

Note: If the position specified is outside of the user's viewport, the iframe will be moved so that it remains in the user's viewport.

#### Returns

`void`

#### Remarks

The easiest way to use this API is to load the HTML file defined in the manifest. This enables writing a separate HTML file which can be accessed through the [`__html__`](https://www.figma.com/plugin-docs/api/global-objects#html) global variable.

If the `<iframe>` UI is already showing when this function is called, the previous UI will be closed before the new one is displayed.

## Usage Examples

```js title="Example usage"
figma.showUI(
  "<b>Hello from Figma</b>",
  { width: 400, height: 200, title: "My title" }
)

figma.showUI(
  "<b>Hello from Figma</b>",
  { width: 400, height: 200, title: "My title", position: { x: 100, y: 100 } }
)

figma.showUI(__html__)
```

***

### subtract()

> **subtract**(`nodes`, `parent`, `index?`): [`BooleanOperationNode`](BooleanOperationNode.md)

Defined in: figmaPluginTypes.ts:1746

Creates a new [BooleanOperationNode](BooleanOperationNode.md) using the SUBTRACT operation using the contents of `nodes`. The arguments to `union` are the same as in [PluginAPI.subtract](#subtract).

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

##### parent

[`BaseNode`](../type-aliases/BaseNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

##### index?

`number`

#### Returns

[`BooleanOperationNode`](BooleanOperationNode.md)

***

### triggerUndo()

> **triggerUndo**(): `void`

Defined in: figmaPluginTypes.ts:303

Triggers an undo action. Reverts to the last `commitUndo()` state.

#### Returns

`void`

***

### ungroup()

> **ungroup**(`node`): [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:1778

Ungroups the given `node`, moving all of `node`'s children into `node`'s parent and removing `node`. Returns an array of nodes that were children of `node`.

#### Parameters

##### node

[`SceneNode`](../type-aliases/SceneNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

The node to ungroup.

#### Returns

[`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

This API is roughly the equivalent of pressing Ctrl-Shift-G/⌘⇧G in the editor, but ungroups the given node rather than all nodes in the current selection.

If the ungrouped node is part of the current selection, the ungrouped node's children will become part of the selection. Otherwise the selection is unchanged.

***

### union()

> **union**(`nodes`, `parent`, `index?`): [`BooleanOperationNode`](BooleanOperationNode.md)

Defined in: figmaPluginTypes.ts:1738

Creates a new [BooleanOperationNode](BooleanOperationNode.md) using the UNION operation using the contents of `nodes`. The arguments to `union` are the same as in [PluginAPI.group](#group).

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

##### parent

[`BaseNode`](../type-aliases/BaseNode.md) & [`ChildrenMixin`](ChildrenMixin.md)

##### index?

`number`

#### Returns

[`BooleanOperationNode`](BooleanOperationNode.md)
