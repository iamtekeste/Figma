---

SectionNode

# Interface: SectionNode

Defined in: figmaPluginTypes.ts:9813

## See

https://www.figma.com/plugin-docs/api/SectionNode

## Extends

- [`ChildrenMixin`](ChildrenMixin.md).[`MinimalFillsMixin`](MinimalFillsMixin.md).[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`DevStatusMixin`](DevStatusMixin.md).[`AspectRatioLockMixin`](AspectRatioLockMixin.md)

## Properties

### absoluteBoundingBox

> `readonly` **absoluteBoundingBox**: `null` \| [`Rect`](Rect.md)

Defined in: figmaPluginTypes.ts:5712

The bounds of the node that does not include rendered properties like drop shadows or strokes. The `x` and `y` inside this property represent the absolute position of the node on the page.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`absoluteBoundingBox`](OpaqueNodeMixin.md#absoluteboundingbox)

---

### absoluteTransform

> `readonly` **absoluteTransform**: [`Transform`](../type-aliases/Transform.md)

Defined in: figmaPluginTypes.ts:5708

The position of a node relative to its **containing page** as a [Transform](../type-aliases/Transform.md) matrix.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`absoluteTransform`](OpaqueNodeMixin.md#absolutetransform)

---

### attachedConnectors

> `readonly` **attachedConnectors**: [`ConnectorNode`](ConnectorNode.md)[]

Defined in: figmaPluginTypes.ts:5183

An array of `ConnectorNode`s that are attached to a node.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`attachedConnectors`](OpaqueNodeMixin.md#attachedconnectors)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`boundVariables`](OpaqueNodeMixin.md#boundvariables)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`componentPropertyReferences`](OpaqueNodeMixin.md#componentpropertyreferences)

---

### devStatus

> **devStatus**: [`DevStatus`](../type-aliases/DevStatus.md)

Defined in: figmaPluginTypes.ts:5140

Whether the node is marked [ready for development](https://help.figma.com/hc/en-us/articles/15023124644247-Guide-to-Dev-Mode#01H8CR3K6V9S02RK503QCX0367) or [completed](https://help.figma.com/hc/en-us/articles/15023124644247-Guide-to-Dev-Mode#01H8CR3K6V9S02RK503QCX0367).

There are some restrictions on how `devStatus` can be set:

- Can only be set on a node directly under a page or section
- Cannot be set on a node that is inside another node that already has a `devStatus`

#### Inherited from

[`DevStatusMixin`](DevStatusMixin.md).[`devStatus`](DevStatusMixin.md#devstatus)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`explicitVariableModes`](OpaqueNodeMixin.md#explicitvariablemodes)

---

### exportSettings

> **exportSettings**: readonly [`ExportSettings`](../type-aliases/ExportSettings.md)[]

Defined in: figmaPluginTypes.ts:6748

List of export settings stored on the node. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`exportSettings`](OpaqueNodeMixin.md#exportsettings)

---

### fills

> **fills**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:6658

The paints used to fill the area of the shape. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

#### Remarks

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if the node has multiple sets of fills. Text nodes can have multiple sets of fills if some characters are colored differently than others.

Use [UtilAPI.solidPaint](UtilAPI.md#solidpaint) to create solid paint fills with CSS color strings.

Page nodes have a [`backgrounds`](https://www.figma.com/plugin-docs/api/PageNode/#backgrounds) property instead of a `fills` property.

#### Inherited from

[`MinimalFillsMixin`](MinimalFillsMixin.md).[`fills`](MinimalFillsMixin.md#fills)

---

### fillStyleId

> **fillStyleId**: `string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:6668

The id of the [PaintStyle](PaintStyle.md) object that the [MinimalFillsMixin.fills](MinimalFillsMixin.md#fills) property of this node is linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setFillStyleIdAsync` to update the style.

#### Remarks

This property can return [PluginAPI.mixed](PluginAPI.md#mixed) if the node has multiple fills.properties. Text nodes can have multiple fills if some characters are colored differently than others.

#### Inherited from

[`MinimalFillsMixin`](MinimalFillsMixin.md).[`fillStyleId`](MinimalFillsMixin.md#fillstyleid)

---

### height

> `readonly` **height**: `number`

Defined in: figmaPluginTypes.ts:5642

The height of the node. Use a resizing method to change this value.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`height`](OpaqueNodeMixin.md#height)

---

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:4878

The unique identifier of a node. For example, `1:3`. The node id can be used with methods such as [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync), but plugins typically don't need to use this since you can usually just access a node directly.

#### Remarks

One possible use case for using the `id` is to have a serializable representation of a Figma node. To "deserialize" an id back into a node, pass it to [PluginAPI.getNodeByIdAsync](PluginAPI.md#getnodebyidasync). This will return null if the node is no longer present in the document.

In the URLs for Figma files, node ids are hyphenated. However, for use with the API, node ids must use colons. For example, if a Figma file URL has the node id `1-3`, you must convert it to `1:3`.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`id`](OpaqueNodeMixin.md#id)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`inferredVariables`](OpaqueNodeMixin.md#inferredvariables)

---

### isAsset

> `readonly` **isAsset**: `boolean`

Defined in: figmaPluginTypes.ts:5010

Returns true if Figma detects that a node is an asset, otherwise returns false. An asset is is either an icon or a raster image.

This property is useful if you’re building a [plugin for code generation](https://www.figma.com/plugin-docs/codegen-plugins).

Note: This property uses a set of heuristics to determine if a node is an asset. At a high level an icon is a small vector graphic and an image is a node with an image fill.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`isAsset`](OpaqueNodeMixin.md#isasset)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`locked`](OpaqueNodeMixin.md#locked)

---

### maxHeight

> **maxHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5658

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxHeight`.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`maxHeight`](OpaqueNodeMixin.md#maxheight)

---

### maxWidth

> **maxWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5650

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `maxWidth`.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`maxWidth`](OpaqueNodeMixin.md#maxwidth)

---

### minHeight

> **minHeight**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5654

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to null to remove `minHeight`.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`minHeight`](OpaqueNodeMixin.md#minheight)

---

### minWidth

> **minWidth**: `null` \| `number`

Defined in: figmaPluginTypes.ts:5646

Applicable only to auto-layout frames and their direct children. Value must be positive. Set to `null` to remove `minWidth`.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`minWidth`](OpaqueNodeMixin.md#minwidth)

---

### name

> **name**: `string`

Defined in: figmaPluginTypes.ts:4898

The name of the layer that appears in the layers panel. Calling `figma.root.name` will return the name, read-only, of the current file.

#### Remarks

If the node is a [TextNode](TextNode.md), the name will update automatically by default based on the `characters` property (`autoRename` is true). If you manually override the text node's name, it will set `autoRename` to false. This matches the behavior in the editor.

If the node is a [PageNode](PageNode.md) with no children and the name is a page divider name, it will set `isPageDivider` to true. A page divider name consists of all asterisks, all en dashes, all em dashes, or all spaces.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`name`](OpaqueNodeMixin.md#name)

---

### parent

> `readonly` **parent**: `null` \| BaseNode & ChildrenMixin

Defined in: figmaPluginTypes.ts:4888

Returns the parent of this node, if any. This property is not meant to be directly edited. To reparent, see [ChildrenMixin.appendChild](ChildrenMixin.md#appendchild).

#### Remarks

The root node (i.e. `figma.root`) doesn't have a parent.

Components accessed via [instance.getMainComponentAsync()](InstanceNode.md#getmaincomponentasync) or [instance.mainComponent](InstanceNode.md#maincomponent) do not always have a parent. They could be remote components or soft-deleted components.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`parent`](OpaqueNodeMixin.md#parent)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`relativeTransform`](OpaqueNodeMixin.md#relativetransform)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`removed`](OpaqueNodeMixin.md#removed)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`resolvedVariableModes`](OpaqueNodeMixin.md#resolvedvariablemodes)

---

### sectionContentsHidden

> **sectionContentsHidden**: `boolean`

Defined in: figmaPluginTypes.ts:9826

Whether the section node contents are [marked as hidden](https://help.figma.com/hc/en-us/articles/4939765379351-Organize-your-FigJam-board-with-sections#Hide_section).

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`stuckNodes`](OpaqueNodeMixin.md#stucknodes)

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

> `readonly` **type**: `"SECTION"`

Defined in: figmaPluginTypes.ts:9822

The type of this node, represented by the string literal "SECTION"

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`visible`](OpaqueNodeMixin.md#visible)

---

### width

> `readonly` **width**: `number`

Defined in: figmaPluginTypes.ts:5638

The width of the node. Use a resizing method to change this value.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`width`](OpaqueNodeMixin.md#width)

---

### x

> **x**: `number`

Defined in: figmaPluginTypes.ts:5626

The position of the node. Identical to `relativeTransform[0][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`x`](OpaqueNodeMixin.md#x)

---

### y

> **y**: `number`

Defined in: figmaPluginTypes.ts:5634

The position of the node. Identical to `relativeTransform[1][2]`.

#### Remarks

This value is automatically computed in children of auto-layout frames. Setting this property for these auto-layout children will no-op.

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`y`](OpaqueNodeMixin.md#y)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`addDevResourceAsync`](OpaqueNodeMixin.md#adddevresourceasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`clearExplicitVariableModeForCollection`](OpaqueNodeMixin.md#clearexplicitvariablemodeforcollection)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`clearExplicitVariableModeForCollection`](OpaqueNodeMixin.md#clearexplicitvariablemodeforcollection)

---

### clone()

> **clone**(): `SectionNode`

Defined in: figmaPluginTypes.ts:9830

Create a copy of this node. By default, the duplicate will be parented under `figma.currentPage`.

#### Returns

`SectionNode`

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`deleteDevResourceAsync`](OpaqueNodeMixin.md#deletedevresourceasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`editDevResourceAsync`](OpaqueNodeMixin.md#editdevresourceasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`exportAsync`](OpaqueNodeMixin.md#exportasync)

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`string`\>

Defined in: figmaPluginTypes.ts:6812

##### Parameters

###### settings

[`ExportSettingsSVGString`](ExportSettingsSVGString.md)

##### Returns

`Promise`\<`string`\>

##### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`exportAsync`](OpaqueNodeMixin.md#exportasync)

#### Call Signature

> **exportAsync**(`settings`): `Promise`\<`Object`\>

Defined in: figmaPluginTypes.ts:6813

##### Parameters

###### settings

[`ExportSettingsREST`](ExportSettingsREST.md)

##### Returns

`Promise`\<`Object`\>

##### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`exportAsync`](OpaqueNodeMixin.md#exportasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getCSSAsync`](OpaqueNodeMixin.md#getcssasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getDevResourcesAsync`](OpaqueNodeMixin.md#getdevresourcesasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getPluginData`](OpaqueNodeMixin.md#getplugindata)

---

### getPluginDataKeys()

> **getPluginDataKeys**(): `string`[]

Defined in: figmaPluginTypes.ts:5053

Retrieves a list of all keys stored on this node or style using using [PluginDataMixin.setPluginData](PluginDataMixin.md#setplugindata). This enables iterating through all data stored privately on a node or style by your plugin.

#### Returns

`string`[]

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getPluginDataKeys`](OpaqueNodeMixin.md#getplugindatakeys)

---

### getRelaunchData()

> **getRelaunchData**(): `object`

Defined in: figmaPluginTypes.ts:5000

Retreives the reluanch data stored on this node using [BaseNodeMixin.setRelaunchData](BaseNodeMixin.md#setrelaunchdata)

#### Returns

`object`

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getRelaunchData`](OpaqueNodeMixin.md#getrelaunchdata)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getSharedPluginData`](OpaqueNodeMixin.md#getsharedplugindata)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getSharedPluginDataKeys`](OpaqueNodeMixin.md#getsharedplugindatakeys)

---

### getTopLevelFrame()

> **getTopLevelFrame**(): `undefined` \| [`FrameNode`](FrameNode.md)

Defined in: figmaPluginTypes.ts:5022

Returns the top-most frame that contains this node. If the node is not inside a frame, this will return undefined.

Note: This function will only work in Figma Design and will throw an error if called in FigJam or Slides.

#### Returns

`undefined` \| [`FrameNode`](FrameNode.md)

#### Inherited from

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`getTopLevelFrame`](OpaqueNodeMixin.md#gettoplevelframe)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`remove`](OpaqueNodeMixin.md#remove)

---

### resizeWithoutConstraints()

> **resizeWithoutConstraints**(`width`, `height`): `void`

Defined in: figmaPluginTypes.ts:9838

Resizes the section node without constraints.

#### Parameters

##### width

`number`

New width of the node. Must be >= 0.01

##### height

`number`

New height of the node. Must be >= 0.01

#### Returns

`void`

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setBoundVariable`](OpaqueNodeMixin.md#setboundvariable)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setBoundVariable`](OpaqueNodeMixin.md#setboundvariable)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setDevResourcePreviewAsync`](OpaqueNodeMixin.md#setdevresourcepreviewasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setExplicitVariableModeForCollection`](OpaqueNodeMixin.md#setexplicitvariablemodeforcollection)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setExplicitVariableModeForCollection`](OpaqueNodeMixin.md#setexplicitvariablemodeforcollection)

---

### setFillStyleIdAsync()

> **setFillStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:6672

Sets the [PaintStyle](PaintStyle.md) that the [MinimalFillsMixin.fills](MinimalFillsMixin.md#fills) property of this node is linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`MinimalFillsMixin`](MinimalFillsMixin.md).[`setFillStyleIdAsync`](MinimalFillsMixin.md#setfillstyleidasync)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setPluginData`](OpaqueNodeMixin.md#setplugindata)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setRelaunchData`](OpaqueNodeMixin.md#setrelaunchdata)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`setSharedPluginData`](OpaqueNodeMixin.md#setsharedplugindata)

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

[`OpaqueNodeMixin`](OpaqueNodeMixin.md).[`toString`](OpaqueNodeMixin.md#tostring)

---

### unlockAspectRatio()

> **unlockAspectRatio**(): `void`

Defined in: figmaPluginTypes.ts:5913

Unlocks the node's `targetAspectRatio`.

#### Returns

`void`

#### Inherited from

[`AspectRatioLockMixin`](AspectRatioLockMixin.md).[`unlockAspectRatio`](AspectRatioLockMixin.md#unlockaspectratio)
