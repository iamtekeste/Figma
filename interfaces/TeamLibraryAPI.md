---

TeamLibraryAPI

# Interface: TeamLibraryAPI

Defined in: figmaPluginTypes.ts:2058

## See

https://www.figma.com/plugin-docs/api/figma-teamlibrary

## Methods

### getAvailableLibraryVariableCollectionsAsync()

> **getAvailableLibraryVariableCollectionsAsync**(): `Promise`\<[`LibraryVariableCollection`](LibraryVariableCollection.md)[]\>

Defined in: figmaPluginTypes.ts:2070

Returns a descriptor of all [VariableCollection](VariableCollection.md)s that exist in the enabled libraries of the current file. Rejects if the request fails.

Note: This requires that users enable libraries that contain variables via the UI. Currently it is not possible to enable libraries via the Plugin API.

#### Returns

`Promise`\<[`LibraryVariableCollection`](LibraryVariableCollection.md)[]\>

A list of [LibraryVariableCollection](LibraryVariableCollection.md)s that are available for this file

#### Remarks

This is intended to be used in conjunction with [TeamLibraryAPI.getVariablesInLibraryCollectionAsync](#getvariablesinlibrarycollectionasync)

---

### getVariablesInLibraryCollectionAsync()

> **getVariablesInLibraryCollectionAsync**(`libraryCollectionKey`): `Promise`\<[`LibraryVariable`](LibraryVariable.md)[]\>

Defined in: figmaPluginTypes.ts:2095

Returns a descriptor of all [Variable](Variable.md)s that exist in a given [LibraryVariableCollection](LibraryVariableCollection.md).
Rejects if the given variable collection does not exist, or if the current user
does not have access to that variable collection's library, or if the request fails.

#### Parameters

##### libraryCollectionKey

`string`

the key of the library variable collection that contains the returned library variables.

## Example usage

```ts title="Example usage of getVariablesInLibraryCollectionAsync"
// Query all published collections from libraries enabled for this file
const libraryCollections =
  await figma.teamLibrary.getAvailableLibraryVariableCollectionsAsync();
// Select a library variable collection to import into this file
const variablesInFirstLibrary =
  await figma.teamLibrary.getVariablesInLibraryCollectionAsync(
    libraryCollections[0].key
  );
// Import the first number variable we find in that collection
const variableToImport = variablesInFirstLibrary.find(
  (libVar) => libVar.resolvedType === "FLOAT"
);
const importedVariable = await figma.variables.importVariableByKeyAsync(
  variableToImport.key
);
```

#### Returns

`Promise`\<[`LibraryVariable`](LibraryVariable.md)[]\>
