---

DevStatusMixin

# Interface: DevStatusMixin

Defined in: figmaPluginTypes.ts:5132

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`BaseFrameMixin`](BaseFrameMixin.md)
- [`SectionNode`](SectionNode.md)

## Properties

### devStatus

> **devStatus**: [`DevStatus`](../type-aliases/DevStatus.md)

Defined in: figmaPluginTypes.ts:5140

Whether the node is marked [ready for development](https://help.figma.com/hc/en-us/articles/15023124644247-Guide-to-Dev-Mode#01H8CR3K6V9S02RK503QCX0367) or [completed](https://help.figma.com/hc/en-us/articles/15023124644247-Guide-to-Dev-Mode#01H8CR3K6V9S02RK503QCX0367).

There are some restrictions on how `devStatus` can be set:

- Can only be set on a node directly under a page or section
- Cannot be set on a node that is inside another node that already has a `devStatus`
