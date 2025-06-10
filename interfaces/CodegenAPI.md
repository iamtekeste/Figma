---

CodegenAPI

# Interface: CodegenAPI

Defined in: figmaPluginTypes.ts:2550

## See

https://www.figma.com/plugin-docs/api/figma-codegen

## Properties

### preferences

> `readonly` **preferences**: [`CodegenPreferences`](../type-aliases/CodegenPreferences.md)

Defined in: figmaPluginTypes.ts:2629

Read the current preferences as specified by the user.

```ts
type CodegenPreferences = {
  readonly unit: "PIXEL" | "SCALED";
  readonly scaleFactor?: number;
  // An object for every "select" item and their currently
  // selected values. The format of this is "select" item
  // propertyName => selectedOption.value.
  readonly customSettings: Record<string, string>;
};
```

---

### refresh()

> **refresh**: () => `void`

Defined in: figmaPluginTypes.ts:2635

Triggers the `figma.codegen.on("generate")` callback again.

This is is useful for plugins that need to refresh the codegen output. For example, if you’re using an iframe to provide more customization options.

#### Returns

`void`

## Methods

### off()

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2610

Removes a callback added by [\`figma.codegen.on\`](#on) or [\`figma.codegen.once\`](#once).

##### Parameters

###### type

`"generate"`

###### callback

(`event`) => [`CodegenResult`](../type-aliases/CodegenResult.md)[] \| `Promise`\<[`CodegenResult`](../type-aliases/CodegenResult.md)[]\>

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2614

##### Parameters

###### type

`"preferenceschange"`

###### callback

(`event`) => `Promise`\<`void`\>

##### Returns

`void`

---

### on()

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2594

A plugin for code generation needs to call `figma.codegen.on('generate')` to register a callback
that will be called when a user's selection changes in Dev Mode. This callback
should return an array of JSON objects that represent the sections in the
Inspect panel. The callback has a 15 second timeout and returns an error if it times out. For more
information, see the remarks.

##### Parameters

###### type

`"generate"`

The type of event to add the callback for: 'generate' or 'preferenceschange'.

###### callback

(`event`) => [`CodegenResult`](../type-aliases/CodegenResult.md)[] \| `Promise`\<[`CodegenResult`](../type-aliases/CodegenResult.md)[]\>

The callback that is called when the event is triggered.

##### Returns

`void`

##### Remarks

This callback can be async if your plugin needs to do some data fetching or other async
operation to generate code.

Note: `figma.showUI` is not allowed within the generate callback. Instead, if [`figma.showUI`](https://www.figma.com/plugin-docs/api/properties/figma-showui/) is required in the generate callback, the `showUI` call should be moved outside of the callback and [`figma.ui.postMessage`](https://www.figma.com/plugin-docs/api/properties/figma-ui-postmessage) should be used within the callback instead. This ensures that the plugin is able to handle concurrent "generate" events.

A plugin can also register a callback to handle events when codegen preferences are modified.
This is useful for codegenPreferences that need to open an iframe to get more user input.

Note: Only preferences with `itemType: "action"` will trigger the `"preferenceschange"`` callback.

The callback has a 15 second timeout. If the callback registered by `figma.codegen.on('generate')`
doesn't return a value within 15 seconds (for example, if the array of JSON objects takes too long to
construct), the operation ends and an error message is sent to the console:

```text title="Callback timeout error"
code generation timed out after 15 seconds
```

Additionally, a notification appears in the Code section of the Inspect panel to alert the
plugin's user of the error:

```text title="Inspect panel timeout error"
<Plugin name> ran into an issue

This plugin is created by a third party and not
maintained by Figma, so to give feedback please
reach out to the developer.
```

The error in the Inspect panel includes a link to your plugin's community page.

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2598

##### Parameters

###### type

`"preferenceschange"`

###### callback

(`event`) => `Promise`\<`void`\>

##### Returns

`void`

---

### once()

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2602

Same as [\`figma.codegen.on\`](#on), but the callback only gets called the first time.

##### Parameters

###### type

`"generate"`

###### callback

(`event`) => [`CodegenResult`](../type-aliases/CodegenResult.md)[] \| `Promise`\<[`CodegenResult`](../type-aliases/CodegenResult.md)[]\>

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2606

##### Parameters

###### type

`"preferenceschange"`

###### callback

(`event`) => `Promise`\<`void`\>

##### Returns

`void`
