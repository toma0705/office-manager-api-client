
# UserListItem


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`iconFileName` | string
`office` | [Office](Office.md)

## Example

```typescript
import type { UserListItem } from '@office-manager/api-client'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "iconFileName": null,
  "office": null,
} satisfies UserListItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UserListItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


