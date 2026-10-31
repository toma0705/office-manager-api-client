# NotificationsApi

All URIs are relative to *https://okayama-office-manager.vercel.app/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**notifyPost**](NotificationsApi.md#notifypostoperation) | **POST** /notify | Discord に通知する |



## notifyPost

> NotifyPost200Response notifyPost(notifyPostRequest)

Discord に通知する

入室・退室は、そのときの在室状況を添えて 1 通で送る。メモはメモだけ送る。 名前とオフィスは送信内容ではなく、トークンのユーザーから決まる。 

### Example

```ts
import {
  Configuration,
  NotificationsApi,
} from '@office-manager/api-client';
import type { NotifyPostOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NotificationsApi(config);

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

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 通知した |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

