---

FramePrototypingMixin

# Interface: FramePrototypingMixin

Defined in: figmaPluginTypes.ts:6818

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`DefaultFrameMixin`](DefaultFrameMixin.md)

## Properties

### numberOfFixedChildren

> **numberOfFixedChildren**: `number`

Defined in: figmaPluginTypes.ts:6834

Determines which children of the frame are fixed children in a scrolling frame.

#### Remarks

In Figma, fixed children are always on top of scrolling (non-fixed) children. Despite the "Fix position when scrolling" checkbox in the UI, fixed layers are not represented as a boolean property on individual layers. Instead, what we really have are two sections of children inside each frame. These section headers are visible in the layers panel when a frame has at least one fixed child.

---

### overflowDirection

> **overflowDirection**: [`OverflowDirection`](../type-aliases/OverflowDirection.md)

Defined in: figmaPluginTypes.ts:6826

Determines whether a frame will scroll in presentation mode when the frame contains content that exceed the frame's bounds. Reflects the value shown in "Overflow Behavior" in the Prototype tab.

#### Remarks

Frames directly parented under the canvas don't need this property to be set or for content to exceed the frame's bounds in order to scroll in presentation mode. They just need the frame to be bigger than the device or screen and will scroll automatically.

---

### overlayBackground

> `readonly` **overlayBackground**: [`OverlayBackground`](../type-aliases/OverlayBackground.md)

Defined in: figmaPluginTypes.ts:6842

How this frame obscures the content under it when opened as an overlay.

---

### overlayBackgroundInteraction

> `readonly` **overlayBackgroundInteraction**: [`OverlayBackgroundInteraction`](../type-aliases/OverlayBackgroundInteraction.md)

Defined in: figmaPluginTypes.ts:6846

How the user can interact with the content under this frame when opened as an overlay.

---

### overlayPositionType

> `readonly` **overlayPositionType**: [`OverlayPositionType`](../type-aliases/OverlayPositionType.md)

Defined in: figmaPluginTypes.ts:6838

How this frame is positioned when opened as an overlay.
