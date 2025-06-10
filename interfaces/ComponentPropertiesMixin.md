---

ComponentPropertiesMixin

# Interface: ComponentPropertiesMixin

Defined in: figmaPluginTypes.ts:7390

## Extended by

- [`ComponentSetNode`](ComponentSetNode.md)
- [`ComponentNode`](ComponentNode.md)

## Properties

### componentPropertyDefinitions

> `readonly` **componentPropertyDefinitions**: [`ComponentPropertyDefinitions`](../type-aliases/ComponentPropertyDefinitions.md)

Defined in: figmaPluginTypes.ts:7545

All component properties and their default values that exist on this component set. `'VARIANT'` properties will also have a list of all variant options. `'BOOLEAN'`, `'TEXT'`, and `'INSTANCE_SWAP'` properties will have their names suffixed by a unique identifier starting with `'#'`, which is helpful for quickly distinguishing multiple component properties that have the same name in the Figma UI. The entire property name should be used for all Component property-related API methods and properties.

#### Remarks

[Component properties-related properties](https://help.figma.com/hc/en-us/articles/5579474826519-Create-and-use-component-properties) define parts of the component people can change by tying them to specific design properties. You can create component properties for any main component or component set, and apply them to nested layers of the component or variant.

```ts title="Component properties-related properties and methods for component sets, components, and instances"
componentSet.componentPropertyDefinitions

// Output
{
  Size: {
    type: 'VARIANT',
    defaultValue: 'Small',
    variantOptions: ['Small', 'Medium', 'Large'],
  },
  IconVisible#0:0: {
    type: 'BOOLEAN',
    defaultValue: false,
  },
  ButtonText#0:1: {
    type: 'TEXT',
    defaultValue: 'submit',
  },
  IconInstance#0:2: {
    type: 'INSTANCE_SWAP',
    defaultValue: '1:1',
    preferredValues: [
      {type: 'COMPONENT', key: 'ckey1'},
      {type: 'COMPONENT_SET', key: 'sgkey1'}
    ],
  },
}

// componentProperties on an instance
instance.componentProperties

// Output
{
  Size: {
    type: 'VARIANT',
    value: 'Medium',
  },
  IconVisible#0:0: {
    type: 'BOOLEAN',
    value: false,
  },
  ButtonText#0:1: {
    type: 'TEXT',
    value: 'cancel',
  },
  IconInstance#0:2: {
    type: 'INSTANCE_SWAP',
    defaultValue: '1:1',
    preferredValues: [
      {type: 'COMPONENT', key: 'ckey1'},
      {type: 'COMPONENT_SET', key: 'sgkey1'}
    ],
  },
}

// component property definitions can be created, edited, and deleted
component.addComponentProperty("ButtonIcon", "INSTANCE_SWAP", "2:22")
// returns "ButtonIcon#4:3"

component.editComponentProperty(
  "ButtonIcon#4:3",
  {name: "PrimaryButtonIcon", defaultValue: "1:100"}
)
// returns "PrimaryButtonIcon#5:5"

component.deleteComponentProperty("PrimaryButtonIcon#5:5")

// componentPropertyDefinitions and componentProperties work similarly for
// main components and their instances but will never have 'VARIANT'
// properties.
component.componentPropertyDefinitions

// Output
{
  ImageVisible#0:0: {
    type: 'BOOLEAN',
    defaultValue: true,
  },
  Icon#0:1: {
    type: 'INSTANCE_SWAP',
    defaultValue: '7:23',
  },
}

instance.componentProperties

// Output
{
  ImageVisible#0:0: {
    type: 'BOOLEAN',
    value: true,
  },
  Icon#0:1: {
    type: 'INSTANCE_SWAP',
    value: '1:24',
  },
}

// component properties can be applied to node properties of nested layers
component.children[0].children[0].componentPropertyReferences = {
  'visible': 'IconVisible#0:0'
}
component.children[0].children[0].visible

// Output
false // gets value from component property definition

// Use setProperties on an instance to configure it
instance.setProperties({ Size: 'Large', 'ButtonText#0:1': 'login' })
instance.componentProperties

// Output
{
  Size: {
    type: 'VARIANT',
    value: 'Large',
  },
  IconVisible#0:0: {
    type: 'BOOLEAN',
    value: false,
  },
  ButtonText#0:1: {
    type: 'TEXT',
    value: 'login',
  },
}

instance.setProperties({ 'IconVisible#0:0': true })
instance.componentProperties

// Output
{
  Size: {
    type: 'VARIANT',
    value: 'Large',
  },
  IconVisible#0:0: {
    type: 'BOOLEAN',
    value: true,
  },
  ButtonText#0:1: {
    type: 'TEXT',
    value: 'login',
  },
}
```

## Methods

### addComponentProperty()

> **addComponentProperty**(`propertyName`, `type`, `defaultValue`, `options?`): `string`

Defined in: figmaPluginTypes.ts:7549

Adds a new component property to this node and returns the property name with its unique identifier suffixed. This function supports properties with type `'BOOLEAN'`, `'TEXT'`, `'INSTANCE_SWAP'` or `'VARIANT'`.

#### Parameters

##### propertyName

`string`

##### type

[`ComponentPropertyType`](../type-aliases/ComponentPropertyType.md)

##### defaultValue

`string` | `boolean` | [`VariableAlias`](VariableAlias.md)

##### options?

[`ComponentPropertyOptions`](../type-aliases/ComponentPropertyOptions.md)

#### Returns

`string`

---

### deleteComponentProperty()

> **deleteComponentProperty**(`propertyName`): `void`

Defined in: figmaPluginTypes.ts:7575

Deletes an existing component property on this node. This function only supports properties with type `'BOOLEAN'`, `'TEXT'`, or `'INSTANCE_SWAP'`.

#### Parameters

##### propertyName

`string`

#### Returns

`void`

---

### editComponentProperty()

> **editComponentProperty**(`propertyName`, `newValue`): `string`

Defined in: figmaPluginTypes.ts:7564

Modifies the name, default value, or preferred values of an existing component property on this node and returns the property name with its unique identifier suffixed.

This function supports properties with type `'BOOLEAN'`, `'TEXT'`, `'INSTANCE_SWAP'`, or `'VARIANT'` with the following restrictions:

- `name` is supported for all properties
- `defaultValue` is supported for `'BOOLEAN'`, `'TEXT'`, and `'INSTANCE_SWAP'` properties, but not for `'VARIANT'` properties
- `preferredValues` is only supported for `'INSTANCE_SWAP'` properties

#### Parameters

##### propertyName

`string`

##### newValue

###### defaultValue?

`string` \| `boolean` \| [`VariableAlias`](VariableAlias.md)

###### name?

`string`

###### preferredValues?

[`InstanceSwapPreferredValue`](../type-aliases/InstanceSwapPreferredValue.md)[]

#### Returns

`string`
