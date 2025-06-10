---

User

# Interface: User

Defined in: figmaPluginTypes.ts:10226

## See

https://www.figma.com/plugin-docs/api/User

## Extends

- [`BaseUser`](BaseUser.md)

## Extended by

- [`ActiveUser`](ActiveUser.md)

## Properties

### color

> `readonly` **color**: `string`

Defined in: figmaPluginTypes.ts:10230

The current user's multiplayer color. This will match the color of their dot stamps and cursor.

---

### id

> `readonly` **id**: `null` \| `string`

Defined in: figmaPluginTypes.ts:10211

The user's id. `id` will be automatically generated users in workshop mode.
`id` will also be automatically generated for the current user if they are not logged in.
For other non-logged in users, this value will be null.

#### Inherited from

[`BaseUser`](BaseUser.md).[`id`](BaseUser.md#id)

---

### name

> `readonly` **name**: `string`

Defined in: figmaPluginTypes.ts:10215

The user's name. `name` will be 'Anonymous' for non-logged in users.

#### Inherited from

[`BaseUser`](BaseUser.md).[`name`](BaseUser.md#name)

---

### photoUrl

> `readonly` **photoUrl**: `null` \| `string`

Defined in: figmaPluginTypes.ts:10221

The user's photo URL. `photoUrl` will be automatically generated users in workshop mode.
`photoUrl` will also be automatically generated for the current user if they are not logged in.
For other non-logged in users, this value will be null.

#### Inherited from

[`BaseUser`](BaseUser.md).[`photoUrl`](BaseUser.md#photourl)

---

### sessionId

> `readonly` **sessionId**: `number`

Defined in: figmaPluginTypes.ts:10236

The user's session id. This is guaranteed to be unique among active users.
For example, if a user with the same `id` opens a file in different tabs,
each `User` will have a unique `sessionId`.
