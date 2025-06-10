---

GridLayoutGrid

# Interface: GridLayoutGrid

Defined in: figmaPluginTypes.ts:4129

## See

https://www.figma.com/plugin-docs/api/LayoutGrid

## Properties

### boundVariables?

> `readonly` `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:4140

#### sectionSize?

> `optional` **sectionSize**: [`VariableAlias`](VariableAlias.md)

---

### color?

> `readonly` `optional` **color**: [`RGBA`](RGBA.md)

Defined in: figmaPluginTypes.ts:4139

---

### pattern

> `readonly` **pattern**: `"GRID"`

Defined in: figmaPluginTypes.ts:4133

The string literal "GRID" representing the layout grid this is. Always check the `pattern` before reading other properties.

---

### sectionSize

> `readonly` **sectionSize**: `number`

Defined in: figmaPluginTypes.ts:4137

The size of individual grid cells.

---

### visible?

> `readonly` `optional` **visible**: `boolean`

Defined in: figmaPluginTypes.ts:4138
