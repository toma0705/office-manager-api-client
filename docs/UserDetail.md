
# UserDetail


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`email` | string
`iconFileName` | string
`note` | string
`entered` | boolean
`enteredAt` | Date
`exitedAt` | Date
`officeId` | number
`office` | [Office](Office.md)
`password` | string
`resetToken` | string
`resetTokenExpires` | Date

## Example

```typescript
import type { UserDetail } from '@office-manager/api-client'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "email": null,
  "iconFileName": null,
  "note": null,
  "entered": null,
  "enteredAt": null,
  "exitedAt": null,
  "officeId": null,
  "office": null,
  "password": null,
  "resetToken": null,
  "resetTokenExpires": null,
} satisfies UserDetail

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UserDetail
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


