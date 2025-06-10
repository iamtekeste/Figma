---

ChildrenMixin

# Interface: ChildrenMixin

Defined in: figmaPluginTypes.ts:5355

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`PageNode`](PageNode.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)
- [`BooleanOperationNode`](BooleanOperationNode.md)
- [`SectionNode`](SectionNode.md)
- [`SlideRowNode`](SlideRowNode.md)
- [`SlideGridNode`](SlideGridNode.md)

## Properties

### children

> `readonly` **children**: readonly [`SceneNode`](../type-aliases/SceneNode.md)[]

Defined in: figmaPluginTypes.ts:5369

The list of children, sorted back-to-front. That is, the first child in the array is the bottommost layer on the screen, and the last child in the array is the topmost layer.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this property.

#### Remarks

This array can be read like and iterated like a regular array. However, calling this property always returns a new array, and both the property and the new array are read-only.

As such, this property cannot be assigned to, and the array cannot be modified directly (it wouldn't do anything). Instead, use [ChildrenMixin.appendChild](#appendchild), [ChildrenMixin.insertChild](#insertchild) or [BaseNodeMixin.remove](BaseNodeMixin.md#remove).

Note: If you are curious, the reason why inserting children has to be done via API calls is because our internal representation for the layer tree uses [fractional indexing](https://www.figma.com/blog/multiplayer-editing-in-figma/) and [ChildrenMixin.insertChild](#insertchild) performs that conversion.

## Methods

### appendChild()

> **appendChild**(`child`): `void`

Defined in: figmaPluginTypes.ts:5381

Adds a new child to the end of the [ChildrenMixin.children](#children) array. That is, visually on top of all other children.

If the manifest contains `"documentAccess": "dynamic-page"`, **and** the node is a [PageNode](PageNode.md), you must first call [PageNode.loadAsync](PageNode.md#loadasync) to access this function.

#### Parameters

##### child

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

`void`

#### Remarks

Reparenting nodes is subject to many restrictions. For example, some nodes cannot be moved, others would break the document if moved. Below are possible exceptions that can be thrown if the operation is invalid.

If this is called on an auto-layout frame, calling this function can cause this layer to be resized and children to be moved.

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

Nodes are included in **back-to-front** order. Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](#children) array.

This traversal method is known as ["pre-order traversal"](<https://en.wikipedia.org/wiki/Tree_traversal#Pre-order_(NLR)>).

Note that the node this method is called on is **not included**.

Example: find all nodes whose name is "Color":

```ts
const colors = figma.currentPage.findAll((n) => n.name === "Color");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
If you only need to search immediate children, it is much faster to call `node.children.filter(callback)` or `node.findChildren(callback)`.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

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

This is a faster but more limited search compared to [ChildrenMixin.findAll](#findall), which lets you search nodes based on any logic you can include in a callback.

When paired with [`figma.skipInvisibleInstanceChildren = true`](https://www.figma.com/plugin-docs/api/properties/figma-skipinvisibleinstancechildren), this method can be hundreds of times faster in large documents with tens of thousands of nodes.

The return value is narrowly typed to match the provided `types`, which makes it much easier to use node-type-specific properties. For example, `node.findAllWithCriteria({ types: ['TEXT'] })` will return `TextNode[]` instead of the more generic `SceneNode[]` from [ChildrenMixin.findAll](#findall).

Nodes are included in **back-to-front** order, which is the same order as in [ChildrenMixin.findAll](#findall). Parents always appear before their children, and children appear in same relative order before their children, and children appear in same relative order as in the [ChildrenMixin.children](#children) array.

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

This function returns `null` if no matching node is found. The traversal order is the same as in [ChildrenMixin.findAll](#findall).

Note that the node this method is called on is **not included**.

Example: find one node whose name is "Template":

```ts
const template = figma.currentPage.findOne((n) => n.name === "Template");
```

Caution: ⚠ Large documents in Figma can have tens of thousands of nodes. Be careful using this function as it could be very slow.
If you only need to search immediate children, it is much faster to call `node.children.find(callback)` or `node.findChild(callback)`.
Please refer to our [recommendations](https://www.figma.com/plugin-docs/accessing-document#optimizing-traversals) for how to optimize document traversals.

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

---

### insertChild()

> **insertChild**(`index`, `child`): `void`

Defined in: figmaPluginTypes.ts:5402

Adds a new child at the specified index in the [ChildrenMixin.children](#children) array.

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
