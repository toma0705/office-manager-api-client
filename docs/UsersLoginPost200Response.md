
# UsersLoginPost200Response


## Properties

Name | Type
------------ | -------------
`user` | [UserSafe](UserSafe.md)
`token` | string

## Example

```typescript
import type { UsersLoginPost200Response } from '@office-manager/api-client'

// TODO: Update the object below with actual values
const example = {
  "user": null,
  "token": null,
} satisfies UsersLoginPost200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UsersLoginPost200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


