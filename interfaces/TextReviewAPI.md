---

TextReviewAPI

# Interface: TextReviewAPI

Defined in: figmaPluginTypes.ts:2834

## See

https://www.figma.com/plugin-docs/api/figma-textreview

## Properties

### isEnabled

> `readonly` **isEnabled**: `boolean`

Defined in: figmaPluginTypes.ts:2851

This property is a readonly boolean that can be used to check if your plugin is enabled as a text review plugin for the user. It will be true if the plugin is enabled, and false if the plugin is disabled.

## Methods

### requestToBeDisabledAsync()

> **requestToBeDisabledAsync**(): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:2847

This method will disable the plugin as a text review plugin if it is enabled. The promise will resolve if it has been successfully been disabled and reject if it wasn’t enabled in the first place.

#### Returns

`Promise`\<`void`\>

---

### requestToBeEnabledAsync()

> **requestToBeEnabledAsync**(): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:2843

This method will request your plugin to be enabled as a text review plugin for the user.
A modal will pop up that will ask the user if they want to enable the plugin for text review.
The promise returned by the function will be resolved if the user accepts in the dialog and will be rejected if the user cancels.
Note that to prevent spam the promise will be auto rejected if the user cancels the request multiple times in a given plugin run.

![Dialog box that shows when you call the function](https://static.figma.com/uploads/ee33919763431eb2520074650fddfaa904c7e9c1)

#### Returns

`Promise`\<`void`\>
