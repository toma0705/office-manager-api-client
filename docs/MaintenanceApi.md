# MaintenanceApi

All URIs are relative to *https://okayama-office-manager.vercel.app/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cronFinalizeExitsGet**](MaintenanceApi.md#cronfinalizeexitsget) | **GET** /cron/finalize-exits | 入退室の保留の確定（cron-job.org から毎分） |
| [**cronNightlyCheckoutGet**](MaintenanceApi.md#cronnightlycheckoutget) | **GET** /cron/nightly-checkout | 一括退室（cron-job.org から毎日 4:00） |
| [**warmupGet**](MaintenanceApi.md#warmupget) | **GET** /warmup | DB への接続を先に済ませる |
| [**warmupHead**](MaintenanceApi.md#warmuphead) | **HEAD** /warmup | 死活確認 |



## cronFinalizeExitsGet

> CronFinalizeExitsGet200Response cronFinalizeExitsGet()

入退室の保留の確定（cron-job.org から毎分）

確認の時間を過ぎた入室の保留と、猶予を過ぎた退室の保留を確定して Discord に通知する。

### Example

```ts
import {
  Configuration,
  MaintenanceApi,
} from '@office-manager/api-client';
import type { CronFinalizeExitsGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: cronSecret
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MaintenanceApi(config);

  try {
    const data = await api.cronFinalizeExitsGet();
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

[**CronFinalizeExitsGet200Response**](CronFinalizeExitsGet200Response.md)

### Authorization

[cronSecret](../README.md#cronSecret)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 確定した人数 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## cronNightlyCheckoutGet

> CronNightlyCheckoutGet200Response cronNightlyCheckoutGet()

一括退室（cron-job.org から毎日 4:00）

入室中の全員を退室にする。Discord には通知しない。

### Example

```ts
import {
  Configuration,
  MaintenanceApi,
} from '@office-manager/api-client';
import type { CronNightlyCheckoutGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: cronSecret
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MaintenanceApi(config);

  try {
    const data = await api.cronNightlyCheckoutGet();
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

[**CronNightlyCheckoutGet200Response**](CronNightlyCheckoutGet200Response.md)

### Authorization

[cronSecret](../README.md#cronSecret)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 退室にした人数 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## warmupGet

> WarmupGet200Response warmupGet()

DB への接続を先に済ませる

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

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## warmupHead

> warmupHead()

死活確認

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

