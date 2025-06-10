---

VectorSegment

# Interface: VectorSegment

Defined in: figmaPluginTypes.ts:4330

## See

https://www.figma.com/plugin-docs/api/VectorNetwork

## Properties

### end

> `readonly` **end**: `number`

Defined in: figmaPluginTypes.ts:4338

The index of the vertex that ends this segment.

---

### start

> `readonly` **start**: `number`

Defined in: figmaPluginTypes.ts:4334

The index of the vertex that starts this segment.

---

### tangentEnd?

> `readonly` `optional` **tangentEnd**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:4346

The tangent on the end side of this segment. Defaults to { x: 0, y: 0 }

---

### tangentStart?

> `readonly` `optional` **tangentStart**: [`Vector`](Vector.md)

Defined in: figmaPluginTypes.ts:4342

The tangent on the start side of this segment. Defaults to { x: 0, y: 0 }
