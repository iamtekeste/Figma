---

BaseUser

# Interface: BaseUser

Defined in: figmaPluginTypes.ts:10205

## See

https://www.figma.com/plugin-docs/api/BaseUser

## Extended by

- [`User`](User.md)

## Properties

### id

> `readonly` **id**: `null` \| `string`

Defined in: figmaPluginTypes.ts:10211

The user's id. `id` will be automatically generated users in workshop mode.
`id` will also be automatically generated for the current user if they are not logged in.
For other non-logged in users, this value will be null.

---

### name

> `readonly` **name**: `string`

Defined in: figmaPluginTypes.ts:10215

The user's name. `name` will be 'Anonymous' for non-logged in users.

---

### photoUrl

> `readonly` **photoUrl**: `null` \| `string`

Defined in: figmaPluginTypes.ts:10221

The user's photo URL. `photoUrl` will be automatically generated users in workshop mode.
`photoUrl` will also be automatically generated for the current user if they are not logged in.
For other non-logged in users, this value will be null.
