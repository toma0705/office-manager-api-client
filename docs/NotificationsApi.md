# NotificationsApi

All URIs are relative to *https://api.example.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**notifyPost**](NotificationsApi.md#notifypostoperation) | **POST** /notify | Discord 通知送信 |



## notifyPost

> NotifyPost200Response notifyPost(notifyPostRequest)

Discord 通知送信

入退室イベントを Discord Webhook に投稿します。

### Example

```ts
import {
  Configuration,
  NotificationsApi,
} from '@office-manager/api-client';
import type { NotifyPostOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new NotificationsApi();

  const body = {
    // NotifyPostRequest
    notifyPostRequest: ...,
  } satisfies NotifyPostOperationRequest;

  try {
    const data = await api.notifyPost(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **notifyPostRequest** | [NotifyPostRequest](NotifyPostRequest.md) |  | |

### Return type

[**NotifyPost200Response**](NotifyPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 通知送信に成功 |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

