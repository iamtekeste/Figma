---

VectorPath

# Interface: VectorPath

Defined in: figmaPluginTypes.ts:4389

## See

https://www.figma.com/plugin-docs/api/VectorPath

## Properties

### data

> `readonly` **data**: `string`

Defined in: figmaPluginTypes.ts:4417

A series of path commands that encodes how to draw the path.

#### Remarks

Figma supports a subset of the SVG path format. Path commands must be joined into a single string in order separated by a single space. Here are the path commands we support:

- `M x y`: The absolute "move to" command.
- `L x y`: The absolute "line to" command.
- `Q x0 y0 x y`: The absolute "quadratic spline to" command. _Note_ that while Figma supports this as input, we will never generate this ourselves. All quadratic splines are converted to cubic splines internally.
- `C x0 y0 x1 y1 x y`: The absolute "cubic spline to" command.
- `Z`: The "close path" command.

---

### windingRule

> `readonly` **windingRule**: `"NONE"` \| [`WindingRule`](../type-aliases/WindingRule.md)

Defined in: figmaPluginTypes.ts:4404

The winding rule for the path (same as in SVGs). This determines whether a given point in space is inside or outside the path.

#### Remarks

```ts
type WindingRule = "NONZERO" | "EVENODD";
```

Winding rules work off a concept called the winding number, which tells you for a given point how many times the path winds around that point. This is described in much more detail [here](https://oreillymedia.github.io/Using_SVG/extras/ch06-fill-rule.html). This field can have three possible values:

- `"NONZERO"`: The point is considered inside the path if the winding number is NONZERO.
- `"EVENODD"`: The point is considered inside the path if the winding number is odd.
- `"NONE"`: An open path won’t have a fill.
