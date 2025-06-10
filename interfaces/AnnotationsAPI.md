---

AnnotationsAPI

# Interface: AnnotationsAPI

Defined in: figmaPluginTypes.ts:2034

## See

https://www.figma.com/plugin-docs/api/figma-annotations

## Methods

### addAnnotationCategoryAsync()

> **addAnnotationCategoryAsync**(`categoryInput`): `Promise`\<[`AnnotationCategory`](AnnotationCategory.md)\>

Defined in: figmaPluginTypes.ts:2050

Adds a new [AnnotationCategory](AnnotationCategory.md).

#### Parameters

##### categoryInput

The label and color of the annotation category.

###### color

[`AnnotationCategoryColor`](../type-aliases/AnnotationCategoryColor.md)

###### label

`string`

#### Returns

`Promise`\<[`AnnotationCategory`](AnnotationCategory.md)\>

---

### getAnnotationCategoriesAsync()

> **getAnnotationCategoriesAsync**(): `Promise`\<[`AnnotationCategory`](AnnotationCategory.md)[]\>

Defined in: figmaPluginTypes.ts:2038

Returns a list of all [AnnotationCategory](AnnotationCategory.md)s that exist in the current file.

#### Returns

`Promise`\<[`AnnotationCategory`](AnnotationCategory.md)[]\>

---

### getAnnotationCategoryByIdAsync()

> **getAnnotationCategoryByIdAsync**(`id`): `Promise`\<`null` \| [`AnnotationCategory`](AnnotationCategory.md)\>

Defined in: figmaPluginTypes.ts:2044

Returns an [AnnotationCategory](AnnotationCategory.md) by its ID. If not found, returns a promise containing null.

#### Parameters

##### id

`string`

The annotation category ID to search for.

#### Returns

`Promise`\<`null` \| [`AnnotationCategory`](AnnotationCategory.md)\>
