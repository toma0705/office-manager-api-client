# OfficesApi

All URIs are relative to *https://api.example.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**officesGet**](OfficesApi.md#officesget) | **GET** /offices | オフィス一覧の取得 |



## officesGet

> Array&lt;Office&gt; officesGet()

オフィス一覧の取得

### Example

```ts
import {
  Configuration,
  OfficesApi,
} from '@office-manager/api-client';
import type { OfficesGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new OfficesApi();

  try {
    const data = await api.officesGet();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Array&lt;Office&gt;**](Office.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 成功 |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

