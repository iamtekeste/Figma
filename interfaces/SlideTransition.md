---

SlideTransition

# Interface: SlideTransition

Defined in: figmaPluginTypes.ts:9911

## See

https://www.figma.com/plugin-docs/api/SlideTransition

## Properties

### curve

> `readonly` **curve**: `"EASE_IN"` \| `"EASE_OUT"` \| `"EASE_IN_AND_OUT"` \| `"LINEAR"` \| `"GENTLE"` \| `"QUICK"` \| `"BOUNCY"` \| `"SLOW"`

Defined in: figmaPluginTypes.ts:9946

The easing of the slide transition.

---

### duration

> `readonly` **duration**: `number`

Defined in: figmaPluginTypes.ts:9942

The duration of the slide transition, in seconds.

---

### style

> `readonly` **style**: `"NONE"` \| `"DISSOLVE"` \| `"SMART_ANIMATE"` \| `"SLIDE_FROM_LEFT"` \| `"SLIDE_FROM_RIGHT"` \| `"SLIDE_FROM_BOTTOM"` \| `"SLIDE_FROM_TOP"` \| `"PUSH_FROM_LEFT"` \| `"PUSH_FROM_RIGHT"` \| `"PUSH_FROM_BOTTOM"` \| `"PUSH_FROM_TOP"` \| `"MOVE_FROM_LEFT"` \| `"MOVE_FROM_RIGHT"` \| `"MOVE_FROM_TOP"` \| `"MOVE_FROM_BOTTOM"` \| `"SLIDE_OUT_TO_LEFT"` \| `"SLIDE_OUT_TO_RIGHT"` \| `"SLIDE_OUT_TO_TOP"` \| `"SLIDE_OUT_TO_BOTTOM"` \| `"MOVE_OUT_TO_LEFT"` \| `"MOVE_OUT_TO_RIGHT"` \| `"MOVE_OUT_TO_TOP"` \| `"MOVE_OUT_TO_BOTTOM"`

Defined in: figmaPluginTypes.ts:9915

The type of slide transition.

---

### timing

> `readonly` **timing**: `object`

Defined in: figmaPluginTypes.ts:9958

The timing of the slide transition.

#### delay?

> `readonly` `optional` **delay**: `number`

The delay of the timing, in seconds.

#### type

> `readonly` **type**: `"ON_CLICK"` \| `"AFTER_DELAY"`

The type of timing.
