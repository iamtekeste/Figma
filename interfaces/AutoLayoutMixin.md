---

AutoLayoutMixin

# Interface: AutoLayoutMixin

Defined in: figmaPluginTypes.ts:6007

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`InferredAutoLayoutResult`](InferredAutoLayoutResult.md)
- [`BaseFrameMixin`](BaseFrameMixin.md)

## Properties

### counterAxisAlignContent

> **counterAxisAlignContent**: `"AUTO"` \| `"SPACE_BETWEEN"`

Defined in: figmaPluginTypes.ts:6307

Applicable only on auto-layout frames with [AutoLayoutMixin.layoutWrap](#layoutwrap) set to `"WRAP"`. Determines how the wrapped tracks are spaced out inside of the auto-layout frame.

#### Remarks

Changing this property on a non-wrapping auto-layout frame will throw an error.

- `"AUTO"`: If all children of this auto-layout frame have [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign) set to `"STRETCH"`, the tracks will stretch to fill the auto-layout frame. This is like flexbox `align-content: stretch`. Otherwise, each track will be as tall as the tallest child of the track, and will align based on the value of [AutoLayoutMixin.counterAxisAlignItems](#counteraxisalignitems). This is like flexbox `align-content: start | center | end`. [AutoLayoutMixin.counterAxisSpacing](#counteraxisspacing) is respected when `counterAxisAlignContent` is set to `"AUTO"`.
- `"SPACE_BETWEEN"`: Tracks are all sized based on the tallest child in the track. The free space within the auto-layout frame is divided up evenly between each track. If the total height of all tracks is taller than the height of the auto-layout frame, the spacing will be 0.

---

### counterAxisAlignItems

> **counterAxisAlignItems**: `"MIN"` \| `"CENTER"` \| `"MAX"` \| `"BASELINE"`

Defined in: figmaPluginTypes.ts:6296

Applicable only on auto-layout frames. Determines how the auto-layout frame’s children should be aligned in the counter axis direction.

#### Remarks

Changing this property will cause all the children to update their `x` and `y` values.

- In horizontal auto-layout frames, `“MIN”` and `“MAX”` correspond to top and bottom respectively.
- In vertical auto-layout frames, `“MIN”` and `“MAX”` correspond to left and right respectively.
- `"BASELINE"` can only be set on horizontal auto-layout frames, and aligns all children along the [text baseline](https://help.figma.com/hc/en-us/articles/360040451373-Explore-auto-layout-properties#Text_baseline_alignment).

The corresponding property for the primary axis direction is [AutoLayoutMixin.primaryAxisAlignItems](#primaryaxisalignitems).

```ts title="Horizontal auto-layout frame with different counterAxisAlignItems values"
(async () => {
  const parentFrame = figma.createFrame();
  const text = figma.createText();
  await figma.loadFontAsync(text.fontName);
  text.characters = "asdf";
  // Make the text taller so we can see how text baseline alignment works
  text.lineHeight = { unit: "PERCENT", value: 300 };

  // Auto-layout frame will have 2 children: a frame and a text node
  parentFrame.appendChild(figma.createFrame());
  parentFrame.appendChild(text);
  parentFrame.layoutMode = "HORIZONTAL";

  // Make the parent frame taller so we can see the effects of
  // the different counterAxisAlignItems values
  parentFrame.resize(200, 150);

  // Parent frame
  // +--------------------------+
  // |+-----------++----+       |
  // ||           ||    |       |
  // ||  Child 1  ||asdf|       |
  // ||           ||    |       |
  // |+-----------++----+       |
  // |                          |
  // |                          |
  // +--------------------------+
  parentFrame.counterAxisAlignItems = "MIN";

  // Parent frame
  // +--------------------------+
  // |                          |
  // |                          |
  // |+-----------++----+       |
  // ||           ||    |       |
  // ||  Child 1  ||asdf|       |
  // ||           ||    |       |
  // |+-----------++----+       |
  // +--------------------------+
  parentFrame.counterAxisAlignItems = "MAX";

  // Parent frame
  // +--------------------------+
  // |                          |
  // |+-----------++----+       |
  // ||           ||    |       |
  // ||  Child 1  ||asdf|       |
  // ||           ||    |       |
  // |+-----------++----+       |
  // |                          |
  // +--------------------------+
  parentFrame.counterAxisAlignItems = "CENTER";

  // Parent frame
  // +--------------------------+
  // |+-----------+             |
  // ||           |+----+       |
  // ||  Child 1  ||    |       |
  // ||           ||asdf|       |
  // |+-----------+|    |       |
  // |             +----+       |
  // |                          |
  // +--------------------------+
  parentFrame.counterAxisAlignItems = "BASELINE";
})();
```

---

### counterAxisSizingMode

> **counterAxisSizingMode**: `"AUTO"` \| `"FIXED"`

Defined in: figmaPluginTypes.ts:6149

Applicable only on auto-layout frames. Determines whether the counter axis has a fixed length (determined by the user) or an automatic length (determined by the layout engine).

#### Remarks

Auto-layout frames have a **primary axis**, which is the axis that resizes when you add new items into the frame. For example, frames with "VERTICAL" [AutoLayoutMixin.layoutMode](#layoutmode) resize in the y-axis.

The other axis is called the **counter axis**.

- `"FIXED"`: The counter axis length is determined by the user or plugins, unless the [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign) is set to “STRETCH” or [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow) is 1.
- `"AUTO"`: The counter axis length is determined by the size of the children. If set, the auto-layout frame will automatically resize along the counter axis to fit its children.

Note: `“AUTO”` cannot be used in any axes where [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign) = “STRETCH” or [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow) = 1. Either use `“FIXED”` or disable [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign)/[AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow).

```ts title="Horizontal auto-layout frame with different counterAxisSizingMode values"
const parentFrame = figma.createFrame();
const child2 = figma.createFrame();
// Make the second child 200px high instead of the default 100px
child2.resize(100, 200);
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(child2);
parentFrame.layoutMode = "HORIZONTAL";

// Parent frame
// +--------------------------+
// |+-----------++-----------+|
// ||           ||           ||
// ||  Child 1  ||  Child 2  ||
// ||           ||           ||
// |+-----------+|           ||
// +--------------------------+
parentFrame.counterAxisSizingMode = "FIXED"; // Child 2 is clipped

// Parent frame
// +--------------------------+
// |+-----------++-----------+|
// ||           ||           ||
// ||  Child 1  ||  Child 2  ||
// ||           ||           ||
// |+-----------+|           ||
// |             |           ||
// |             |           ||
// |             +-----------+|
// +--------------------------+
parentFrame.counterAxisSizingMode = "AUTO";
```

---

### counterAxisSpacing

> **counterAxisSpacing**: `null` \| `number`

Defined in: figmaPluginTypes.ts:6407

Applicable only on auto-layout frames with [AutoLayoutMixin.layoutWrap](#layoutwrap) set to `"WRAP"`. Determines the distance between wrapped tracks. The value must be positive.

#### Remarks

Set this propety to `null` to have it sync with [AutoLayoutMixin.itemSpacing](#itemspacing). This will never return `null`. Once set to `null`, it will start returning the value of [AutoLayoutMixin.itemSpacing](#itemspacing).

```ts title="Auto-layout frame with children wrapping to the next line"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(figma.createFrame());

// Make children flow horizontally and wrap
parentFrame.layoutMode = "HORIZONTAL";
parentFrame.layoutWrap = "WRAP";

// Set a fixed width so when we set itemSpacing below, the children will wrap
parentFrame.primaryAxisSizingMode = "FIXED";

// Let the height of the parent frame resize to fit the children
parentFrame.counterAxisSizingMode = "AUTO";

// Horizontal gap between children
parentFrame.itemSpacing = 10;

// Parent frame
// +------------------------------------------+
// |+-----------+          +-----------+      |
// ||           |          |           |      |
// ||  Child 1  | -- 10 -- |  Child 2  |      |
// ||           |          |           |      |
// |+-----------+          +-----------+      |
// |      |                                   |
// |      |                                   |
// |      20                                  |
// |      |                                   |
// |      |                                   |
// |+-----------+                             |
// ||           |                             |
// ||  Child 3  |                             |
// ||           |                             |
// |+-----------+                             |
// +------------------------------------------+
parentFrame.counterAxisSpacing = 20;
```

---

### ~~horizontalPadding~~

> **horizontalPadding**: `number`

Defined in: figmaPluginTypes.ts:6085

#### Deprecated

Use `paddingLeft` and `paddingRight` instead.

---

### itemReverseZIndex

> **itemReverseZIndex**: `boolean`

Defined in: figmaPluginTypes.ts:6447

Applicable only on auto-layout frames. Determines the [canvas stacking order](https://help.figma.com/hc/en-us/articles/360040451373-Explore-auto-layout-properties#Canvas_stacking_order) of layers in this frame. When true, the first layer will be draw on top.

#### Remarks

```ts title="Auto-layout frame with different canvas stacking"
const parentFrame = figma.createFrame();
// Create red and green children so we can see the overlap
const child1 = figma.createFrame();
child1.fills = [{ type: "SOLID", color: { r: 1, g: 0, b: 0 } }];
const child2 = figma.createFrame();
child2.fills = [{ type: "SOLID", color: { r: 0, g: 1, b: 0 } }];
parentFrame.appendChild(child1);
parentFrame.appendChild(child2);
parentFrame.layoutMode = "HORIZONTAL";
// Negative horizontal gap between children so they overlap
parentFrame.itemSpacing = -20;

// Parent frame (last child on top)
// +---------------------+
// |+-------+-----------+|
// ||       |           ||
// ||Child 1|  Child 2  ||
// ||       |           ||
// |+-------+-----------+|
// +---------------------+
parentFrame.itemReverseZIndex = false;

// Parent frame (first child on top)
// +---------------------+
// |+-----------+-------+|
// ||           |       ||
// ||  Child 1  |Child 2||
// ||           |       ||
// |+-----------+-------+|
// +---------------------+
parentFrame.itemReverseZIndex = true;
```

---

### itemSpacing

> **itemSpacing**: `number`

Defined in: figmaPluginTypes.ts:6359

Applicable only on auto-layout frames. Determines distance between children of the frame.

#### Remarks

For auto-layout frames with [AutoLayoutMixin.layoutMode](#layoutmode) set to `"HORIZONTAL"`, this is the horizontal gap between children. For auto-layout frames with [AutoLayoutMixin.layoutMode](#layoutmode) set to `"VERTICAL"`, this is the vertical gap between children.

```ts title="Auto-layout frame with a horizontal gap between children"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(figma.createFrame());
parentFrame.layoutMode = "HORIZONTAL";

// Parent frame
// +------------------------------------+
// |+-----------+          +-----------+|
// ||           |          |           ||
// ||  Child 1  | -- 20 -- |  Child 2  ||
// ||           |          |           ||
// |+-----------+          +-----------+|
// +------------------------------------+
parentFrame.itemSpacing = 20;
```

```ts title="Auto-layout frame with a vertical gap between children"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(figma.createFrame());
parentFrame.layoutMode = "VERTICAL";

// Parent frame
// +-------------+
// |+-----------+|
// ||           ||
// ||  Child 1  ||
// ||           ||
// |+-----------+|
// |      |      |
// |      |      |
// |      20     |
// |      |      |
// |      |      |
// |+-----------+|
// ||           ||
// ||  Child 2  ||
// ||           ||
// |+-----------+|
// +-------------+
parentFrame.itemSpacing = 20;
```

---

### layoutMode

> **layoutMode**: `"NONE"` \| `"HORIZONTAL"` \| `"VERTICAL"`

Defined in: figmaPluginTypes.ts:6055

Determines whether this layer uses auto-layout to position its children. Defaults to "NONE".

#### Remarks

Changing this property will cause the position of the children of this layer to change as a side-effect. It also causes the size of this layer to change, since at least one dimension of auto-layout frames is automatically calculated.

As a consequence, note that if a frame has `layoutMode === "NONE"`, calling `layoutMode = "VERTICAL"; layoutMode = "NONE"` does not leave the document unchanged. Removing auto-layout from a frame does not restore the children to their original positions.

This property must be set to `"HORIZONTAL"` or `"VERTICAL"` in order for the [AutoLayoutMixin.primaryAxisSizingMode](#primaryaxissizingmode), [AutoLayoutMixin.counterAxisSizingMode](#counteraxissizingmode), [AutoLayoutMixin.layoutWrap](#layoutwrap), [AutoLayoutMixin.primaryAxisAlignItems](#primaryaxisalignitems), [AutoLayoutMixin.counterAxisAlignItems](#counteraxisalignitems), [AutoLayoutMixin.counterAxisAlignContent](#counteraxisaligncontent), [AutoLayoutMixin.paddingTop](#paddingtop), [AutoLayoutMixin.paddingBottom](#paddingbottom), [AutoLayoutMixin.paddingLeft](#paddingleft), [AutoLayoutMixin.paddingRight](#paddingright), [AutoLayoutMixin.itemSpacing](#itemspacing), [AutoLayoutMixin.counterAxisSpacing](#counteraxisspacing), [AutoLayoutMixin.itemReverseZIndex](#itemreversezindex), and [AutoLayoutMixin.strokesIncludedInLayout](#strokesincludedinlayout) properties to be applicable.

```ts title="Auto-layout frame with horizontal layout"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(figma.createFrame());

// Parent frame
// +--------------------------+
// |+-----------++-----------+|
// ||           ||           ||
// ||  Child 1  ||  Child 2  ||
// ||           ||           ||
// |+-----------++-----------+|
// +--------------------------+
parentFrame.layoutMode = "HORIZONTAL";
```

````ts title="Auto-layout frame with vertical layout"
const parentFrame = figma.createFrame()
parentFrame.appendChild(figma.createFrame())
parentFrame.appendChild(figma.createFrame())

// Parent frame
// +-------------+
// |+-----------+|
// ||           ||
// ||  Child 1  ||
// ||           ||
// |+-----------+|
// |+-----------+|
// ||           ||
// ||  Child 2  ||
// ||           ||
// |+-----------+|
// +-------------+
parentFrame.layoutMode = 'VERTICAL'

***

### layoutWrap

> **layoutWrap**: `"NO_WRAP"` \| `"WRAP"`

Defined in: figmaPluginTypes.ts:6065

Determines whether this layer should use wrapping auto-layout. Defaults to "NO_WRAP".

#### Remarks

This property can only be set on layers with `layoutMode === "HORIZONTAL"`. Setting it on layers without this property will throw an Error.

This property must be set to `"WRAP"` in order for the [AutoLayoutMixin.counterAxisSpacing](#counteraxisspacing) and [AutoLayoutMixin.counterAxisAlignContent](#counteraxisaligncontent) properties to be applicable.

***

### paddingBottom

> **paddingBottom**: `number`

Defined in: figmaPluginTypes.ts:6081

Applicable only on auto-layout frames. Determines the bottom padding between the border of the frame and its children.

***

### paddingLeft

> **paddingLeft**: `number`

Defined in: figmaPluginTypes.ts:6069

Applicable only on auto-layout frames. Determines the left padding between the border of the frame and its children.

***

### paddingRight

> **paddingRight**: `number`

Defined in: figmaPluginTypes.ts:6073

Applicable only on auto-layout frames. Determines the right padding between the border of the frame and its children.

***

### paddingTop

> **paddingTop**: `number`

Defined in: figmaPluginTypes.ts:6077

Applicable only on auto-layout frames. Determines the top padding between the border of the frame and its children.

***

### primaryAxisAlignItems

> **primaryAxisAlignItems**: `"MIN"` \| `"CENTER"` \| `"MAX"` \| `"SPACE_BETWEEN"`

Defined in: figmaPluginTypes.ts:6214

Applicable only on auto-layout frames. Determines how the auto-layout frame’s children should be aligned in the primary axis direction.

#### Remarks

Changing this property will cause all the children to update their `x` and `y` values.

- In horizontal auto-layout frames, `“MIN”` and `“MAX”` correspond to left and right respectively.
- In vertical auto-layout frames, `“MIN”` and `“MAX”` correspond to top and bottom respectively.
- `“SPACE_BETWEEN”` will cause the children to space themselves evenly along the primary axis, only putting the extra space between the children.

The corresponding property for the counter axis direction is [AutoLayoutMixin.counterAxisAlignItems](#counteraxisalignitems).

```ts title="Horizontal auto-layout frame with different primaryAxisAlignItems values"
const parentFrame = figma.createFrame()
parentFrame.appendChild(figma.createFrame())
parentFrame.appendChild(figma.createFrame())
parentFrame.layoutMode = 'HORIZONTAL'

// Make the parent frame wider so we can see the effects of
// the different primaryAxisAlignItems values
parentFrame.resize(300, 100)

// Parent frame
// +------------------------------------+
// | +-----------++-----------+         |
// | |           ||           |         |
// | |  Child 1  ||  Child 2  |         |
// | |           ||           |         |
// | +-----------++-----------+         |
// +------------------------------------+
parentFrame.primaryAxisAlignItems = 'MIN'

// Parent frame
// +------------------------------------+
// |          +-----------++-----------+|
// |          |           ||           ||
// |          |  Child 1  ||  Child 2  ||
// |          |           ||           ||
// |          +-----------++-----------+|
// +------------------------------------+
parentFrame.primaryAxisAlignItems = 'MAX'

// Parent frame
// +------------------------------------+
// |     +-----------++-----------+     |
// |     |           ||           |     |
// |     |  Child 1  ||  Child 2  |     |
// |     |           ||           |     |
// |     +-----------++-----------+     |
// +------------------------------------+
parentFrame.primaryAxisAlignItems = 'CENTER'

// Parent frame
// +------------------------------------+
// |+-----------+          +-----------+|
// ||           |          |           ||
// ||  Child 1  |          |  Child 2  ||
// ||           |          |           ||
// |+-----------+          +-----------+|
// +------------------------------------+
parentFrame.primaryAxisAlignItems = 'SPACE_BETWEEN'
````

---

### primaryAxisSizingMode

> **primaryAxisSizingMode**: `"AUTO"` \| `"FIXED"`

Defined in: figmaPluginTypes.ts:6102

Applicable only on auto-layout frames. Determines whether the primary axis has a fixed length (determined by the user) or an automatic length (determined by the layout engine).

#### Remarks

Auto-layout frames have a **primary axis**, which is the axis that resizes when you add new items into the frame. For example, frames with "VERTICAL" [AutoLayoutMixin.layoutMode](#layoutmode) resize in the y-axis.

- `"FIXED"`: The primary axis length is determined by the user or plugins, unless the [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign) is set to “STRETCH” or [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow) is 1.
- `"AUTO"`: The primary axis length is determined by the size of the children. If set, the auto-layout frame will automatically resize along the counter axis to fit its children.

Note: `“AUTO”` should not be used in any axes where [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign) = “STRETCH” or [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow) = 1. Either use `“FIXED”` or disable [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign)/[AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow).

---

### strokesIncludedInLayout

> **strokesIncludedInLayout**: `boolean`

Defined in: figmaPluginTypes.ts:6488

Applicable only on auto-layout frames. Determines whether strokes are included in [layout calculations](https://help.figma.com/hc/en-us/articles/360040451373-Explore-auto-layout-properties#strokes-in-layout). When true, auto-layout frames behave like css `box-sizing: border-box`.

#### Remarks

```ts title="Auto-layout frame with strokes included in layout"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(figma.createFrame());
parentFrame.layoutMode = "HORIZONTAL";
// Let the height of the parent frame resize to fit the children
parentFrame.counterAxisSizingMode = "AUTO";

// Thick stroke around parent frame to illustrate layout differences
parentFrame.strokes = [{ type: "SOLID", color: { r: 0, g: 0, b: 0 } }];
parentFrame.strokeWeight = 10;

// Parent frame (strokes overlap with children)
// +--------------------------+
// |+-----------++-----------+|
// ||           ||           ||
// ||  Child 1  ||  Child 2  ||
// ||           ||           ||
// |+-----------++-----------+|
// +--------------------------+
parentFrame.strokesIncludedInLayout = false;

// Parent frame (strokes do not overlap with children)
// +--------------------------------+
// |                                |
// |   +-----------++-----------+   |
// |   |           ||           |   |
// |   |  Child 1  ||  Child 2  |   |
// |   |           ||           |   |
// |   +-----------++-----------+   |
// |                                |
// +--------------------------------+
parentFrame.strokesIncludedInLayout = true;
```

---

### ~~verticalPadding~~

> **verticalPadding**: `number`

Defined in: figmaPluginTypes.ts:6089

#### Deprecated

Use `paddingTop` and `paddingBottom` instead.
