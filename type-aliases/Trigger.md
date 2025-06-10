---

Trigger

# Type Alias: Trigger

> **Trigger** = \{ `type`: `"ON_CLICK"` \| `"ON_HOVER"` \| `"ON_PRESS"` \| `"ON_DRAG"`; \} \| \{ `timeout`: `number`; `type`: `"AFTER_TIMEOUT"`; \} \| \{ `delay`: `number`; `type`: `"MOUSE_UP"` \| `"MOUSE_DOWN"`; \} \| \{ `delay`: `number`; `deprecatedVersion`: `boolean`; `type`: `"MOUSE_ENTER"` \| `"MOUSE_LEAVE"`; \} \| \{ `device`: `"KEYBOARD"` \| `"XBOX_ONE"` \| `"PS4"` \| `"SWITCH_PRO"` \| `"UNKNOWN_CONTROLLER"`; `keyCodes`: `ReadonlyArray`\<`number`\>; `type`: `"ON_KEY_DOWN"`; \} \| \{ `mediaHitTime`: `number`; `type`: `"ON_MEDIA_HIT"`; \} \| \{ `type`: `"ON_MEDIA_END"`; \}

Defined in: figmaPluginTypes.ts:4730
