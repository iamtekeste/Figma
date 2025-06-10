---

GroupNode

# Interface: GroupNode

Defined in: figmaPluginTypes.ts:8466

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`BaseNodeMixin`](BaseNodeMixin.md).[`SceneNodeMixin`](SceneNodeMixin.md).[`ReactionMixin`](ReactionMixin.md).[`ChildrenMixin`](ChildrenMixin.md).[`ContainerMixin`](ContainerMixin.md).[`DeprecatedBackgroundMixin`](DeprecatedBackgroundMixin.md).[`BlendMixin`](BlendMixin.md).[`LayoutMixin`](LayoutMixin.md).[`ExportMixin`](ExportMixin.md).[`AspectRatioLockMixin`](AspectRatioLockMixin.md)

## Properties

### absoluteBoundingBox

> `readonly` **absoluteBoundingBox**: `null` \| [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:5712

The bounds of the node that does not include rendered properties like drop shadows or strokes. The `x` and `y` inside this property represent the absolute position of the node on the page.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`absoluteBoundingBox`](LayoutMixin.md#absoluteboundingbox)

---

### absoluteRenderBounds

> `readonly` **absoluteRenderBounds**: `null` \| [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:5721

The actual bounds of a node accounting for drop shadows, thick strokes, and anything else that may fall outside the node's regular bounding box defined in `x`, `y`, `width`, and `height`. The `x` and `y` inside this property represent the absolute position of the node on the page. This value will be `null` if the node is invisible.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`absoluteRenderBounds`](LayoutMixin.md#absoluterenderbounds)

---

### absoluteTransform

> `readonly` **absoluteTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5708

The position of a node relative to its **containing page** as a [Transform](../type-aliases/Transform.md) matrix.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`absoluteTransform`](LayoutMixin.md#absolutetransform)

---

### attachedConnectors

> `readonly` **attachedConnectors**: [`ConnectorNode`](ConnectorNode.md)[]

Defined in: figmaPluginTypes.ts:5183

An array of `ConnectorNode`s that are attached to a node.

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`attachedConnectors`](SceneNodeMixin.md#attachedconnectors)

---

### ~~backgrounds~~

> **backgrounds**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:5995

#### Deprecated

Use `fills` instead.

#### Inherited from

[`DeprecatedBackgroundMixin`](DeprecatedBackgroundMixin.md).[`backgrounds`](DeprecatedBackgroundMixin.md#backgrounds)

---

### ~~backgroundStyleId~~

> **backgroundStyleId**: `string`

Defined in: figmaPluginTypes.ts:5999

#### Deprecated

Use `fillStyleId` instead. This property is read-only if the manifest contains `"documentAccess": "dynamic-page"`.

#### Inherited from

[`DeprecatedBackgroundMixin`](DeprecatedBackgroundMixin.md).[`backgroundStyleId`](DeprecatedBackgroundMixin.md#backgroundstyleid)

---

### blendMode

> **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:7182

Blend mode of this node, as shown in the Layer panel. In addition to the blend modes that paints & effects support, the layer blend mode can also have the value PASS_THROUGH.

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`blendMode`](BlendMixin.md#blendmode)

---

### boundVariables?

> `readonly` `optional` **boundVariables**: `object` & `object` & `object`

Defined in: figmaPluginTypes.ts:5195

The variables bound to a particular field on this node. Please see the [Working with Variables](https://www.figma.com/plugin-docs/working-with-variables) guide for how to get and set variable bindings.

#### Type declaration

##### bottomLeftRadius?

> `optional` **bottomLeftRadius**: [`VariableAlias`](VariableAlias.md)

##### bottomRightRadius?

> `optional` **bottomRightRadius**: [`VariableAlias`](VariableAlias.md)

##### characters?

> `optional` **characters**: [`VariableAlias`](VariableAlias.md)

##### counterAxisSpacing?

> `optional` **counterAxisSpacing**: [`VariableAlias`](VariableAlias.md)

##### height?

> `optional` **height**: [`VariableAlias`](VariableAlias.md)

##### itemSpacing?

> `optional` **itemSpacing**: [`VariableAlias`](VariableAlias.md)

##### maxHeight?

> `optional` **maxHeight**: [`VariableAlias`](VariableAlias.md)

##### maxWidth?

> `optional` **maxWidth**: [`VariableAlias`](VariableAlias.md)

##### minHeight?

> `optional` **minHeight**: [`VariableAlias`](VariableAlias.md)

##### minWidth?

> `optional` **minWidth**: [`VariableAlias`](VariableAlias.md)

##### opacity?

> `optional` **opacity**: [`VariableAlias`](VariableAlias.md)

##### paddingBottom?

> `optional` **paddingBottom**: [`VariableAlias`](VariableAlias.md)

##### paddingLeft?

> `optional` **paddingLeft**: [`VariableAlias`](VariableAlias.md)

##### paddingRight?

> `optional` **paddingRight**: [`VariableAlias`](VariableAlias.md)

##### paddingTop?

> `optional` **paddingTop**: [`VariableAlias`](VariableAlias.md)

##### strokeBottomWeight?

> `optional` **strokeBottomWeight**: [`VariableAlias`](VariableAlias.md)

##### strokeLeftWeight?

> `optional` **strokeLeftWeight**: [`VariableAlias`](VariableAlias.md)

##### strokeRightWeight?

> `optional` **strokeRightWeight**: [`VariableAlias`](VariableAlias.md)

##### strokeTopWeight?

> `optional` **strokeTopWeight**: [`VariableAlias`](VariableAlias.md)

##### strokeWeight?

> `optional` **strokeWeight**: [`VariableAlias`](VariableAlias.md)

##### topLeftRadius?

> `optional` **topLeftRadius**: [`VariableAlias`](VariableAlias.md)

##### topRightRadius?

> `optional` **topRightRadius**: [`VariableAlias`](VariableAlias.md)

##### visible?

> `optional` **visible**: [`VariableAlias`](VariableAlias.md)

##### width?

> `optional` **width**: [`VariableAlias`](VariableAlias.md)

#### Type declaration

##### fontFamily?

> `optional` **fontFamily**: [`VariableAlias`](VariableAlias.md)[]

##### fontSize?

> `optional` **fontSize**: [`VariableAlias`](VariableAlias.md)[]

##### fontStyle?

> `optional` **fontStyle**: [`VariableAlias`](VariableAlias.md)[]

##### fontWeight?

> `optional` **fontWeight**: [`VariableAlias`](VariableAlias.md)[]

##### letterSpacing?

> `optional` **letterSpacing**: [`VariableAlias`](VariableAlias.md)[]

##### lineHeight?

> `optional` **lineHeight**: [`VariableAlias`](VariableAlias.md)[]

##### paragraphIndent?

> `optional` **paragraphIndent**: [`VariableAlias`](VariableAlias.md)[]

##### paragraphSpacing?

> `optional` **paragraphSpacing**: [`VariableAlias`](VariableAlias.md)[]

#### Type declaration

##### componentProperties?

> `readonly` `optional` **componentProperties**: `object`

###### Index Signature

\[`propertyName`: `string`\]: [`VariableAlias`](VariableAlias.md)

##### effects?

> `readonly` `optional` **effects**: [`VariableAlias`](VariableAlias.md)[]

##### fills?

> `readonly` `optional` **fills**: [`VariableAlias`](VariableAlias.md)[]

##### layoutGrids?

> `readonly` `optional` **layoutGrids**: [`VariableAlias`](VariableAlias.md)[]

##### strokes?

> `readonly` `optional` **strokes**: [`VariableAlias`](VariableAlias.md)[]

##### textRangeFills?

> `readonly` `optional` **textRangeFills**: [`VariableAlias`](VariableAlias.md)[]

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`boundVariables`](SceneNodeMixin.md#boundvariables)

---

### children

> `readonly` **children**: readonly [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5369

The list of children, sorted back-to-front. That is, the first child in the array is the bottommost layer on the screen, and the last child in the array is the topmost layer.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this property.

#### Remarks

This array can be read like and iterated like a regular array. However, calling this property always returns a new array, and both the property and the new array are read-only.

As such, this property cannot be assigned to, and the array cannot be modified directly (it wouldn't do anything). Instead, use [ChildrenMixin.appendChild](ChildrenMixin.md#appendchild), [ChildrenMixin.insertChild](ChildrenMixin.md#insertchild) or [BaseNodeMixin.remove](BaseNodeMixin.md#remove).

Note: If you are curious, the reason why inserting children has to be done via API calls is because our internal representation for the layer tree uses [fractional indexing](https://www.figma.com/blog/multiplayer-editing-in-figma/) and [ChildrenMixin.insertChild](ChildrenMixin.md#insertchild) performs that conversion.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`children`](ChildrenMixin.md#children)

---

### componentPropertyReferences

> **componentPropertyReferences**: `null` \| \{ `characters?`: `string`; `mainComponent?`: `string`; `visible?`: `string`; \}

Defined in: figmaPluginTypes.ts:5187

All component properties that are attached on this node. A node can only have `componentPropertyReferences` if it is a component sublayer or an instance sublayer. It will be `null` otherwise. The value in the key-value pair refers to the component property name as returned by `componentPropertyDefinitions` on the containing component, component set or main component (for instances).

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`componentPropertyReferences`](SceneNodeMixin.md#componentpropertyreferences)

---

### ~~constrainProportions~~

> **constrainProportions**: `boolean`

Defined in: figmaPluginTypes.ts:5727

When toggled, causes the layer to keep its proportions when the user resizes it via the properties panel.

#### Deprecated

Use `targetAspectRatio`, `lockAspectRatio`, and `unlockAspectRatio` instead.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`constrainProportions`](LayoutMixin.md#constrainproportions)

---

### effects

> **effects**: readonly [`Effect`](../type-aliases/Effect.md)[]

Defined in: figmaPluginTypes.ts:5967

Array of effects. See [Effect](../type-aliases/Effect.md) type. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`effects`](BlendMixin.md#effects)

---

### effectStyleId

> **effectStyleId**: `string`

Defined in: figmaPluginTypes.ts:5973

The id of the [EffectStyle](EffectStyle.md) object that the properties of this node are linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setEffectStyleIdAsync` to update the style.

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`effectStyleId`](BlendMixin.md#effectstyleid)

---

### expanded

> **expanded**: `boolean`

Defined in: figmaPluginTypes.ts:5986

Whether this container is shown as expanded in the layers panel.

#### Inherited from

[`ContainerMixin`](ContainerMixin.md).[`expanded`](ContainerMixin.md#expanded)

---

### explicitVariableModes

> **explicitVariableModes**: `object`

Defined in: figmaPluginTypes.ts:8250

The explicitly set modes for this node.
For `SceneNodes`, represents a subset of [SceneNodeMixin.resolvedVariableModes](SceneNodeMixin.md#resolvedvariablemodes).
Note that this does not include [workspace and team-default modes](https://help.figma.com/hc/en-us/articles/12611253730071).

#### Index Signature

\[`collectionId`: `string`\]: `string`

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`explicitVariableModes`](SceneNodeMixin.md#explicitvariablemodes)

---

### exportSettings

> **exportSettings**: readonly [`ExportSettings`](../type-aliases/ExportSettings.md)[]

Defined in: figmaPluginTypes.ts:6748

List of export settings stored on the node. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportSettings`](ExportMixin.md#exportsettings)

---

### height

> `readonly` **height**: `number`

Defined in: figmaPluginTypes.ts:5642

The height of the node. Use a resizing method to change this value.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`height`](LayoutMixin.md#height)

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:4878

The unique identifier of a node. For example, `1:3`. The node id can be used with methods such as [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync), but plugins typically don't need to use this since you can usually just access a node directly.

#### Remarks

One possible use case for using the `id` is to have a serializable representation of a Figma node. To "deserialize" an id back into a node, pass it to [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync). This will return null if the node is no longer present in the document.

In the URLs for Figma files, node ids are hyphenated. However, for use with the API, node ids must use colons. For example, if a Figma file URL has the node id `1-3`, you must convert it to `1:3`.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`id`](BaseNodeMixin.md#id)

---

### inferredVariables?

> `readonly` `optional` **inferredVariables**: `object` & `object`

Defined in: figmaPluginTypes.ts:5248

An object, keyed by field, returning any variables that match the raw value of that field for the mode of the node (or the default variable value if no mode is set)

#### Type declaration

##### bottomLeftRadius?

> `optional` **bottomLeftRadius**: [`VariableAlias`](VariableAlias.md)[]

##### bottomRightRadius?

> `optional` **bottomRightRadius**: [`VariableAlias`](VariableAlias.md)[]

##### characters?

> `optional` **characters**: [`VariableAlias`](VariableAlias.md)[]

##### counterAxisSpacing?

> `optional` **counterAxisSpacing**: [`VariableAlias`](VariableAlias.md)[]

##### height?

> `optional` **height**: [`VariableAlias`](VariableAlias.md)[]

##### itemSpacing?

> `optional` **itemSpacing**: [`VariableAlias`](VariableAlias.md)[]

##### maxHeight?

> `optional` **maxHeight**: [`VariableAlias`](VariableAlias.md)[]

##### maxWidth?

> `optional` **maxWidth**: [`VariableAlias`](VariableAlias.md)[]

##### minHeight?

> `optional` **minHeight**: [`VariableAlias`](VariableAlias.md)[]

##### minWidth?

> `optional` **minWidth**: [`VariableAlias`](VariableAlias.md)[]

##### opacity?

> `optional` **opacity**: [`VariableAlias`](VariableAlias.md)[]

##### paddingBottom?

> `optional` **paddingBottom**: [`VariableAlias`](VariableAlias.md)[]

##### paddingLeft?

> `optional` **paddingLeft**: [`VariableAlias`](VariableAlias.md)[]

##### paddingRight?

> `optional` **paddingRight**: [`VariableAlias`](VariableAlias.md)[]

##### paddingTop?

> `optional` **paddingTop**: [`VariableAlias`](VariableAlias.md)[]

##### strokeBottomWeight?

> `optional` **strokeBottomWeight**: [`VariableAlias`](VariableAlias.md)[]

##### strokeLeftWeight?

> `optional` **strokeLeftWeight**: [`VariableAlias`](VariableAlias.md)[]

##### strokeRightWeight?

> `optional` **strokeRightWeight**: [`VariableAlias`](VariableAlias.md)[]

##### strokeTopWeight?

> `optional` **strokeTopWeight**: [`VariableAlias`](VariableAlias.md)[]

##### strokeWeight?

> `optional` **strokeWeight**: [`VariableAlias`](VariableAlias.md)[]

##### topLeftRadius?

> `optional` **topLeftRadius**: [`VariableAlias`](VariableAlias.md)[]

##### topRightRadius?

> `optional` **topRightRadius**: [`VariableAlias`](VariableAlias.md)[]

##### visible?

> `optional` **visible**: [`VariableAlias`](VariableAlias.md)[]

##### width?

> `optional` **width**: [`VariableAlias`](VariableAlias.md)[]

#### Type declaration

##### fills?

> `readonly` `optional` **fills**: [`VariableAlias`](VariableAlias.md)[][]

##### strokes?

> `readonly` `optional` **strokes**: [`VariableAlias`](VariableAlias.md)[][]

#### Remarks

Inferred variables are only returned for a field when it is not using a [bound variable](https://www.figma.com/plugin-docs/api/node-properties/#boundvariables).

Variables can be inferred from:

- The collections of variables used in the file
- Variables from subscribed libraries, provided the variable is used in the file

Variables can only be inferred when there is a single variable that matches the raw value used for the scope of the variable.

- i.e. For a property set to width: 100px, where there are two variables set to a value of 100 with the default scope, a value cannot be inferred as there are two matches.
- i.e. For a property set to width: 100px, where there is a variable set to 100 with a scope of "Width and height" and a variable set to 100 with a scope of "Corner radius", a value can be inferred as there is a single match for the given scope.

Inferred variables for fills and strokes return a list of results where the index matches that of node.fills and node.strokes.

- i.e. node.inferredVariables.fills[0] holds the inferred variables for node.fills[0]

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`inferredVariables`](SceneNodeMixin.md#inferredvariables)

---

### isAsset

> `readonly` **isAsset**: `boolean`

Defined in: figmaPluginTypes.ts:5010

Returns true if Figma detects that a node is an asset, otherwise returns false. An asset is is either an icon or a raster image.

This property is useful if you’re building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

Note: This property uses a set of heuristics to determine if a node is an asset. At a high level an icon is a small vector graphic and an image is a node with an image fill.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`isAsset`](BaseNodeMixin.md#isasset)

---

### isMask

> **isMask**: `boolean`

Defined in: figmaPluginTypes.ts:5959

Whether this node is a mask. A mask node masks its subsequent siblings.

#### Remarks

Since a mask node masks all of its subsequent siblings, enabling `isMask` on a node that is not in a group-like container designed to stop mask propagation can have unintented consequences — that is, it may "mask" (often in practice, hide) more siblings than you intend. When enabling `isMask`, ensure you have contained its propagation propertly. ("Subsequent siblings" are siblings listed _after_ this node in a `children` array in the plugin API; this corresponds to layers shown _above_ this node in the layers panel.)

Example:

```ts
const rect = figma.createRectangle();
const circleToMask = figma.createEllipse();
const otherCircle1 = figma.createEllipse();
const otherCircle2 = figma.createEllipse();

// In the layers panel, this would look something like:
// - otherCircle2
// - otherCircle1
// - circleToMask
// - rect
//
// So if I enable `rect.isMask`, the rect will mask ALL other nodes,
// because they are all siblings.
//
// If I only want `rect` to mask `circleToMask`, I should group
// them first.
figma.group(
  [rect, circleToMask],
  figma.currentPage,
  figma.currentPage.children.indexOf(circleToMask)
);
rect.isMask = true;

// Now `rect` only masks its siblings above it in its group
// (`circleToMask`) but not the circles outside of the group.
// In the layers panel this would look like:
// - otherCircle2
// - otherCircle1
// - Group
//   - circleToMask [this is the only node masked by rect]
//   - rect (isMask)
```

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`isMask`](BlendMixin.md#ismask)

---

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

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`layoutAlign`](LayoutMixin.md#layoutalign)

---

### layoutGrow

> **layoutGrow**: `number`

Defined in: figmaPluginTypes.ts:6517

This property is applicable only for direct children of auto-layout frames. Determines whether a layer should stretch along the parent’s primary axis. 0 corresponds to a fixed size and 1 corresponds to stretch.

#### Remarks

0 and 1 are currently the only supported values.

Note: If the current node is an auto-layout frame (e.g. an auto-layout frame inside a parent auto-layout frame) if you set `layoutGrow` to 1 you should set the corresponding axis – either [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode) or [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode) – to be `“FIXED”`. This is because an auto-layout frame cannot simultaneously stretch to fill its parent and shrink to hug its children.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`layoutGrow`](LayoutMixin.md#layoutgrow)

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

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`layoutPositioning`](LayoutMixin.md#layoutpositioning)

---

### layoutSizingHorizontal

> **layoutSizingHorizontal**: `"FILL"` \| `"FIXED"` \| `"HUG"`

Defined in: figmaPluginTypes.ts:5813

Applicable only on auto-layout frames, their children, and text nodes. This is a shorthand for setting [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow), [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign), [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode), and [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode). This field maps directly to the "Horizontal sizing" dropdown in the Figma UI.

#### Remarks

`"HUG"` is only valid on auto-layout frames and text nodes. `"FILL"` is only valid on auto-layout children. Setting these values when they don't apply will throw an error.

```ts title="Setting layoutSizingHorizontal on an auto-layout frame"
const parentFrame = figma.createFrame();
const child2 = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(child2);
parentFrame.layoutMode = "VERTICAL";
// Make the second child twice as wide as the first
child2.resize(200, 100);

// Parent frame (child 2 is clipped)
// +-------------+
// |+-----------+|
// ||           ||
// ||  Child 1  ||
// ||           ||
// |+-----------+|
// |+------------|
// ||            |
// ||  Child 2   |
// ||            |
// |+------------|
// +-------------+

parentFrame.layoutSizingHorizontal = "FIXED";

// Parent frame (child 2 is not clipped)
// +------------------------+
// |+-----------+           |
// ||           |           |
// ||  Child 1  |           |
// ||           |           |
// |+-----------+           |
// |+----------------------+|
// ||                      ||
// ||       Child 2        ||
// ||                      ||
// |+----------------------+|
// +------------------------+
parentFrame.layoutSizingHorizontal = "HUG";
```

```ts title="Setting layoutSizingHorizontal on an auto-layout child"
const parentFrame = figma.createFrame();
const child2 = figma.createFrame();
parentFrame.appendChild(figma.createFrame());
parentFrame.appendChild(child2);
parentFrame.layoutMode = "HORIZONTAL";
parentFrame.resize(300, 100);

// Parent frame
// +-------------------------------------+
// |+-----------++-----------+           |
// ||           ||           |           |
// ||  Child 1  ||  Child 2  |           |
// ||           ||           |           |
// |+-----------++-----------+           |
// +-------------------------------------+
child2.layoutSizingHorizontal = "FIXED";

// Parent frame
// +-------------------------------------+
// |+-----------++----------------------+|
// ||           ||                      ||
// ||  Child 1  ||       Child 2        ||
// ||           ||                      ||
// |+-----------++----------------------+|
// +-------------------------------------+
child2.layoutSizingHorizontal = "FILL";
```

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`layoutSizingHorizontal`](LayoutMixin.md#layoutsizinghorizontal)

---

### layoutSizingVertical

> **layoutSizingVertical**: `"FILL"` \| `"FIXED"` \| `"HUG"`

Defined in: figmaPluginTypes.ts:5821

Applicable only on auto-layout frames, their children, and text nodes. This is a shorthand for setting [AutoLayoutChildrenMixin.layoutGrow](AutoLayoutChildrenMixin.md#layoutgrow), [AutoLayoutChildrenMixin.layoutAlign](AutoLayoutChildrenMixin.md#layoutalign), [AutoLayoutMixin.primaryAxisSizingMode](AutoLayoutMixin.md#primaryaxissizingmode), and [AutoLayoutMixin.counterAxisSizingMode](AutoLayoutMixin.md#counteraxissizingmode). This field maps directly to the "Vertical sizing" dropdown in the Figma UI.

#### Remarks

`"HUG"` is only valid on auto-layout frames and text nodes. `"FILL"` is only valid on auto-layout children. Setting these values when they don't apply will throw an error.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`layoutSizingVertical`](LayoutMixin.md#layoutsizingvertical)

---

### locked

> **locked**: `boolean`

Defined in: figmaPluginTypes.ts:5167

Whether the node is locked or not, preventing certain user interactions on the canvas such as selecting and dragging. Does not affect a plugin's ability to write to those properties.

#### Remarks

The value that this property returns is independent from the node's parent. i.e.

- The node isn't necessarily locked if this is `.locked === true`.
- The node isn't necessarily unlocked if this is `.locked === false`.
- An object is locked if `.locked == true` for itself or **any** of its parents.

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`locked`](SceneNodeMixin.md#locked)

---

### maskType

> **maskType**: [`MaskType`](../type-aliases/MaskType.md)

Defined in: figmaPluginTypes.ts:5963

Type of masking to use if this node is a mask. Defaults to `"ALPHA"`. You must check `isMask` to verify that this is a mask; changing `maskType` does not automatically turn on `isMask`, and a node that is not a mask can still have a `maskType`.

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`maskType`](BlendMixin.md#masktype)

---

### maxHeight

> **maxHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5658

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxHeight`.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`maxHeight`](LayoutMixin.md#maxheight)

---

### maxWidth

> **maxWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5650

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxWidth`.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`maxWidth`](LayoutMixin.md#maxwidth)

---

### minHeight

> **minHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5654

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to null to remove `minHeight`.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`minHeight`](LayoutMixin.md#minheight)

---

### minWidth

> **minWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5646

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `minWidth`.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`minWidth`](LayoutMixin.md#minwidth)

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:4898

The name of the layer that appears in the layers panel. Calling `figma.root.name` will return the name, read-only, of the current file.

#### Remarks

If the node is a [TextNode](TextNode.md), the name will update automatically by default based on the `characters` property (`autoRename` is true). If you manually override the text node's name, it will set `autoRename` to false. This matches the behavior in the editor.

If the node is a [PageNode](PageNode.md) with no children and the name is a page divider name, it will set `isPageDivider` to true. A page divider name consists of all asterisks, all en dashes, all em dashes, or all spaces.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`name`](BaseNodeMixin.md#name)

---

### opacity

> **opacity**: `number`

Defined in: figmaPluginTypes.ts:7178

Opacity of the node, as shown in the Layer panel. Must be between 0 and 1.

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`opacity`](BlendMixin.md#opacity)

---

### parent

> `readonly` **parent**: `null` \| BaseNode & ChildrenMixin

Defined in: figmaPluginTypes.ts:4888

Returns the parent of this node, if any. This property is not meant to be directly edited. To reparent, see [ChildrenMixin.appendChild](ChildrenMixin.md#appendchild).

#### Remarks

The root node (i.e. `figma.root`) doesn't have a parent.

Components accessed via [instance.getMainComponentAsync()](InstanceNode.md#getmaincomponentasync) or [instance.mainComponent](InstanceNode.md#maincomponent) do not always have a parent. They could be remote components or soft-deleted components.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`parent`](BaseNodeMixin.md#parent)

---

### reactions

> **reactions**: readonly [`Reaction`](../type-aliases/Reaction.md)[]

Defined in: figmaPluginTypes.ts:7027

List of [Reactions](https://www.figma.com/plugin-docs/api/Reaction) on this node, which includes both the method of interaction with this node in a prototype, and the behavior of that interaction. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setReactionsAsync` to update the value.

#### Remarks

[Prototyping](https://help.figma.com/hc/en-us/articles/360040314193-Guide-to-prototyping-in-Figma) in Figma lets users create connections between nodes that consist of a trigger (click, hover, etc...) and a corresponding list of actions, such as navigating to another frame or setting a variable. The `reactions` property lets you read and modify prototyping reactions on the node.

```ts title="Changing the transition duration in a prototyping action"
const node = figma.currentPage.selection[0];
console.log(node.reactions);

/*
Output:

[{
  action: {
    type: 'NODE',
    destinationId: '4:1539',
    navigation: 'NAVIGATE',
    transition: {
      type:'SMART_ANIMATE',
      easing: { type: 'EASE_OUT' },
      duration: 0.20000000298023224
    },
    preserveScrollPosition: false
  },
  actions: [{
    type: 'NODE',
    destinationId: '4:1539',
    navigation: 'NAVIGATE',
    transition: {
      type:'SMART_ANIMATE',
      easing: { type: 'EASE_OUT' },
      duration: 0.20000000298023224
    },
    preserveScrollPosition: false
  }],
  trigger: { type: 'ON_CLICK' }
}]
*/

// See clone() implementation from the Editing Properties page
const newReactions = clone(node.reactions);
// highlight-start
newReactions[0].actions[0].transition.duration = 0.5;
// highlight-end
await node.setReactionsAsync(newReactions);
```

It is also possible to add Advanced Prototyping action types through the Plugin API: [Set Variable](https://help.figma.com/hc/en-us/articles/14506587589399-Use-variables-in-prototypes) and [Conditional](https://help.figma.com/hc/en-us/articles/15253220891799-Multiple-actions-and-conditionals).
Moreover, Reactions now include the ability to execute multiple actions by updating the `actions` field on a `Reaction`.

```ts title="Create a button with a Reaction object that updates the visibility of another Frame."
(async () => {
  // Create collection with "show" variable inside
  const collection = figma.variables.createVariableCollection("prototyping");
  const modeId = collection.modes[0].modeId;
  const showVariable = figma.variables.createVariable(
    "show",
    collection,
    "BOOLEAN"
  );

  // Initialize "show" variable to true
  showVariable.setValueForMode(modeId, true);

  const parentFrame = figma.createFrame();
  parentFrame.resize(350, 200);

  // Green "Click me" button
  const toggleButton = figma.createFrame();
  parentFrame.appendChild(toggleButton);
  toggleButton.x = 50;
  toggleButton.y = 50;
  toggleButton.layoutMode = "HORIZONTAL";
  toggleButton.layoutSizingHorizontal = "HUG";
  toggleButton.layoutSizingVertical = "HUG";
  toggleButton.fills = [{ type: "SOLID", color: { r: 0, g: 1, b: 0 } }];
  const text = figma.createText();
  await figma.loadFontAsync(text.fontName);
  text.characters = "Click me";
  toggleButton.appendChild(text);

  // Red square
  const frame = figma.createFrame();
  parentFrame.appendChild(frame);
  frame.x = 200;
  frame.y = 50;
  frame.fills = [{ type: "SOLID", color: { r: 1, g: 0, b: 0 } }];

  // The "show" variable will now control the visibility of the frame
  frame.setBoundVariable("visible", showVariable);

  await toggleButton.setReactionsAsync([
    {
      trigger: { type: "ON_CLICK" },
      actions: [
        {
          type: "CONDITIONAL",
          conditionalBlocks: [
            {
              condition: {
                // Conditional: if "show" variable == true
                type: "EXPRESSION",
                resolvedType: "BOOLEAN",
                value: {
                  expressionArguments: [
                    {
                      type: "VARIABLE_ALIAS",
                      resolvedType: "BOOLEAN",
                      value: {
                        type: "VARIABLE_ALIAS",
                        id: showVariable.id,
                      },
                    },
                    {
                      type: "BOOLEAN",
                      resolvedType: "BOOLEAN",
                      value: true,
                    },
                  ],
                  expressionFunction: "EQUALS",
                },
              },
              actions: [
                // then set "show" variable to false
                {
                  type: "SET_VARIABLE",
                  variableId: showVariable.id,
                  variableValue: {
                    resolvedType: "BOOLEAN",
                    type: "BOOLEAN",
                    value: false,
                  },
                },
              ],
            },
            {
              actions: [
                // else set "show" variable to true
                {
                  type: "SET_VARIABLE",
                  variableId: showVariable.id,
                  variableValue: {
                    resolvedType: "BOOLEAN",
                    type: "BOOLEAN",
                    value: true,
                  },
                },
              ],
            },
          ],
        },
      ],
    },
  ]);
})();
```

#### Inherited from

[`ReactionMixin`](ReactionMixin.md).[`reactions`](ReactionMixin.md#reactions)

---

### relativeTransform

> **relativeTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5704

The position of a node relative to its **containing parent** as a [Transform](../type-aliases/Transform.md) matrix. Not used for scaling, see `width` and `height` instead. Read the details page to understand the nuances of this property.

#### Remarks

### Scale

The `relativeTransform` is **not** used for scaling a node. The transform always has unit axes. That is, `sqrt(m00^2 + m10^2) == sqrt(m01^2 + m11^2) == 1`. In order to set the size of a node, use [LayoutMixin.resize](LayoutMixin.md#resize) or [LayoutMixin.resizeWithoutConstraints](LayoutMixin.md#resizewithoutconstraints).

Note: If you have a background in computer graphics, you may find it odd that we use the transform matrix in such a manner. This is because in 2D UI design, it's rare that you would want to scale the children when resizing a frame. And even if you did, it would be through more nuanced constraint settings that aren't captured by a transformation matrix.

Also, if nodes had both a `width` and a separate `m00` scale property, it would be confusing to the users which one they're changing, especially during interactions like dragging.

### Container parent

The relative transform of a node is shown relative to its container parent, which includes canvas nodes, frame nodes, component nodes, and instance nodes. Just like in the properties panel, it is **not** relative to its direct parent if the parent is a group or a boolean operation.

Example 1: In the following hierarchy, the relative transform of `rectangle` is relative to `page` (which is just its position on the canvas).

```text
page
  group
    rectangle
```

Example 2: In the following hierarchy, the relative transform of `rectangle` is relative to `frame`.

```text
page
  frame
    boolean operation
      rectangle
```

One implication is that to calculate the absolute position of a node, you have to either use the [DimensionAndPositionMixin.absoluteTransform](DimensionAndPositionMixin.md#absolutetransform) property or multiply relative transform matrices while traversing up the node hierarchy while ignoring groups and boolean operations.

Note: Why this complication? We do it this way because groups and boolean operations automatically resize to fit their children. While you _can_ set the relative transform of a group to move it, it's a property derived from the position and size of its children.
If the relative transform was always relative to it’s immediate parent, you could get into confusing situations where moving a layer inside a group by setting the relative transform changes the position of the parent, which then requires changing the relative transform of the child in order to preserve its on-screen position!

### Skew

While it is possible to skew a layer by setting `m00`, `m01`, `m10`, `m11` to the right values, be aware that the skew will not be surfaced in the properties panel and may be confusing to the user dealing with a skewed node.

### Auto-layout frames

The translation components `m02` and `m12` of the transform matrix is automatically computed in children of auto-layout frames. Setting `relativeTransform` on those layers will ignore the translation components, but do keep the rotation components.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`relativeTransform`](LayoutMixin.md#relativetransform)

---

### removed

> `readonly` **removed**: `boolean`

Defined in: figmaPluginTypes.ts:4911

Returns true if this node has been removed since it was first accessed. If your plugin stays open for a while and stores references to nodes, you should write your code defensively and check that the nodes haven't been removed by the user.

#### Remarks

A node can be removed for any number of reasons. Some examples:

- Your plugin called node.remove() on it
- Someone else deleted the node using multiplayer
- The user triggered an undo action and the node was removed
- The user simply deleted the node
- You removed all children out of a group, and the group auto-deleted itself

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`removed`](BaseNodeMixin.md#removed)

---

### resolvedVariableModes

> **resolvedVariableModes**: `object`

Defined in: figmaPluginTypes.ts:5292

The resolved mode for this node for each variable collection in this file.

#### Index Signature

\[`collectionId`: `string`\]: `string`

#### Remarks

The set of resolved modes on a node includes the explicitly set modes on the node, as well as the explicitly set modes on ancestors of the node. By default, nodes [automatically inherit](https://help.figma.com/hc/en-us/articles/15343816063383-Modes-for-variables#Auto_mode) the modes of their parents.

```ts title="explicitVariableModes vs resolvedVariableModes"
// Create two collections with two modes each
const collection1 = figma.variables.createVariableCollection("Collection 1");
const collection1Mode1Id = collection1.modes[0].modeId;
const collection1Mode2Id = collection1.addMode("Mode 2");
const collection2 = figma.variables.createVariableCollection("Collection 2");
const collection2Mode1Id = collection2.modes[0].modeId;
const collection2Mode2Id = collection2.addMode("Mode 2");

const parentFrame = figma.createFrame();
const childFrame = figma.createFrame();
parentFrame.appendChild(childFrame);

parentFrame.setExplicitVariableModeForCollection(
  collection1,
  collection1Mode2Id
);
childFrame.setExplicitVariableModeForCollection(
  collection2,
  collection2Mode1Id
);

// Example output (only collection2 is present):
// { 'VariableCollectionId:1:3': '1:2' }
console.log(childFrame.explicitVariableModes);

// Example output (both collections are present):
// { 'VariableCollectionId:1:2': '1:1', 'VariableCollectionId:1:3': '1:2' }
console.log(childFrame.resolvedVariableModes);
```

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`resolvedVariableModes`](SceneNodeMixin.md#resolvedvariablemodes)

---

### rotation

> **rotation**: `number`

Defined in: figmaPluginTypes.ts:5735

The rotation of the node in degrees. Returns values from -180 to 180. Identical to `Math.atan2(-m10, m00)` in the [DimensionAndPositionMixin.relativeTransform](DimensionAndPositionMixin.md#relativetransform) matrix. When setting `rotation`, it will also set `m00`, `m01`, `m10`, `m11`.

#### Remarks

The rotation is with respect to the top-left of the object. Therefore, it is independent from the position of the object. If you want to rotate with respect to the center (or any arbitrary point), you can do so via matrix transformations and [DimensionAndPositionMixin.relativeTransform](DimensionAndPositionMixin.md#relativetransform).

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`rotation`](LayoutMixin.md#rotation)

---

### stuckNodes

> `readonly` **stuckNodes**: [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5179

An array of nodes that are "stuck" to this node. In FigJam, stamps, highlights, and some widgets can "stick"
to other nodes if they are dragged on top of another node.

#### Remarks

This property is only available in FigJam.

In FigJam a stickable host that means that stickables, like `'STAMP'` nodes, are allowed to attach themselves to the node. If the stickable host moves all nodes that are in `stuckNodes` move along with it.

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`stuckNodes`](SceneNodeMixin.md#stucknodes)

---

### targetAspectRatio

> `readonly` **targetAspectRatio**: `null` \| [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:5905

When toggled, causes the layer to keep its proportions when the user resizes it via auto layout, constraints, the properties panel, or on-canvas.
If not set, the node does NOT resize toward a specific targetAspectRatio.

#### Remarks

Use `lockAspectRatio` and `unlockAspectRatio` to set targetAspectRatio.

```ts
const parentFrame = figma.createFrame();
const image = await figma.createNodeFromJSXAsync(
  <figma.widget.Image
    src="https://picsum.photos/200/300"
    width={200}
    height={300}
  />
);
parentFrame.appendChild(image);

image.lockAspectRatio(); // set to 2:3 ratio, implicit from the size

// Add autolayout to parent, which defaults to Hug x Hug
parentFrame.layoutMode = "HORIZONTAL";

// Set child to fill-width
image.layoutGrow = 1;

// Resize parent to be much larger
parentFrame.resize(500, 1000);

// Since the child is fill-width, it will expand to the available space
image.width == 500;
image.height == 750;
// Image maintains the 2:3 ratio even as it grew with auto layout!
```

Caution: ⚠️ `targetAspectRatio` cannot be used with auto-resizing text (TextNodes where textAutoResize !== NONE).

#### Inherited from

[`AspectRatioLockMixin`](AspectRatioLockMixin.md).[`targetAspectRatio`](AspectRatioLockMixin.md#targetaspectratio)

---

### type

> `readonly` **type**: `"GROUP"`

Defined in: figmaPluginTypes.ts:8480

The type of this node, represented by the string literal "GROUP".

---

### visible

> **visible**: `boolean`

Defined in: figmaPluginTypes.ts:5156

Whether the node is visible or not. Does not affect a plugin's ability to access the node.

#### Remarks

The value that this property returns is independent from the node's parent. i.e.

- The node isn't necessarily visible if this is `.visible === true`.
- The node isn't necessarily invisible if this is `.visible === false`.
- An object is visible if `.visible == true` for itself and **all** its parents.

#### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`visible`](SceneNodeMixin.md#visible)

---

### width

> `readonly` **width**: `number`

Defined in: figmaPluginTypes.ts:5638

The width of the node. Use a resizing method to change this value.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`width`](LayoutMixin.md#width)

---

### x

> **x**: `number`

Defined in: figmaPluginTypes.ts:5626

The position of the node. Identical to `relativeTransform[0][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`x`](LayoutMixin.md#x)

---

### y

> **y**: `number`

Defined in: figmaPluginTypes.ts:5634

The position of the node. Identical to `relativeTransform[1][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`y`](LayoutMixin.md#y)

## Methods

### addDevResourceAsync()

> **addDevResourceAsync**(`url`, `name?`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5100

Adds a dev resource to a node. This will fail if the node already has a dev resource with the same url.

#### Parameters

##### url

`string`

The url of the dev resource.

##### name?

`string`

The name of the dev resource. If not provided, Figma will get the name from the url.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`addDevResourceAsync`](BaseNodeMixin.md#adddevresourceasync)

---

### appendChild()

> **appendChild**(`child`): `void`

Defined in: figmaPluginTypes.ts:5381

Adds a new child to the end of the [ChildrenMixin.children](ChildrenMixin.md#children) array. That is, visually on top of all other children.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### child

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

`void`

#### Remarks

Reparenting nodes is subject to many restrictions. For example, some nodes cannot be moved, others would break the document if moved. Below are possible exceptions that can be thrown if the operation is invalid.

If this is called on an auto-layout frame, calling this function can cause this layer to be resized and children to be moved.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`appendChild`](ChildrenMixin.md#appendchild)

---

### clearExplicitVariableModeForCollection()

#### Call Signature

> **clearExplicitVariableModeForCollection**(`collectionId`): `void`

Defined in: figmaPluginTypes.ts:8258

Clears an explicit mode for the given collection on this node

##### Parameters

###### collectionId

`string`

##### Returns

`void`

##### Deprecated

Use `clearExplicitVariableModeForCollection(VariableCollection)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

##### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`clearExplicitVariableModeForCollection`](SceneNodeMixin.md#clearexplicitvariablemodeforcollection)

#### Call Signature

> **clearExplicitVariableModeForCollection**(`collection`): `void`

Defined in: figmaPluginTypes.ts:8264

Clears an explicit mode for the given collection on this node

##### Parameters

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a variable collection ID is deprecated.

##### Returns

`void`

##### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`clearExplicitVariableModeForCollection`](SceneNodeMixin.md#clearexplicitvariablemodeforcollection)

---

### clone()

> **clone**(): `GroupNode`

Defined in: figmaPluginTypes.ts:8484

Duplicates the group node. By default, the duplicate will be parented under `figma.currentPage`. Nested components will be cloned as instances who master is the original component.

#### Returns

`GroupNode`

---

### deleteDevResourceAsync()

> **deleteDevResourceAsync**(`url`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5122

Deletes a dev resource on a node. This will fail if the node does not have a dev resource with the same url.

#### Parameters

##### url

`string`

The url of the dev resource.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`deleteDevResourceAsync`](BaseNodeMixin.md#deletedevresourceasync)

---

### editDevResourceAsync()

> **editDevResourceAsync**(`currentUrl`, `newValue`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5109

Edits a dev resource on a node. This will fail if the node does not have a dev resource with the same url.

#### Parameters

##### currentUrl

`string`

The current url of the dev resource.

##### newValue

The new name and/or url of the dev resource.

###### name?

`string`

###### url?

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`editDevResourceAsync`](BaseNodeMixin.md#editdevresourceasync)

---

### exportAsync()

#### Call Signature

> **exportAsync**(`settings?`): `Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

Defined in: figmaPluginTypes.ts:6811

Exports the node as an encoded image.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

##### Parameters

###### settings?

[`ExportSettings`](../type-aliases/ExportSettings.md)

When this parameter is absent, this function defaults to exporting as a PNG at 1x resolution.

Note that the result is a Uint8Array, representing the bytes of the image file (encoded in the specified format).

```ts title="Create a hexagon, export as PNG, and place on canvas"
(async () => {
  const polygon = figma.createPolygon();
  polygon.pointCount = 6;
  polygon.fills = [{ type: "SOLID", color: { r: 1, g: 0, b: 0 } }];

  // highlight-start
  // Export a 2x resolution PNG of the node
  const bytes = await polygon.exportAsync({
    format: "PNG",
    constraint: { type: "SCALE", value: 2 },
  });
  // highlight-end

  // Add the image onto the canvas as an image fill in a frame
  const image = figma.createImage(bytes);
  const frame = figma.createFrame();
  frame.x = 200;
  frame.resize(200, 230);
  frame.fills = [
    {
      imageHash: image.hash,
      scaleMode: "FILL",
      scalingFactor: 1,
      type: "IMAGE",
    },
  ];
})();
```

```ts title="Export a VectorNode as an SVG string"
(async () => {
  // Create a triangle using the VectorPath API
  const vector = figma.createVector();
  vector.vectorPaths = [
    {
      windingRule: "EVENODD",
      data: "M 0 100 L 100 100 L 50 0 Z",
    },
  ];

  // highlight-start
  // Export the vector to SVG
  const svg = await vector.exportAsync({ format: "SVG_STRING" });
  // highlight-end
  console.log(svg);
})();
```

```ts title="Export a node as a JSON object"
(async () => {
  const json = await figma.currentPage.selection[0].exportAsync({
    format: "JSON_REST_V1",
  });
  // Return a JSON object in the same format as the Figma REST API response
  console.log(json.document);
})();
```

##### Returns

`Promise`\<`Uint8Array`\<`ArrayBufferLike`\>\>

##### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportAsync`](ExportMixin.md#exportasync)

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`string`\>

Defined in: figmaPluginTypes.ts:6812

##### Parameters

###### settings

[`ExportSettingsSVGString`](ExportSettingsSVGString.md)

##### Returns

`Promise`\<`string`\>

##### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportAsync`](ExportMixin.md#exportasync)

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`Object`\>

Defined in: figmaPluginTypes.ts:6813

##### Parameters

###### settings

[`ExportSettingsREST`](ExportSettingsREST.md)

##### Returns

`Promise`\<`Object`\>

##### Inherited from

[`ExportMixin`](ExportMixin.md).[`exportAsync`](ExportMixin.md#exportasync)

---

### findAll()

> **findAll**(`callback?`): [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5459

Searches this entire subtree (this node's children, its children's children, etc). Returns all nodes for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### callback?

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`. If this argument is omitted, `findAll` returns all nodes in the subtree.

#### Returns

[`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

Nodes are included in **back-to-front** order. Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

This traversal method is known as ["pre-order traversal"](<https://en.wikipedia.org/wiki/Tree_traversal#Pre-order_(NLR)>).

Note that the node this method is called on is **not included**.

Example: find all nodes whose name is "Color":

```ts
const colors = figma.currentPage.findAll((n) => n.name === "Color");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
If you only need to search immediate children, it is much faster to call `node.children.filter(callback)` or `node.findChildren(callback)`.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findAll`](ChildrenMixin.md#findall)

---

### findAllWithCriteria()

> **findAllWithCriteria**\<`T`\>(`criteria`): `object` & [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5582

Searches this entire subtree (this node's children, its children's children, etc). Returns all nodes that satisfy all of specified criteria.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Type Parameters

##### T

`T` _extends_ (`"TEXT"` \| `"DOCUMENT"` \| `"PAGE"` \| `"SLICE"` \| `"FRAME"` \| `"GROUP"` \| `"COMPONENT_SET"` \| `"COMPONENT"` \| `"INSTANCE"` \| `"BOOLEAN_OPERATION"` \| `"VECTOR"` \| `"STAR"` \| `"LINE"` \| `"ELLIPSE"` \| `"POLYGON"` \| `"RECTANGLE"` \| `"TEXT_PATH"` \| `"TRANSFORM_GROUP"` \| `"STICKY"` \| `"CONNECTOR"` \| `"SHAPE_WITH_TEXT"` \| `"CODE_BLOCK"` \| `"STAMP"` \| `"WIDGET"` \| `"EMBED"` \| `"LINK_UNFURL"` \| `"MEDIA"` \| `"SECTION"` \| `"HIGHLIGHT"` \| `"WASHI_TAPE"` \| `"TABLE"` \| `"SLIDE"` \| `"SLIDE_ROW"` \| `"SLIDE_GRID"` \| `"INTERACTIVE_SLIDE_ELEMENT"`)[]

#### Parameters

##### criteria

[`FindAllCriteria`](FindAllCriteria.md)\<`T`\>

An object of type [FindAllCriteria](FindAllCriteria.md) that specifies the search criteria. The following criterias are currently supported:

- Nodes with specific [types](../type-aliases/NodeType.md)
- Nodes with [SharedPluginData](PluginDataMixin.md#getsharedplugindata) by their namespace and keys.
- Nodes with [PluginData](PluginDataMixin.md#getplugindata) by their keys.
- A combination of any of the above.

#### Returns

`object` & [`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

This is a faster but more limited search compared to [ChildrenMixin.findAll](ChildrenMixin.md#findall), which lets you search nodes based on any logic you can include in a callback.

When paired with [`figma.skipInvisibleInstanceChildren = true`](https://www.figma.com/plugin-docs/api/properties/figma-skipinvisibleinstancechildren), this method can be hundreds of times faster in large documents with tens of thousands of nodes.

The return value is narrowly typed to match the provided `types`, which makes it much easier to use node-type-specific properties. For example, `node.findAllWithCriteria({ types: ['TEXT'] })` will return `TextNode[]` instead of the more generic `SceneNode[]` from [ChildrenMixin.findAll](ChildrenMixin.md#findall).

Nodes are included in **back-to-front** order, which is the same order as in [ChildrenMixin.findAll](ChildrenMixin.md#findall). Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

This traversal method is known as ["pre-order traversal"](<https://en.wikipedia.org/wiki/Tree_traversal#Pre-order_(NLR)>).

Note: The node this method is called on is **not included**.

## Example Usages

### Find by node type

```ts
// Find all component and component set nodes in the current
// page
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["COMPONENT", "COMPONENT_SET"],
});

// Find all text nodes in the current page
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["TEXT"],
});
```

### Find by plugin data

```ts
// Find all nodes in the current page with plugin data
// for the current plugin.
const nodes = figma.currentPage.findAllWithCriteria({
  pluginData: {},
});

// Find all nodes in the current page with plugin data
// for the current plugin with keys "a" or "b"
const nodes = figma.currentPage.findAllWithCriteria({
  pluginData: {
    keys: ["a", "b"],
  },
});
```

### Find by shared plugin data

```ts
// Find all nodes in the current page with shared plugin data
// stored on the "bar" namespace
const nodes = figma.currentPage.findAllWithCriteria({
  sharedPluginData: {
    namespace: "bar",
  },
});

// Find all nodes in the current page with shared plugin data
// stored on the "bar" namespace and keys "a" or "b"
const nodes = figma.currentPage.findAllWithCriteria({
  sharedPluginData: {
    namespace: "bar",
    keys: ["a", "b"],
  },
});
```

### Combining criterias

You can combine multiple criterias for further narrow your search.

```ts
// Find all text nodes in the current page with plugin data
// for the current plugin
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["TEXT"],
  pluginData: {},
});

// Find all text nodes in the current page with shared plugin data
// stored on the "bar" namespace
const nodes = figma.currentPage.findAllWithCriteria({
  types: ["TEXT"],
  sharedPluginData: {
    namespace: "bar",
  },
});
```

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findAllWithCriteria`](ChildrenMixin.md#findallwithcriteria)

---

### findChild()

> **findChild**(`callback`): `null` \| [`SceneNode`](../type-aliases/SceneNode.md)

Defined in: figmaPluginTypes.ts:5434

Searches the immediate children of this node (i.e. not including the children's children). Returns the first node for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### callback

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`.

#### Returns

`null` \| [`SceneNode`](../type-aliases/SceneNode.md)

#### Remarks

This function returns `null` if no matching node is found.

Example: find the first frame that is an immediate child of the current page.

```ts
const firstChildFrame = figma.currentPage.findChild((n) => n.type === "FRAME");
```

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findChild`](ChildrenMixin.md#findchild)

---

### findChildren()

> **findChildren**(`callback?`): [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5417

Searches the immediate children of this node (i.e. not including the children's children). Returns all nodes for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### callback?

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`. If this argument is omitted, `findChildren` returns `node.children`.

#### Returns

[`SceneNode`](../type-aliases/SceneNode.md)[]

#### Remarks

Example: find all frames that are immediate child of the current page.

```ts
const childFrames = figma.currentPage.findChildren((n) => n.type === "FRAME");
```

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findChildren`](ChildrenMixin.md#findchildren)

---

### findOne()

> **findOne**(`callback`): `null` \| [`SceneNode`](../type-aliases/SceneNode.md)

Defined in: figmaPluginTypes.ts:5481

Searches this entire subtree (this node's children, its children's children, etc). Returns the first node for which `callback` returns true.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### callback

(`node`) => `boolean`

A function that evaluates whether to return the provided `node`.

#### Returns

`null` \| [`SceneNode`](../type-aliases/SceneNode.md)

#### Remarks

This function returns `null` if no matching node is found. The traversal order is the same as in [ChildrenMixin.findAll](ChildrenMixin.md#findall).

Note that the node this method is called on is **not included**.

Example: find one node whose name is "Template":

```ts
const template = figma.currentPage.findOne((n) => n.name === "Template");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
If you only need to search immediate children, it is much faster to call `node.children.find(callback)` or `node.findChild(callback)`.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findOne`](ChildrenMixin.md#findone)

---

### findWidgetNodesByWidgetId()

> **findWidgetNodesByWidgetId**(`widgetId`): [`WidgetNode`](WidgetNode.md)[]

Defined in: figmaPluginTypes.ts:5600

Searches this entire subtree (this node's children, its children's children, etc). Returns all widget nodes that match the provided `widgetId`.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### widgetId

`string`

The widget ID to search for, which represents unique identifier for the widget.

#### Returns

[`WidgetNode`](WidgetNode.md)[]

#### Remarks

`node.widgetId` is not to be confused with `node.id`, which is the unique identifier for the node on the canvas. In other words, if you clone a widget, the cloned widget will have a matching `widgetId` but a different `id`.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`findWidgetNodesByWidgetId`](ChildrenMixin.md#findwidgetnodesbywidgetid)

---

### getCSSAsync()

> **getCSSAsync**(): `Promise`\<\{[`key`: `string`]: `string`; \}\>

Defined in: figmaPluginTypes.ts:5014

Resolves to a JSON object of CSS properties of the node. This is the same CSS that Figma shows in the inspect panel and is helpful if you are building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

#### Returns

`Promise`\<\{[`key`: `string`]: `string`; \}\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getCSSAsync`](BaseNodeMixin.md#getcssasync)

---

### getDevResourcesAsync()

> **getDevResourcesAsync**(`options?`): `Promise`\<[`DevResourceWithNodeId`](DevResourceWithNodeId.md)[]\>

Defined in: figmaPluginTypes.ts:5091

Gets all of the dev resources on a node. This includes any inherited dev resources from components and component sets.

#### Parameters

##### options?

An optional parameter to include getting all of the dev resources on the children of the node. Defaults to false.

###### includeChildren?

`boolean`

#### Returns

`Promise`\<[`DevResourceWithNodeId`](DevResourceWithNodeId.md)[]\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getDevResourcesAsync`](BaseNodeMixin.md#getdevresourcesasync)

---

### getPluginData()

> **getPluginData**(`key`): `string`

Defined in: figmaPluginTypes.ts:5031

Retrieves custom information that was stored on this node or style using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). If there is no data stored for the provided key, an empty string is returned.

#### Parameters

##### key

`string`

#### Returns

`string`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getPluginData`](BaseNodeMixin.md#getplugindata)

---

### getPluginDataKeys()

> **getPluginDataKeys**(): `string`[]

Defined in: figmaPluginTypes.ts:5053

Retrieves a list of all keys stored on this node or style using using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). This enables iterating through all data stored privately on a node or style by your plugin.

#### Returns

`string`[]

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getPluginDataKeys`](BaseNodeMixin.md#getplugindatakeys)

---

### getRelaunchData()

> **getRelaunchData**(): `object`

Defined in: figmaPluginTypes.ts:5000

Retreives the reluanch data stored on this node using [BaseNodeMixin.setRelaunchData](BaseNodeMixin.md#setrelaunchdata)

#### Returns

`object`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getRelaunchData`](BaseNodeMixin.md#getrelaunchdata)

---

### getSharedPluginData()

> **getSharedPluginData**(`namespace`, `key`): `string`

Defined in: figmaPluginTypes.ts:5057

Retrieves custom information that was stored on this node or style using [PluginDataMixin.setSharedPluginData](PluginDataMixin.md#setsharedplugindata). If there is no data stored for the provided namespace and key, an empty string is returned.

#### Parameters

##### namespace

`string`

##### key

`string`

#### Returns

`string`

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getSharedPluginData`](BaseNodeMixin.md#getsharedplugindata)

---

### getSharedPluginDataKeys()

> **getSharedPluginDataKeys**(`namespace`): `string`[]

Defined in: figmaPluginTypes.ts:5079

Retrieves a list of all keys stored on this node or style using [PluginDataMixin.setSharedPluginData](PluginDataMixin.md#setsharedplugindata). This enables iterating through all data stored in a given namespace.

#### Parameters

##### namespace

`string`

#### Returns

`string`[]

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getSharedPluginDataKeys`](BaseNodeMixin.md#getsharedplugindatakeys)

---

### getTopLevelFrame()

> **getTopLevelFrame**(): `undefined` \| [`FrameNode`](FrameNode.md)

Defined in: figmaPluginTypes.ts:5022

Returns the top-most frame that contains this node. If the node is not inside a frame, this will return undefined.

Note: This function will only work in Figma Design and will throw an error if called in FigJam or Slides.

#### Returns

`undefined` \| [`FrameNode`](FrameNode.md)

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`getTopLevelFrame`](BaseNodeMixin.md#gettoplevelframe)

---

### insertChild()

> **insertChild**(`index`, `child`): `void`

Defined in: figmaPluginTypes.ts:5402

Adds a new child at the specified index in the [ChildrenMixin.children](ChildrenMixin.md#children) array.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### index

`number`

Determines where the new layer gets inserted. For example, suppose a group has layers A, B, C, where C is the top-most layer.

- `insertChild(0, D)` gives a group with layers **D**, A, B, C
- `insertChild(1, D)` gives a group with layers A, **D**, B, C
- `insertChild(2, D)` gives a group with layers A, B, **D**, C
- `insertChild(3, D)` gives a group with layers A, B, C, **D**
- `insertChild(4, D)` throws an error since the group originally only has 3 children

##### child

[`SceneNode`](../type-aliases/SceneNode.md)

The node to be inserted.

#### Returns

`void`

#### Remarks

Reparenting nodes is subject to many restrictions. For example, some nodes cannot be moved, others would break the document if moved. Below are possible exceptions that can be thrown if the operation is invalid.

If this is called on an auto-layout frame, calling this function can cause this layer to be resized and children to be moved.

#### Inherited from

[`ChildrenMixin`](ChildrenMixin.md).[`insertChild`](ChildrenMixin.md#insertchild)

---

### lockAspectRatio()

> **lockAspectRatio**(): `void`

Defined in: figmaPluginTypes.ts:5909

Locks the node's `targetAspectRatio` to the current ratio of its width and height.

#### Returns

`void`

#### Inherited from

[`AspectRatioLockMixin`](AspectRatioLockMixin.md).[`lockAspectRatio`](AspectRatioLockMixin.md#lockaspectratio)

---

### remove()

> **remove**(): `void`

Defined in: figmaPluginTypes.ts:4933

Removes this node and **all of its children** from the document.

#### Returns

`void`

#### Remarks

If you want to only remove this node but not its children, you will have to first move them to another node before calling `remove()`.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`remove`](BaseNodeMixin.md#remove)

---

### rescale()

> **rescale**(`scale`): `void`

Defined in: figmaPluginTypes.ts:5861

Rescales the node. This API function is the equivalent of using the Scale Tool from the toolbar.

#### Parameters

##### scale

`number`

The scale by which to resize the node from the top-left corner.

#### Returns

`void`

#### Remarks

The scale factor must be >= 0.01

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`rescale`](LayoutMixin.md#rescale)

---

### resize()

> **resize**(`width`, `height`): `void`

Defined in: figmaPluginTypes.ts:5836

Resizes the node. If the node contains children with constraints, it applies those constraints during resizing. If the parent has auto-layout, causes the parent to be resized.

#### Parameters

##### width

`number`

New width of the node. Must be >= 0.01

##### height

`number`

New height of the node. Must be >= 0.01, except for [LineNode](LineNode.md) which must always be given a height of exactly 0.

#### Returns

`void`

#### Remarks

Since this function applies constraints recursively (when there are multiple levels of nested frames with constraints), calls to this function could be expensive. Use [LayoutMixin.resizeWithoutConstraints](LayoutMixin.md#resizewithoutconstraints) if you don't need to apply constraints.

Caution: ⚠️ If this node is a text node with a missing font or contains a text node with a missing font, the text node will be resized but the text will not re-layout until the next time the text node is opened on a machine that _has_ the font. This can cause the text node to re-layout immediately and be surprising to your user. Consider checking if the document [PluginAPI.hasMissingFont](PluginAPI.md#hasmissingfont) before using this function.

Ignores `targetAspectRatio`. If `targetAspectRatio` has been set, it will be updated to correspond to the post-resize value.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`resize`](LayoutMixin.md#resize)

---

### resizeWithoutConstraints()

> **resizeWithoutConstraints**(`width`, `height`): `void`

Defined in: figmaPluginTypes.ts:5851

Resizes the node. Children of the node are never resized, even if those children have constraints. If the parent has auto-layout, causes the parent to be resized (this constraint cannot be ignored).

#### Parameters

##### width

`number`

New width of the node. Must be >= 0.01

##### height

`number`

New height of the node. Must be >= 0.01, except for [LineNode](LineNode.md) which must always be given a height of exactly 0.

#### Returns

`void`

#### Remarks

This function will not cause its children to resize. Use [LayoutMixin.resize](LayoutMixin.md#resize) if you need to apply constraints.

Caution: ⚠️ If this node is a text node with a missing font, the text node will be resized but the text will not re-layout until the next time the text node is opened on a machine that _has_ the font. This can cause the text node to re-layout immediately and be surprising to your user. Consider checking the text node property [`hasMissingFont`](https://www.figma.com/plugin-docs/api/TextNode#hasmissingfont) before using this function.

Ignores `targetAspectRatio`. If `targetAspectRatio` has been set, it will be updated to correspond to the post-resize value.

#### Inherited from

[`LayoutMixin`](LayoutMixin.md).[`resizeWithoutConstraints`](LayoutMixin.md#resizewithoutconstraints)

---

### setBoundVariable()

#### Call Signature

> **setBoundVariable**(`field`, `variableId`): `void`

Defined in: figmaPluginTypes.ts:5214

Binds the provided `field` on this node to the given variable. Please see the [Working with Variables](https://www.figma.com/plugin-docs/working-with-variables) guide for how to get and set variable bindings.

##### Parameters

###### field

[`VariableBindableTextField`](../type-aliases/VariableBindableTextField.md) | [`VariableBindableNodeField`](../type-aliases/VariableBindableNodeField.md)

###### variableId

`null` | `string`

##### Returns

`void`

##### Deprecated

Use `setBoundVariable(VariableBindableNodeField, Variable)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

##### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`setBoundVariable`](SceneNodeMixin.md#setboundvariable)

#### Call Signature

> **setBoundVariable**(`field`, `variable`): `void`

Defined in: figmaPluginTypes.ts:5226

Binds the provided `field` on this node to the given variable. Please see the [Working with Variables](https://www.figma.com/plugin-docs/working-with-variables) guide for how to get and set variable bindings.

If `null` is provided as the variable, the given `field` will be unbound from any variables.

##### Parameters

###### field

The field to bind the variable to.

[`VariableBindableTextField`](../type-aliases/VariableBindableTextField.md) | [`VariableBindableNodeField`](../type-aliases/VariableBindableNodeField.md)

###### variable

The variable to bind to the field. If `null` is provided, the field will be unbound from any variables. Make sure to pass a Variable object or null; passing a variable ID is deprecated.

`null` | [`Variable`](Variable.md)

##### Returns

`void`

##### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`setBoundVariable`](SceneNodeMixin.md#setboundvariable)

---

### setDevResourcePreviewAsync()

> **setDevResourcePreviewAsync**(`url`, `preview`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5127

Caution: This is a private API only available to [Figma partners](https://www.figma.com/partners/)

#### Parameters

##### url

`string`

##### preview

[`PlainTextElement`](../type-aliases/PlainTextElement.md)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setDevResourcePreviewAsync`](BaseNodeMixin.md#setdevresourcepreviewasync)

---

### setEffectStyleIdAsync()

> **setEffectStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5977

Set the [EffectStyle](EffectStyle.md) that the properties of this node are linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`BlendMixin`](BlendMixin.md).[`setEffectStyleIdAsync`](BlendMixin.md#seteffectstyleidasync)

---

### setExplicitVariableModeForCollection()

#### Call Signature

> **setExplicitVariableModeForCollection**(`collectionId`, `modeId`): `void`

Defined in: figmaPluginTypes.ts:8270

Sets an explicit mode for the given collection on this node

##### Parameters

###### collectionId

`string`

###### modeId

`string`

##### Returns

`void`

##### Deprecated

Use `setExplicitVariableModeForCollection(VariableCollection, Variable)` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

##### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`setExplicitVariableModeForCollection`](SceneNodeMixin.md#setexplicitvariablemodeforcollection)

#### Call Signature

> **setExplicitVariableModeForCollection**(`collection`, `modeId`): `void`

Defined in: figmaPluginTypes.ts:8277

Sets an explicit mode for the given collection on this node

##### Parameters

###### collection

[`VariableCollection`](VariableCollection.md)

A variable collection. Make sure to pass a collection object here; passing a variable collection ID is deprecated.

###### modeId

`string`

A variable mode ID.

##### Returns

`void`

##### Inherited from

[`SceneNodeMixin`](SceneNodeMixin.md).[`setExplicitVariableModeForCollection`](SceneNodeMixin.md#setexplicitvariablemodeforcollection)

---

### setPluginData()

> **setPluginData**(`key`, `value`): `void`

Defined in: figmaPluginTypes.ts:5049

Lets you store custom information on any node or style, **private** to your plugin. The total size of your entry (`pluginId`, `key`, `value`) cannot exceed 100 kB.

#### Parameters

##### key

`string`

The key under which to store the data. This is similar to writing to a plain object via `obj[key] = value`.

##### value

`string`

The data you want to store. If you want to store a value type other than a string, encode it as a JSON string first via `JSON.stringify` and `JSON.parse`. If you set the value to the empty string (""), the key/value pair is removed.

#### Returns

`void`

#### Remarks

The data is specific to your plugin ID. Plugins with other IDs won't be able to read this data. You can retrieve it later by calling `getPluginData` with the same key. To find all data stored on a node or style by your plugin use `getPluginDataKeys`.

Caution: ⚠ The data is stored privately for **stability**, not **security**. It prevents other plugins from accessing with your data. It does not, however, prevent users from seeing the data given sufficient effort. For example, they could export the document as a .fig file and try to decode it.

Caution: ⚠ Data will become inaccessible if your plugin ID changes.

Caution: ⚠ Total entry size cannot exceed 100 kB.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setPluginData`](BaseNodeMixin.md#setplugindata)

---

### setReactionsAsync()

> **setReactionsAsync**(`reactions`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:7031

Updates the reactions on this node. See [ReactionMixin.reactions](ReactionMixin.md#reactions) for a usage example.

#### Parameters

##### reactions

[`Reaction`](../type-aliases/Reaction.md)[]

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`ReactionMixin`](ReactionMixin.md).[`setReactionsAsync`](ReactionMixin.md#setreactionsasync)

---

### setRelaunchData()

> **setRelaunchData**(`data`): `void`

Defined in: figmaPluginTypes.ts:4996

Sets state on the node to show a button and description when the node is selected. Clears the button and description when `relaunchData` is `{}`.

Note: In Figma and Dev Mode, this shows up in the properties panel. In FigJam, this shows up in the property menu. See [here](https://www.figma.com/plugin-docs/api/properties/nodes-setrelaunchdata#example-figma-design-ui) for examples.

#### Parameters

##### data

```ts
{
  [command: string]: string // description
}
```

e.g. `data = { myCommand: 'Short description' }`

#### Returns

`void`

#### Remarks

Each call to this method sets entirely new relaunch data, removing any relaunch data and associated buttons/descriptions from before. To maintain buttons from a previous call one can store the button information using [setPluginData](https://www.figma.com/plugin-docs/api/properties/nodes-setplugindata/) and later fetch it with [getPluginData](https://www.figma.com/plugin-docs/api/PageNode/#getplugindata) before passing it on to `setRelaunchData`.

To use this API, the plugin manifest must include a `relaunchButtons` section: see the [manifest guide](https://www.figma.com/plugin-docs/manifest#relaunchbuttons) for more information.

Note: Note that if the `command` passed to this method does not match a command in the manifest, nothing will be displayed. Similarly if the name of a command in the manifest changes or is removed, then all buttons with that command will disappear. This behavior can be used to remove buttons when a particular action is no longer supported by the plugin.

In Figma design, the relaunch data can also be placed on the [PageNode](PageNode.md) or [DocumentNode](DocumentNode.md), to show a button and description when nothing is selected. Relaunch buttons added to the [PageNode](PageNode.md) will be displayed on that page, combined with buttons from the [DocumentNode](DocumentNode.md) that show on every page. This is not supported in FigJam.

## Examples

```ts title="manifest.json"
// With the following in the manifest:
"relaunchButtons": [
  {"command": "edit", "name": "Edit shape"},
  {"command": "open", "name": "Open Shaper", "multipleSelection": true}
]
```

```ts title="code.ts"
// Add two buttons (ordered by the above array from the manifest):
// * an "Edit shape" button with a description of "Edit this trapezoid
//   with Shaper" that runs the plugin with `figma.command === 'edit'`.
// * an "Open Shaper" button with no description that runs the plugin with
//   `figma.command === 'open'`.
node.setRelaunchData({ edit: 'Edit this trapezoid with Shaper', open: '' })

// With the following in the manifest:
"relaunchButtons": [
  {"command": "relaunch", "name": "Run again", "multipleSelection": true}
]

// Pass an empty description to show only a button
node.setRelaunchData({ relaunch: '' })

// Remove the button and description
node.setRelaunchData({})
```

### Example Figma Design UI

![Relaunch UI in Figma Design](https://www.figma.com/plugin-docs/img/relaunch_ui_design.png)

### Example FigJam UI

![Relaunch UI in FigJam](https://www.figma.com/plugin-docs/img/relaunch_ui_figjam.png)

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setRelaunchData`](BaseNodeMixin.md#setrelaunchdata)

---

### setSharedPluginData()

> **setSharedPluginData**(`namespace`, `key`, `value`): `void`

Defined in: figmaPluginTypes.ts:5075

Lets you store custom information on any node or style, **public** to all plugins. The total size of your entry (`namespace`, `key`, `value`) cannot exceed 100 kB.

#### Parameters

##### namespace

`string`

A unique string to identify your plugin and avoid key collisions with other plugins. The namespace must be at least 3 alphanumeric characters.

##### key

`string`

The key under which to store the data. This is similar to writing to a plain object via `obj[key] = value`.

##### value

`string`

The data you want to store. If you want to store a value type other than a string, encode it as a JSON string first via `JSON.stringify` and `JSON.parse`. If you set the value to the empty string (""), the key/value pair is removed.

#### Returns

`void`

#### Remarks

This lets you store custom information on any node or style. You can retrieve it later by calling [PluginDataMixin.getSharedPluginData](PluginDataMixin.md#getsharedplugindata) with the same namespace and key. To find all data stored on a node or style in a particular namespace, use [PluginDataMixin.getSharedPluginDataKeys](PluginDataMixin.md#getsharedplugindatakeys).

Any data you write using this API will be readable by any plugin. The intent is to allow plugins to interoperate with each other. Use [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata) instead if you don't want other plugins to be able to read your data.

You must also provide a `namespace` argument to avoid key collisions with other plugins. This argument is mandatory to prevent multiple plugins from using generic key names like `data` and overwriting one another. We recommend passing a value that identifies your plugin. This namespace can be given to authors of other plugins so that they can read data from your plugin.

Caution: ⚠ Total entry size cannot exceed 100 kB.

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`setSharedPluginData`](BaseNodeMixin.md#setsharedplugindata)

---

### toString()

> **toString**(): `string`

Defined in: figmaPluginTypes.ts:4925

Returns a string representation of the node. For debugging purposes only, do not rely on the exact output of this string in production code.

#### Returns

`string`

#### Remarks

This currently returns a string of the form `[Node ID]` where `ID` is the id of the node. This is just for debugging convenience so the node displays something useful when converted to a string. We recommend not relying on this in production.

Example:

```ts
// e.g. [Node 0:5]
console.log(`Current selected node ${figma.currentPage.selection[0]}`);
```

#### Inherited from

[`BaseNodeMixin`](BaseNodeMixin.md).[`toString`](BaseNodeMixin.md#tostring)

---

### unlockAspectRatio()

> **unlockAspectRatio**(): `void`

Defined in: figmaPluginTypes.ts:5913

Unlocks the node's `targetAspectRatio`.

#### Returns

`void`

#### Inherited from

[`AspectRatioLockMixin`](AspectRatioLockMixin.md).[`unlockAspectRatio`](AspectRatioLockMixin.md#unlockaspectratio)
