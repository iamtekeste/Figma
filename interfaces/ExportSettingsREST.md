---

ExportSettingsREST

# Interface: ExportSettingsREST

Defined in: figmaPluginTypes.ts:4264

## See

https://www.figma.com/plugin-docs/api/ExportSettings

## Properties

### format

> `readonly` **format**: `"JSON_REST_V1"`

Defined in: figmaPluginTypes.ts:4288

Returns the equivalent REST API response of hitting the endpoint `https://api.figma.com/v1/files/:file_key/nodes?ids=:id`.

This is useful if you have existing code that uses the REST API that you would like to have work inside a plugin as well. It can also be significantly more perfomant if you need to serialize large groups of nodes and their children.
Here is an example that logs the name of every child in a node using the REST API response:

```ts title="Using the JSON_REST_V1 format"
function visitChildren(child: Object) {
  console.log(child.name);
  if (child.children) {
    child.children.forEach(visitChildren);
  }
}

const response = await figma.currentPage.selection[0].exportAsync({
  format: "JSON_REST_V1",
});

visitChildren(response.document);
```

For more information on the shape of the output of the 'JSON_REST_V1' format, see: https://www.figma.com/developers/api#files
