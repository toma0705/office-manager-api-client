
# Office


## Properties

Name | Type
------------ | -------------
`id` | number
`code` | string
`name` | string
`latitude` | number
`longitude` | number
`radiusMeters` | number

## Example

```typescript
import type { Office } from '@office-manager/api-client'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "code": null,
  "name": null,
  "latitude": null,
  "longitude": null,
  "radiusMeters": null,
} satisfies Office

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Office
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


