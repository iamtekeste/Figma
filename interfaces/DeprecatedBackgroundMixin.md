---

DeprecatedBackgroundMixin

# Interface: DeprecatedBackgroundMixin

Defined in: figmaPluginTypes.ts:5991

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`GroupNode`](GroupNode.md)
- [`TransformGroupNode`](TransformGroupNode.md)

## Properties

### ~~backgrounds~~

> **backgrounds**: readonly [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:5995

#### Deprecated

Use `fills` instead.

---

### ~~backgroundStyleId~~

> **backgroundStyleId**: `string`

Defined in: figmaPluginTypes.ts:5999

#### Deprecated

Use `fillStyleId` instead. This property is read-only if the manifest contains `"documentAccess": "dynamic-page"`.
