---

SuggestionResults

# Interface: SuggestionResults

Defined in: figmaPluginTypes.ts:2862

## See

https://www.figma.com/plugin-docs/api/figma-parameters

## Methods

### setError()

> **setError**(`message`): `void`

Defined in: figmaPluginTypes.ts:2938

Displays an error message to the user instead of a list of autocomplete suggestions. When this function
is called, the user is prevented from moving on to the next parameter without first changing the input
for the current parameter.

This is useful to signal to the user that they have entered an invalid value and provide them
instruction for how to correct the input.

You can also use this as a way to validate pre-conditions, like current selection, or some state of the
current document. To do this, in the 'input' event handler for the first parameter key, check the that
all pre-conditions are fulfilled and call `setError` with an appropriate error message if they are not,
unconditionally of what the current `query` value is.

This function is _not_ available on parameters with `allowFreeform` set. The purpose of `allowFreeform`
is to allow users to enter arbitrary values and so Figma doesn't guarantee that the plugin gets an
opportunity to handle an input event and call `setError` before the user moves on to the next parameter.

If you want to generally allow freeform input, but still retain the ability to call `setError`, you can
remove `allowFreeform` and manually add a autocomplete entry containing the current `query` string. I.e.
make the first item in the array passed to `setSuggestions` simply be the string in `query`.

For a full example of what this can look like, see the [Resizer sample plugin](https://github.com/figma/plugin-samples/blob/master/resizer/code.ts)

#### Parameters

##### message

`string`

#### Returns

`void`

---

### setLoadingMessage()

> **setLoadingMessage**(`message`): `void`

Defined in: figmaPluginTypes.ts:2946

Modify the default "Loading Suggestions..." message displayed until the plugin calls `setSuggestions`.
This can be useful if your plugin needs to load autocomplete messages from the network, or if you need
to perform lengthy calculations.

You can call `setLoadingMessage` multiple times in order to provide an updated message.

#### Parameters

##### message

`string`

#### Returns

`void`

---

### setSuggestions()

> **setSuggestions**(`suggestions`): `void`

Defined in: figmaPluginTypes.ts:2904

Sets the list of autocomplete suggestions to be displayed in the quick action UI.

If you only want to provide a string suggestion, and don't need metadata or icons, you can use
an array of simple string values. For example

```ts title="Simple string suggestions"
figma.parameters.on("input", ({ query, result }) => {
  result.setSuggestions(
    ["Armadillo", "Baboon", "Cacatua", "Dolphin"].filter((s) =>
      s.includes(query)
    )
  );
});
```

However the API also allows providing more information with each suggestion:

- The text to display to the user
- An icon (optional)
- Hidden metadata which is passed back to the plugin if the user chooses this suggestion (optional)

Example

```ts title="Suggestions with icons and data"
result.setSuggestions([
  { name: node1.name, data: node1.id, icon: node1Preview },
  { name: node2.name, data: node2.id, icon: node2Preview },
  ...
])
```

The `name` property contains the text to display to the user in the autocomplete suggestions. This
property is required.

The `data` property allows associating hidden metadata with a given autocomplete suggestion.
This data is passed back to the plugin as the parameter's value if the user chooses this option.
If no `data` property is provided, it defaults to the value of the `name` property. I.e. the value
of the parameter will be the string that was displayed to the user.

An icon can be provided through a `icon` or `iconUrl` property. The `icon` property can contain
either a raster image in the form of a `Uint8Array`, or an SVG image in the form of a string. You
can alternatively use the `iconUrl` property to provide a URL to the image. Note that for this to
work the target server has to support CORS.

#### Parameters

##### suggestions

(`string` \| \{ `data?`: `any`; `icon?`: `string` \| `Uint8Array`\<`ArrayBufferLike`\>; `iconUrl?`: `string`; `name`: `string`; \})[]

#### Returns

`void`
