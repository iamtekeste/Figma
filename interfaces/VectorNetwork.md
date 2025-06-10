---

VectorNetwork

# Interface: VectorNetwork

Defined in: figmaPluginTypes.ts:4372

## See

https://www.figma.com/plugin-docs/api/VectorNetwork

## Properties

### regions?

> `readonly` `optional` **regions**: readonly [`VectorRegion`](VectorRegion.md)[]

Defined in: figmaPluginTypes.ts:4384

Regions are defined by segments and specify that an area is to be filled. Defaults to [].

---

### segments

> `readonly` **segments**: readonly [`VectorSegment`](VectorSegment.md)[]

Defined in: figmaPluginTypes.ts:4380

Segments connect vertices.

---

### vertices

> `readonly` **vertices**: readonly [`VectorVertex`](VectorVertex.md)[]

Defined in: figmaPluginTypes.ts:4376

Vertices are points in the graph.
