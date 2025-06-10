---

Action

# Type Alias: Action

> **Action** = \{ `type`: `"BACK"` \| `"CLOSE"`; \} \| \{ `openInNewTab?`: `boolean`; `type`: `"URL"`; `url`: `string`; \} \| \{ `destinationId`: `string` \| `null`; `mediaAction`: `"PLAY"` \| `"PAUSE"` \| `"TOGGLE_PLAY_PAUSE"` \| `"MUTE"` \| `"UNMUTE"` \| `"TOGGLE_MUTE_UNMUTE"`; `type`: `"UPDATE_MEDIA_RUNTIME"`; \} \| \{ `amountToSkip`: `number`; `destinationId?`: `string` \| `null`; `mediaAction`: `"SKIP_FORWARD"` \| `"SKIP_BACKWARD"`; `type`: `"UPDATE_MEDIA_RUNTIME"`; \} \| \{ `destinationId?`: `string` \| `null`; `mediaAction`: `"SKIP_TO"`; `newTimestamp`: `number`; `type`: `"UPDATE_MEDIA_RUNTIME"`; \} \| \{ `type`: `"SET_VARIABLE"`; `variableId`: `string` \| `null`; `variableValue?`: [`VariableData`](../interfaces/VariableData.md); \} \| \{ `type`: `"SET_VARIABLE_MODE"`; `variableCollectionId`: `string` \| `null`; `variableModeId`: `string` \| `null`; \} \| \{ `conditionalBlocks`: [`ConditionalBlock`](ConditionalBlock.md)[]; `type`: `"CONDITIONAL"`; \} \| \{ `destinationId`: `string` \| `null`; `navigation`: [`Navigation`](Navigation.md); `overlayRelativePosition?`: [`Vector`](../interfaces/Vector.md); `preserveScrollPosition?`: `boolean`; `resetInteractiveComponents?`: `boolean`; `resetScrollPosition?`: `boolean`; `resetVideoPosition?`: `boolean`; `transition`: [`Transition`](Transition.md) \| `null`; `type`: `"NODE"`; \}

Defined in: figmaPluginTypes.ts:4648

## Type declaration

\{ `type`: `"BACK"` \| `"CLOSE"`; \}

### type

> `readonly` **type**: `"BACK"` \| `"CLOSE"`

\{ `openInNewTab?`: `boolean`; `type`: `"URL"`; `url`: `string`; \}

### openInNewTab?

> `optional` **openInNewTab**: `boolean`

### type

> `readonly` **type**: `"URL"`

### url

> **url**: `string`

\{ `destinationId`: `string` \| `null`; `mediaAction`: `"PLAY"` \| `"PAUSE"` \| `"TOGGLE_PLAY_PAUSE"` \| `"MUTE"` \| `"UNMUTE"` \| `"TOGGLE_MUTE_UNMUTE"`; `type`: `"UPDATE_MEDIA_RUNTIME"`; \}

### destinationId

> `readonly` **destinationId**: `string` \| `null`

### mediaAction

> `readonly` **mediaAction**: `"PLAY"` \| `"PAUSE"` \| `"TOGGLE_PLAY_PAUSE"` \| `"MUTE"` \| `"UNMUTE"` \| `"TOGGLE_MUTE_UNMUTE"`

### type

> `readonly` **type**: `"UPDATE_MEDIA_RUNTIME"`

\{ `amountToSkip`: `number`; `destinationId?`: `string` \| `null`; `mediaAction`: `"SKIP_FORWARD"` \| `"SKIP_BACKWARD"`; `type`: `"UPDATE_MEDIA_RUNTIME"`; \}

### amountToSkip

> `readonly` **amountToSkip**: `number`

### destinationId?

> `readonly` `optional` **destinationId**: `string` \| `null`

### mediaAction

> `readonly` **mediaAction**: `"SKIP_FORWARD"` \| `"SKIP_BACKWARD"`

### type

> `readonly` **type**: `"UPDATE_MEDIA_RUNTIME"`

\{ `destinationId?`: `string` \| `null`; `mediaAction`: `"SKIP_TO"`; `newTimestamp`: `number`; `type`: `"UPDATE_MEDIA_RUNTIME"`; \}

### destinationId?

> `readonly` `optional` **destinationId**: `string` \| `null`

### mediaAction

> `readonly` **mediaAction**: `"SKIP_TO"`

### newTimestamp

> `readonly` **newTimestamp**: `number`

### type

> `readonly` **type**: `"UPDATE_MEDIA_RUNTIME"`

\{ `type`: `"SET_VARIABLE"`; `variableId`: `string` \| `null`; `variableValue?`: [`VariableData`](../interfaces/VariableData.md); \}

### type

> `readonly` **type**: `"SET_VARIABLE"`

### variableId

> `readonly` **variableId**: `string` \| `null`

### variableValue?

> `readonly` `optional` **variableValue**: [`VariableData`](../interfaces/VariableData.md)

\{ `type`: `"SET_VARIABLE_MODE"`; `variableCollectionId`: `string` \| `null`; `variableModeId`: `string` \| `null`; \}

### type

> `readonly` **type**: `"SET_VARIABLE_MODE"`

### variableCollectionId

> `readonly` **variableCollectionId**: `string` \| `null`

### variableModeId

> `readonly` **variableModeId**: `string` \| `null`

\{ `conditionalBlocks`: [`ConditionalBlock`](ConditionalBlock.md)[]; `type`: `"CONDITIONAL"`; \}

### conditionalBlocks

> `readonly` **conditionalBlocks**: [`ConditionalBlock`](ConditionalBlock.md)[]

### type

> `readonly` **type**: `"CONDITIONAL"`

\{ `destinationId`: `string` \| `null`; `navigation`: [`Navigation`](Navigation.md); `overlayRelativePosition?`: [`Vector`](../interfaces/Vector.md); `preserveScrollPosition?`: `boolean`; `resetInteractiveComponents?`: `boolean`; `resetScrollPosition?`: `boolean`; `resetVideoPosition?`: `boolean`; `transition`: [`Transition`](Transition.md) \| `null`; `type`: `"NODE"`; \}

### destinationId

> `readonly` **destinationId**: `string` \| `null`

### navigation

> `readonly` **navigation**: [`Navigation`](Navigation.md)

### overlayRelativePosition?

> `readonly` `optional` **overlayRelativePosition**: [`Vector`](../interfaces/Vector.md)

### ~~preserveScrollPosition?~~

> `readonly` `optional` **preserveScrollPosition**: `boolean`

#### Deprecated

Use `resetScrollPosition` instead.

### resetInteractiveComponents?

> `readonly` `optional` **resetInteractiveComponents**: `boolean`

### resetScrollPosition?

> `readonly` `optional` **resetScrollPosition**: `boolean`

### resetVideoPosition?

> `readonly` `optional` **resetVideoPosition**: `boolean`

### transition

> `readonly` **transition**: [`Transition`](Transition.md) \| `null`

### type

> `readonly` **type**: `"NODE"`

## See

https://www.figma.com/plugin-docs/api/Action
