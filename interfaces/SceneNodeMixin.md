---

SceneNodeMixin

# Interface: SceneNodeMixin

Defined in: figmaPluginTypes.ts:5145

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md)

## Extended by

- [`DefaultShapeMixin`](DefaultShapeMixin.md)
- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`OpaqueNodeMixin`](OpaqueNodeMixin.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)
- [`SliceNode`](SliceNode.md)

## Properties

### attachedConnectors

> `readonly` **attachedConnectors**: [`ConnectorNode`](ConnectorNode.md)[]

Defined in: figmaPluginTypes.ts:5183

An array of `ConnectorNode`s that are attached to a node.

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

---

### componentPropertyReferences

> **componentPropertyReferences**: `null` \| \{ `characters?`: `string`; `mainComponent?`: `string`; `visible?`: `string`; \}

Defined in: figmaPluginTypes.ts:5187

All component properties that are attached on this node. A node can only have `componentPropertyReferences` if it is a component sublayer or an instance sublayer. It will be `null` otherwise. The value in the key-value pair refers to the component property name as returned by `componentPropertyDefinitions` on the containing component, component set or main component (for instances).

---

### explicitVariableModes

> **explicitVariableModes**: `object`

Defined in: figmaPluginTypes.ts:8250

The explicitly set modes for this node.
For `SceneNodes`, represents a subset of [SceneNodeMixin.resolvedVariableModes](#resolvedvariablemodes).
Note that this does not include [workspace and team-default modes](https://help.figma.com/hc/en-us/articles/12611253730071).

#### Index Signature

\[`collectionId`: `string`\]: `string`

#### Inherited from

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`explicitVariableModes`](ExplicitVariableModesMixin.md#explicitvariablemodes)

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

---

### stuckNodes

> `readonly` **stuckNodes**: [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5179

An array of nodes that are "stuck" to this node. In FigJam, stamps, highlights, and some widgets can "stick"
to other nodes if they are dragged on top of another node.

#### Remarks

This property is only available in FigJam.

In FigJam a stickable host that means that stickables, like `'STAMP'` nodes, are allowed to attach themselves to the node. If the stickable host moves all nodes that are in `stuckNodes` move along with it.

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

## Methods

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

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`clearExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#clearexplicitvariablemodeforcollection)

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

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`clearExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#clearexplicitvariablemodeforcollection)

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

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`setExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#setexplicitvariablemodeforcollection)

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

[`ExplicitVariableModesMixin`](ExplicitVariableModesMixin.md).[`setExplicitVariableModeForCollection`](ExplicitVariableModesMixin.md#setexplicitvariablemodeforcollection)
