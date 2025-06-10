---

ParametersAPI

# Interface: ParametersAPI

Defined in: figmaPluginTypes.ts:2960

## See

https://www.figma.com/plugin-docs/api/figma-parameters

## Methods

### off()

> **off**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2972

Removes a handler added via `figma.parameters.on`.

#### Parameters

##### type

`"input"`

##### callback

(`event`) => `void`

#### Returns

`void`

---

### on()

> **on**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2964

Register a handler for user input events in the quick action UI.

#### Parameters

##### type

`"input"`

##### callback

(`event`) => `void`

#### Returns

`void`

---

### once()

> **once**(`type`, `callback`): `void`

Defined in: figmaPluginTypes.ts:2968

Register a handler for user input events in the quick action UI. Same as `figma.parameters.on("input")`, but only gets called the first time.

#### Parameters

##### type

`"input"`

##### callback

(`event`) => `void`

#### Returns

`void`
