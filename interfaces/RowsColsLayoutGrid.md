---

RowsColsLayoutGrid

# Interface: RowsColsLayoutGrid

Defined in: figmaPluginTypes.ts:4086

## See

https://www.figma.com/plugin-docs/api/LayoutGrid

## Properties

### alignment

> `readonly` **alignment**: `"MIN"` \| `"CENTER"` \| `"MAX"` \| `"STRETCH"`

Defined in: figmaPluginTypes.ts:4094

How the layout grid is aligned. "MIN" corresponds to "Left" or "Top" in the UI depending on the orientation of the layout grid. "MAX" corresponds to "Right" or "Bottom".

---

### boundVariables?

> `readonly` `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:4122

The variables bound to a particular field on this shadow effect

#### count?

> `optional` **count**: [`VariableAlias`](VariableAlias.md)

#### gutterSize?

> `optional` **gutterSize**: [`VariableAlias`](VariableAlias.md)

#### offset?

> `optional` **offset**: [`VariableAlias`](VariableAlias.md)

#### sectionSize?

> `optional` **sectionSize**: [`VariableAlias`](VariableAlias.md)

---

### color?

> `readonly` `optional` **color**: [`RGBA`](RGBA.md)

Defined in: figmaPluginTypes.ts:4118

The color of the layout grid.

---

### count

> `readonly` **count**: `number`

Defined in: figmaPluginTypes.ts:4102

The number of sections. This can be set to the value `Infinity`, which corresponds to "Auto" in the UI.

---

### gutterSize

> `readonly` **gutterSize**: `number`

Defined in: figmaPluginTypes.ts:4098

The distance between the sections of the grid.

---

### offset?

> `readonly` `optional` **offset**: `number`

Defined in: figmaPluginTypes.ts:4110

The distance between the layout grid sections and the edges of the frame. This is ignored when `alignment == "CENTER"` since the size is set automatically.

---

### pattern

> `readonly` **pattern**: `"ROWS"` \| `"COLUMNS"`

Defined in: figmaPluginTypes.ts:4090

The string literal representing the layout grid this is. Always check the `pattern` before reading other properties.

---

### sectionSize?

> `readonly` `optional` **sectionSize**: `number`

Defined in: figmaPluginTypes.ts:4106

The size of a section. This is ignored when `alignment == "STRETCH"` since the size is set automatically.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:4114

Whether the layout grid is visible. Defaults to true.
