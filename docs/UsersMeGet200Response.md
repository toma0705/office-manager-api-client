
# UsersMeGet200Response


## Properties

Name | Type
------------ | -------------
`user` | [UserSafe](UserSafe.md)
`enteredUsers` | [Array&lt;EnteredUser&gt;](EnteredUser.md)

## Example

```typescript
import type { UsersMeGet200Response } from '@office-manager/api-client'

// TODO: Update the object below with actual values
const example = {
  "user": null,
  "enteredUsers": null,
} satisfies UsersMeGet200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UsersMeGet200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


