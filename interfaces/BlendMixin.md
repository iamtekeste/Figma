---

BlendMixin

# Interface: BlendMixin

Defined in: figmaPluginTypes.ts:5918

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extends

- [`MinimalBlendMixin`](MinimalBlendMixin.md)

## Extended by

- [`DefaultShapeMixin`](DefaultShapeMixin.md)
- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)

## Properties

### blendMode

> **blendMode**: [`BlendMode`](../type-aliases/BlendMode.md)

Defined in: figmaPluginTypes.ts:7182

Blend mode of this node, as shown in the Layer panel. In addition to the blend modes that paints & effects support, the layer blend mode can also have the value PASS_THROUGH.

#### Inherited from

[`MinimalBlendMixin`](MinimalBlendMixin.md).[`blendMode`](MinimalBlendMixin.md#blendmode)

---

### effects

> **effects**: readonly [`Effect`](../type-aliases/Effect.md)[]

Defined in: figmaPluginTypes.ts:5967

Array of effects. See [Effect](../type-aliases/Effect.md) type. For help on how to change this value, see [Editing Properties](https://www.figma.com/plugin-docs/editing-properties).

---

### effectStyleId

> **effectStyleId**: `string`

Defined in: figmaPluginTypes.ts:5973

The id of the [EffectStyle](EffectStyle.md) object that the properties of this node are linked to.

If the manifest contains`"documentAccess": "dynamic-page"`, this property is read-only. Use `setEffectStyleIdAsync` to update the style.

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

---

### maskType

> **maskType**: [`MaskType`](../type-aliases/MaskType.md)

Defined in: figmaPluginTypes.ts:5963

Type of masking to use if this node is a mask. Defaults to `"ALPHA"`. You must check `isMask` to verify that this is a mask; changing `maskType` does not automatically turn on `isMask`, and a node that is not a mask can still have a `maskType`.

---

### opacity

> **opacity**: `number`

Defined in: figmaPluginTypes.ts:7178

Opacity of the node, as shown in the Layer panel. Must be between 0 and 1.

#### Inherited from

[`MinimalBlendMixin`](MinimalBlendMixin.md).[`opacity`](MinimalBlendMixin.md#opacity)

## Methods

### setEffectStyleIdAsync()

> **setEffectStyleIdAsync**(`styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:5977

Set the [EffectStyle](EffectStyle.md) that the properties of this node are linked to.

#### Parameters

##### styleId

`string`

#### Returns

`Promise`\<`void`\>
