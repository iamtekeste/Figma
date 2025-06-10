---

AutoLayoutChildrenMixin

# Interface: AutoLayoutChildrenMixin

Defined in: figmaPluginTypes.ts:6493

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`LayoutMixin`](LayoutMixin.md)
- [`InferredAutoLayoutResult`](InferredAutoLayoutResult.md)

## Properties

### layoutAlign

> **layoutAlign**: `"MIN"` \| `"CENTER"` \| `"MAX"` \| `"STRETCH"` \| `"INHERIT"`

Defined in: figmaPluginTypes.ts:6507

Applicable only on direct children of auto-layout frames. Determines if the layer should stretch along the parent’s counter axis. Defaults to `“INHERIT”`.

#### Remarks

Changing this property will cause the `x`, `y`, `size`, and `relativeTransform` properties on this node to change, if applicable (inside an auto-layout frame).

- Setting `"STRETCH"` will make the node "stretch" to fill the width of the parent vertical auto-layout frame, or the height of the parent horizontal auto-layout frame excluding the frame's padding.
- If the current node is an auto layout frame (e.g. an auto layout frame inside a parent auto layout frame) if you set layoutAlign to `“STRETCH”` you should set the corresponding axis – either [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode) or [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode) – to be`“FIXED”`. This is because an auto-layout frame cannot simultaneously stretch to fill its parent and shrink to hug its children.
- Setting `"INHERIT"` does not "stretch" the node.

Caution: ⚠️ Previously, layoutAlign also determined counter axis alignment of auto-layout frame children. Counter axis alignment is now set on the auto-layout frame itself through [AutoLayoutMixin.counterAxisAlignItems](AutoLayoutMixin.md#counteraxisalignitems). Note that this means all layers in an auto-layout frame must now have the same counter axis alignment. This means `"MIN"`, `"CENTER"`, and `"MAX"` are now deprecated values of `layoutAlign`.

---

### layoutGrow

> **layoutGrow**: `number`

Defined in: figmaPluginTypes.ts:6517

This property is applicable only for direct children of auto-layout frames. Determines whether a layer should stretch along the parent’s primary axis. 0 corresponds to a fixed size and 1 corresponds to stretch.

#### Remarks

0 and 1 are currently the only supported values.

Note: If the current node is an auto-layout frame (e.g. an auto-layout frame inside a parent auto-layout frame) if you set `layoutGrow` to 1 you should set the corresponding axis – either [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode) or [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode) – to be `“FIXED”`. This is because an auto-layout frame cannot simultaneously stretch to fill its parent and shrink to hug its children.

---

### layoutPositioning

> **layoutPositioning**: `"AUTO"` \| `"ABSOLUTE"`

Defined in: figmaPluginTypes.ts:6551

This property is applicable only for direct children of auto-layout frames. Determines whether a layer's size and position should be dermined by auto-layout settings or manually adjustable.

#### Remarks

Changing this property may cause the parent layer's size to change, since it will recalculate as if this child did not exist. It will also change this node's `x`, `y`, and `relativeTransform` properties.

- The default value of `"AUTO"` will layout this child according to auto-layout rules.
- Setting `"ABSOLUTE"` will take this child out of auto-layout flow, while still nesting inside the auto-layout frame. This allows explicitly setting `x`, `y`, `width`, and `height`. `"ABSOLUTE"` positioned nodes respect constraint settings.

```ts title="Auto-layout frame absolutely positioned red circle at the top-right corner"
const parentFrame = figma.createFrame();
parentFrame.appendChild(figma.createFrame());

// Create a small red circle
const ellipse = figma.createEllipse();
ellipse.resize(20, 20);
ellipse.fills = [{ type: "SOLID", color: { r: 1, g: 0, b: 0 } }];
parentFrame.appendChild(ellipse);
parentFrame.clipsContent = false;
parentFrame.layoutMode = "HORIZONTAL";

// Enable absolute positioning so we can move the circle
ellipse.layoutPositioning = "ABSOLUTE";

// Center the circle on the top-right corner of the frame
ellipse.x = 90;
ellipse.y = -10;

// Make the circle stick to the top-right corner of the frame
ellipse.constraints = { horizontal: "MAX", vertical: "MIN" };
```
