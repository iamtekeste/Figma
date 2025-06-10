---

PublishableMixin

# Interface: PublishableMixin

Defined in: figmaPluginTypes.ts:7042

## See

https://www.figma.com/plugin-docs/api/node-properties

## Extended by

- [`ComponentSetNode`](ComponentSetNode.md)
- [`ComponentNode`](ComponentNode.md)
- [`BaseStyleMixin`](BaseStyleMixin.md)

## Properties

### description

> **description**: `string`

Defined in: figmaPluginTypes.ts:7052

The plain-text annotation entered by the user for this style/component.

#### Remarks

To set a rich-text description using markdown, see [PublishableMixin.descriptionMarkdown](#descriptionmarkdown)

Caution: ⚠️ There is a currently a bug in Figma where the description field will appear to be missing or not up to date. Until this is fixed, the workaround is to re-publish nodes for which the description is missing.

---

### descriptionMarkdown

> **descriptionMarkdown**: `string`

Defined in: figmaPluginTypes.ts:7061

The rich-text annotation entered by the user for this style/component.

#### Remarks

Caution: ⚠️ There is a currently a bug in Figma where the description field will appear to be missing or not up to date. Until this is fixed, the workaround is to re-publish nodes for which the description is missing.

---

### documentationLinks

> **documentationLinks**: readonly [`DocumentationLink`](DocumentationLink.md)[]

Defined in: figmaPluginTypes.ts:7078

The documentation links for this style/component.

#### Remarks

This API currently only supports setting a single documentation link. To clear the documentation links, set to the empty list [].

Example:

```ts
node.documentationLinks = [{ uri: "https://www.figma.com" }];

// clear documentation links
node.documentationLinks = [];
```

---

### key

> `readonly` **key**: `string`

Defined in: figmaPluginTypes.ts:7086

The key to use with [PluginAPI.importComponentByKeyAsync](PluginAPI.md#importcomponentbykeyasync), [PluginAPI.importComponentSetByKeyAsync](PluginAPI.md#importcomponentsetbykeyasync) and [PluginAPI.importStyleByKeyAsync](PluginAPI.md#importstylebykeyasync). Note that while this key is present on local and published components, you can only import components that are already published.

---

### remote

> `readonly` **remote**: `boolean`

Defined in: figmaPluginTypes.ts:7082

Whether this style/component is a remote style/component that doesn't live in the file (i.e. is from the team library). Remote components are read-only: attempts to change their properties will throw.

## Methods

### getPublishStatusAsync()

> **getPublishStatusAsync**(): `Promise`\<[`PublishStatus`](../type-aliases/PublishStatus.md)\>

Defined in: figmaPluginTypes.ts:7090

Gets the status of this style/component in the team library.

#### Returns

`Promise`\<[`PublishStatus`](../type-aliases/PublishStatus.md)\>
