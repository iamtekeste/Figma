---

VectorRegion

# Interface: VectorRegion

Defined in: figmaPluginTypes.ts:4351

## See

https://www.figma.com/plugin-docs/api/VectorNetwork

## Properties

### fills?

> `readonly` `optional` **fills**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:4363

Array of fill paints used on this region.

---

### fillStyleId?

> `readonly` `optional` **fillStyleId**: `string`

Defined in: figmaPluginTypes.ts:4367

Style key of fill style applied to this region, if any.

---

### loops

> `readonly` **loops**: readonly readonly `number`[][]

Defined in: figmaPluginTypes.ts:4359

List of loops, each of which is a list of indices of `VectorSegment`(s)

---

### windingRule

> `readonly` **windingRule**: [`WindingRule`](../type-aliases/WindingRule.md)

Defined in: figmaPluginTypes.ts:4355

Winding rule for this region.
