---

NotificationOptions

# Interface: NotificationOptions

Defined in: figmaPluginTypes.ts:2238

## See

https://www.figma.com/plugin-docs/api/properties/figma-notify

## Properties

### button?

> `optional` **button**: `object`

Defined in: figmaPluginTypes.ts:2242

#### action()

> **action**: () => `boolean` \| `void`

##### Returns

`boolean` \| `void`

#### text

> **text**: `string`

---

### error?

> `optional` **error**: `boolean`

Defined in: figmaPluginTypes.ts:2240

---

### onDequeue()?

> `optional` **onDequeue**: (`reason`) => `void`

Defined in: figmaPluginTypes.ts:2241

#### Parameters

##### reason

[`NotifyDequeueReason`](../type-aliases/NotifyDequeueReason.md)

#### Returns

`void`

---

### timeout?

> `optional` **timeout**: `number`

Defined in: figmaPluginTypes.ts:2239
