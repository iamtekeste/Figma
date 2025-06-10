---

ViewportAPI

# Interface: ViewportAPI

Defined in: figmaPluginTypes.ts:2781

## See

https://www.figma.com/plugin-docs/api/figma-viewport

## Properties

### bounds

> `readonly` **bounds**: [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:2802

The bounds of the viewport of the page that is currently visible on screen. The (x, y) corresponds to the top-left of the screen. User actions such as resizing the window or showing/hiding the rulers/UI will change the bounds of the viewport.

---

### center

> **center**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:2785

Center of the the current page that is currently visible on screen.

---

### slidesView

> **slidesView**: `"grid"` \| `"single-slide"`

Defined in: figmaPluginTypes.ts:2829

Note: This API is only available in Figma Slides

#### Remarks

The viewport mode within the Slides UI: In Single Slide View, the viewport is zoomed into the current slide, and we only render that
one slide. In Grid View, the viewport is zoomed out to show the entire slide grid.

You can access the current view:

```ts
const currentView = figma.viewport.slidesView;
```

And you can set the view:

```ts
figma.viewport.slidesView = "single-slide";
```

### A Note About Single Slide View:

We have updated all of the create methods (`figma.createRectangle()`, `figma.createLine()`, etc) so that when the Figma Slides file is in Single Slide View,
they append that node to the focused slide instead of to the canvas. This is to ensure that the node you are creating is viewable by the current user and
not hidden off to the side of the larger grid view.

---

### zoom

> **zoom**: `number`

Defined in: figmaPluginTypes.ts:2794

Zoom level. A value of 1.0 means 100% zoom, 0.5 means 50% zoom.

#### Remarks

- zoom &lt; 1: design is zoomed out
- zoom = 1: design is shown at exact size
- zoom &gt; 1: design is zoomed in

## Methods

### scrollAndZoomIntoView()

> **scrollAndZoomIntoView**(`nodes`): `void`

Defined in: figmaPluginTypes.ts:2798

Automatically sets the viewport coordinates such that the nodes are visible on screen. It is the equivalent of pressing Shift-1.

#### Parameters

##### nodes

readonly [`BaseNode`](../type-aliases/BaseNode.md)[]

#### Returns

`void`
