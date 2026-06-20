# MaintenanceApi

All URIs are relative to *https://api.example.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**warmupGet**](MaintenanceApi.md#warmupget) | **GET** /warmup | Prisma クライアントウォームアップ |
| [**warmupHead**](MaintenanceApi.md#warmuphead) | **HEAD** /warmup | ヘルスチェック |



## warmupGet

> WarmupGet200Response warmupGet()

Prisma クライアントウォームアップ

### Example

```ts
import {
  Configuration,
  MaintenanceApi,
} from '@office-manager/api-client';
import type { WarmupGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new MaintenanceApi();

  try {
    const data = await api.warmupGet();
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

[**WarmupGet200Response**](WarmupGet200Response.md)

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


## warmupHead

> warmupHead()

ヘルスチェック

### Example

```ts
import {
  Configuration,
  MaintenanceApi,
} from '@office-manager/api-client';
import type { WarmupHeadRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new MaintenanceApi();

  try {
    const data = await api.warmupHead();
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

`void` (Empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 稼働中 |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

