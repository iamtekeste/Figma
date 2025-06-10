---

ClientStorageAPI

# Interface: ClientStorageAPI

Defined in: figmaPluginTypes.ts:2217

## See

https://www.figma.com/plugin-docs/api/figma-clientStorage

## Methods

### deleteAsync()

> **deleteAsync**(`key`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:2229

Removes the stored key/value pair from client storage with the given `key`. If no such key is stored, this function will return normally but will otherwise do nothing.

#### Parameters

##### key

`string`

#### Returns

`Promise`\<`void`\>

---

### getAsync()

> **getAsync**(`key`): `Promise`\<`any`\>

Defined in: figmaPluginTypes.ts:2221

Retrieves a value from client storage with the given `key`. If no value has been stored for that key, this function will asynchronously return `undefined`.

#### Parameters

##### key

`string`

#### Returns

`Promise`\<`any`\>

---

### keysAsync()

> **keysAsync**(): `Promise`\<`string`[]\>

Defined in: figmaPluginTypes.ts:2233

Retrieves a list of all keys stored to client storage. Use this to enumerate the full contents of the clientStorage API.

#### Returns

`Promise`\<`string`[]\>

---

### setAsync()

> **setAsync**(`key`, `value`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:2225

Sets a value to client storage with the given `key`. The returned promise will resolve if storage is successful, or reject with an error message if storage failed.

#### Parameters

##### key

`string`

##### value

`any`

#### Returns

`Promise`\<`void`\>
