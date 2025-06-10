---

RemovedNode

# Interface: RemovedNode

Defined in: figmaPluginTypes.ts:3054

## See

https://www.figma.com/plugin-docs/api/RemovedNode

## Properties

### id

> `readonly` **id**: `string`

Defined in: figmaPluginTypes.ts:3066

The id of the node

---

### removed

> `readonly` **removed**: `true`

Defined in: figmaPluginTypes.ts:3058

`removed` is set to `true` to distinguish a deleted node from one that is on the document.

---

### type

> `readonly` **type**: `"TEXT"` \| `"DOCUMENT"` \| `"PAGE"` \| `"SLICE"` \| `"FRAME"` \| `"GROUP"` \| `"COMPONENT_SET"` \| `"COMPONENT"` \| `"INSTANCE"` \| `"BOOLEAN_OPERATION"` \| `"VECTOR"` \| `"STAR"` \| `"LINE"` \| `"ELLIPSE"` \| `"POLYGON"` \| `"RECTANGLE"` \| `"TEXT_PATH"` \| `"TRANSFORM_GROUP"` \| `"STICKY"` \| `"CONNECTOR"` \| `"SHAPE_WITH_TEXT"` \| `"CODE_BLOCK"` \| `"STAMP"` \| `"WIDGET"` \| `"EMBED"` \| `"LINK_UNFURL"` \| `"MEDIA"` \| `"SECTION"` \| `"HIGHLIGHT"` \| `"WASHI_TAPE"` \| `"TABLE"` \| `"SLIDE"` \| `"SLIDE_ROW"` \| `"SLIDE_GRID"` \| `"INTERACTIVE_SLIDE_ELEMENT"`

Defined in: figmaPluginTypes.ts:3062

The type of the node before it was removed from the document
