---

DevResourcesAPI

# Interface: DevResourcesAPI

Defined in: figmaPluginTypes.ts:2716

## See

https://www.figma.com/plugin-docs/api/N/A

## Methods

### off()

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2738

Remove a handler for the linkpreview, auth, and open events.

##### Parameters

###### type

`"linkpreview"`

###### callback

(`event`) => [`LinkPreviewResult`](../type-aliases/LinkPreviewResult.md) \| `Promise`\<[`LinkPreviewResult`](../type-aliases/LinkPreviewResult.md)\>

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2742

##### Parameters

###### type

`"auth"`

###### callback

(`event`) => [`AuthResult`](../type-aliases/AuthResult.md) \| `Promise`\<[`AuthResult`](../type-aliases/AuthResult.md)\>

##### Returns

`void`

#### Call Signature

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2743

##### Parameters

###### type

`"open"`

###### callback

(`event`) => `void`

##### Returns

`void`

---

### on()

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2720

Create a handler for when the linkpreview, auth, and open events are triggered.

##### Parameters

###### type

`"linkpreview"`

###### callback

(`event`) => [`LinkPreviewResult`](../type-aliases/LinkPreviewResult.md) \| `Promise`\<[`LinkPreviewResult`](../type-aliases/LinkPreviewResult.md)\>

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2724

##### Parameters

###### type

`"auth"`

###### callback

(`event`) => [`AuthResult`](../type-aliases/AuthResult.md) \| `Promise`\<[`AuthResult`](../type-aliases/AuthResult.md)\>

##### Returns

`void`

#### Call Signature

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2725

##### Parameters

###### type

`"open"`

###### callback

(`event`) => `void`

##### Returns

`void`

---

### once()

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2729

Create a handler for when the linkpreview, auth, and open events are first triggered. This only gets called once.

##### Parameters

###### type

`"linkpreview"`

###### callback

(`event`) => [`LinkPreviewResult`](../type-aliases/LinkPreviewResult.md) \| `Promise`\<[`LinkPreviewResult`](../type-aliases/LinkPreviewResult.md)\>

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2733

##### Parameters

###### type

`"auth"`

###### callback

(`event`) => [`AuthResult`](../type-aliases/AuthResult.md) \| `Promise`\<[`AuthResult`](../type-aliases/AuthResult.md)\>

##### Returns

`void`

#### Call Signature

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2734

##### Parameters

###### type

`"open"`

###### callback

(`event`) => `void`

##### Returns

`void`
