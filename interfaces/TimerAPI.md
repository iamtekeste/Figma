---

TimerAPI

# Interface: TimerAPI

Defined in: figmaPluginTypes.ts:2748

## See

https://www.figma.com/plugin-docs/api/figma-timer

## Properties

### pause()

> **pause**: () => `void`

Defined in: figmaPluginTypes.ts:2764

Pause the timer. If the timer has not been started, does nothing.

#### Returns

`void`

---

### remaining

> `readonly` **remaining**: `number`

Defined in: figmaPluginTypes.ts:2752

Time remaining on timer, in seconds. If the timer has not been started, returns 0.

---

### resume()

> **resume**: () => `void`

Defined in: figmaPluginTypes.ts:2768

Resume the timer. If the timer is not currently started and paused, does nothing.

#### Returns

`void`

---

### start()

> **start**: (`seconds`) => `void`

Defined in: figmaPluginTypes.ts:2772

Start the timer with `seconds` seconds remaining. If the timer is not currently started, will start the timer with this total time. If the timer is currently started, will set the remaining time to this value, and increment or decrement the timer's total time based on how much time was added or removed from the remaining time. If the timer was previously paused, will also unpause the timer.

#### Parameters

##### seconds

`number`

#### Returns

`void`

---

### state

> `readonly` **state**: `"STOPPED"` \| `"PAUSED"` \| `"RUNNING"`

Defined in: figmaPluginTypes.ts:2760

The current state of the timer. If the timer is started and not paused, the state will be `"RUNNING"`. If the timer is not started or finished, the state is `"STOPPED"`. And if the timer is started but paused, the state is `"PAUSED"`.

---

### stop()

> **stop**: () => `void`

Defined in: figmaPluginTypes.ts:2776

Stops the timer. If the timer was not started or is finished, does nothing.

#### Returns

`void`

---

### total

> `readonly` **total**: `number`

Defined in: figmaPluginTypes.ts:2756

Total time on timer, in seconds. If the timer has not been started, returns 0. The total time is defined as the time the timer was initially started at, plus or minus any time that may have been added or removed from the timer.
