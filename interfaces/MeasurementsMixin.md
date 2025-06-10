---

MeasurementsMixin

# Interface: MeasurementsMixin

Defined in: figmaPluginTypes.ts:7260

## Extended by

- [`PageNode`](PageNode.md)

## Methods

### addMeasurement()

> **addMeasurement**(`start`, `end`, `options?`): [`Measurement`](Measurement.md)

Defined in: figmaPluginTypes.ts:7288

Adds a measurement between two nodes in the current page.

Measurements are always between a start and end node. The side indicates which edge of the node to draw the measurement from.

Measurements can only go on the same axis, i.e. from side `"LEFT"` -> `"LEFT"`, `"LEFT"` -> `"RIGHT"`, `"TOP"` -> `"BOTTOM"` etc. But not `"LEFT"` -> `"TOP"`.

See the [Measurement type](https://www.figma.com/plugin-docs/api/Measurement) for usage examples.

Note: This method is only available in Dev Mode. You can check the editor type of your plugin to know if the user is in Dev Mode or not:

```ts
if (figma.editorType === "dev") {
  // In Figma's Dev Mode
}
```

#### Parameters

##### start

###### node

[`SceneNode`](../type-aliases/SceneNode.md)

###### side

[`MeasurementSide`](../type-aliases/MeasurementSide.md)

##### end

###### node

[`SceneNode`](../type-aliases/SceneNode.md)

###### side

[`MeasurementSide`](../type-aliases/MeasurementSide.md)

##### options?

###### freeText?

`string`

###### offset?

[`MeasurementOffset`](../type-aliases/MeasurementOffset.md)

**Default**

```ts
{
  type: "INNER";
  relative: 0;
}
```

#### Returns

[`Measurement`](Measurement.md)

---

### deleteMeasurement()

> **deleteMeasurement**(`id`): `void`

Defined in: figmaPluginTypes.ts:7338

Delete a measurement.

See the [Measurement type](https://www.figma.com/plugin-docs/api/Measurement) for usage examples.

Note: This method is only available in Dev Mode. You can check the editor type of your plugin to know if the user is in Dev Mode or not:

```ts
if (figma.editorType === "dev") {
  // In Figma's Dev Mode
}
```

#### Parameters

##### id

`string`

#### Returns

`void`

---

### editMeasurement()

> **editMeasurement**(`id`, `newValue`): [`Measurement`](Measurement.md)

Defined in: figmaPluginTypes.ts:7318

Edit a measurement’s offset.

See the [Measurement type](https://www.figma.com/plugin-docs/api/Measurement) for usage examples.

Note: This method is only available in Dev Mode. You can check the editor type of your plugin to know if the user is in Dev Mode or not:

```ts
if (figma.editorType === "dev") {
  // In Figma's Dev Mode
}
```

#### Parameters

##### id

`string`

##### newValue

###### freeText?

`string`

###### offset?

[`MeasurementOffset`](../type-aliases/MeasurementOffset.md)

#### Returns

[`Measurement`](Measurement.md)

---

### getMeasurements()

> **getMeasurements**(): [`Measurement`](Measurement.md)[]

Defined in: figmaPluginTypes.ts:7266

Get all measurements in the current page.

Learn more about measurements in the [Help Center](https://help.figma.com/hc/en-us/articles/20774752502935).

#### Returns

[`Measurement`](Measurement.md)[]

---

### getMeasurementsForNode()

> **getMeasurementsForNode**(`node`): [`Measurement`](Measurement.md)[]

Defined in: figmaPluginTypes.ts:7270

Get all measurements pointing to a node in the current page. This includes all measurements whose start _or_ end node is the node passed in.

#### Parameters

##### node

[`SceneNode`](../type-aliases/SceneNode.md)

#### Returns

[`Measurement`](Measurement.md)[]
