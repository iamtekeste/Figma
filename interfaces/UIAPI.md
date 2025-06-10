---

UIAPI

# Interface: UIAPI

Defined in: figmaPluginTypes.ts:2290

## See

https://www.figma.com/plugin-docs/api/figma-ui

## Properties

### onmessage

> **onmessage**: `undefined` \| [`MessageEventHandler`](../type-aliases/MessageEventHandler.md)

Defined in: figmaPluginTypes.ts:2347

Register a handler for incoming messages from the UI's `<iframe>` window.

#### Param

```ts
type MessageEventHandler = (
  pluginMessage: any,
  props: OnMessageProperties
) => void;

interface OnMessageProperties {
  origin: string;
}
```

#### Remarks

The `pluginMessage` argument contains the message passed by the call to `postMessage` on the UI side.

The `props` argument contains a `origin` property contains the origin of the document that sent the message. It is an advanced feature, mainly used for implementing OAuth.

## Methods

### close()

> **close**(): `void`

Defined in: figmaPluginTypes.ts:2310

Destroys the UI and its containing `<iframe>`. Once this has been called, the code inside the iframe will be stopped and you can no longer send messages to and from it.

#### Returns

`void`

---

### hide()

> **hide**(): `void`

Defined in: figmaPluginTypes.ts:2298

Hides the current UI. The UI will still continue to run code and be able to send and receive messages. However, it is not rendered to the user.

#### Returns

`void`

---

### off()

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2365

Removes a handler added via `figma.ui.on`.

#### Parameters

##### type

`"message"`

##### callback

[`MessageEventHandler`](../type-aliases/MessageEventHandler.md)

#### Returns

`void`

---

### on()

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2357

Register a handler for incoming messages from the UI's `<iframe>` window.

#### Parameters

##### type

`"message"`

##### callback

[`MessageEventHandler`](../type-aliases/MessageEventHandler.md)

#### Returns

`void`

#### Remarks

The `pluginMessage` argument contains the message passed by the call to `postMessage` on the UI side.

The `props` argument contains a `origin` property contains the origin of the document that sent the message. It is an advanced feature, mainly used for implementing OAuth.

---

### once()

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2361

Register a handler for incoming messages from the UI's `<iframe>` window. Same as `figma.ui.on("message")`, but only gets called the first time.

#### Parameters

##### type

`"message"`

##### callback

[`MessageEventHandler`](../type-aliases/MessageEventHandler.md)

#### Returns

`void`

---

### postMessage()

> **postMessage**(`pluginMessage`, `options?`): `void`

Defined in: figmaPluginTypes.ts:2327

Sends a message to the UI's `<iframe>` window.

#### Parameters

##### pluginMessage

`any`

This can be almost any data type or plain object, as long as it's a serializable object.

This is similar to saying that it should be possible to send the object over a network if it were necessary. You can send objects, arrays, numbers, strings, booleans, null, undefined, Date objects and Uint8Array objects. However, functions and prototype chains of objects will not be sent.

These restrictions are the same as the browser's `postMessage`: [click here](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm) for more details.

##### options?

[`UIPostMessageOptions`](UIPostMessageOptions.md)

An object that may contain the following optional parameters:

- `origin`: An advanced option, mainly used for implementing OAuth. If the `origin` option is provided, the message will only be delivered to the iframe if the origin of the document inside the iframe matches the `origin`. This defaults to `'*'`, which allows the message to be passed to any document.

#### Returns

`void`

#### Remarks

Read more about how to use this API in the [Creating a User Interface](https://www.figma.com/plugin-docs/creating-ui) tutorial.

---

### reposition()

> **reposition**(`x`, `y`): `void`

Defined in: figmaPluginTypes.ts:2306

Changes the position of the UI, after it has been created. Note that the position can also be set in the initial options.

#### Parameters

##### x

`number`

##### y

`number`

#### Returns

`void`

---

### resize()

> **resize**(`width`, `height`): `void`

Defined in: figmaPluginTypes.ts:2302

Changes the size of the UI, after it has been created. Note that the size can also be set in the initial options. The minimum size is 70x0.

#### Parameters

##### width

`number`

##### height

`number`

#### Returns

`void`

---

### show()

> **show**(): `void`

Defined in: figmaPluginTypes.ts:2294

Makes the plugin's UI visible. Use this to show the UI if it was created using `figma.showUI(..., { visible: false })`, or after a call to `figma.ui.hide()`.

#### Returns

`void`
