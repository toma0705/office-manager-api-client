# AttendanceApi

All URIs are relative to *https://okayama-office-manager.vercel.app/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**usersIdArrivePost**](AttendanceApi.md#usersidarrivepost) | **POST** /users/{id}/arrive | ビーコンの圏内になった（アプリ） |
| [**usersIdEnterPost**](AttendanceApi.md#usersidenterpost) | **POST** /users/{id}/enter | 入室（Web の入室ボタン） |
| [**usersIdExitPost**](AttendanceApi.md#usersidexitpost) | **POST** /users/{id}/exit | 退室（Web の退室ボタン） |
| [**usersIdLeavePost**](AttendanceApi.md#usersidleavepost) | **POST** /users/{id}/leave | ビーコンの圏外になった（アプリ） |



## usersIdArrivePost

> AttendanceStatusResponse usersIdArrivePost(id)

ビーコンの圏内になった（アプリ）

すぐには入室にせず保留にする。確認の時間（1 分）の間に圏外にならなければ、サーバーが入室を確定して Discord に通知する。 - 退室中 → 入室の保留を始める（pending） - 退室の保留中 → 猶予の間に戻ったので保留を取り消す（entered, resumed） - 入室中 → 何もしない（entered） 

### Example

```ts
import {
  Configuration,
  AttendanceApi,
} from '@office-manager/api-client';
import type { UsersIdArrivePostRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttendanceApi(config);

  const body = {
    // number | ユーザー ID
    id: 56,
  } satisfies UsersIdArrivePostRequest;

  try {
    const data = await api.usersIdArrivePost(body);
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
| **id** | `number` | ユーザー ID | [Defaults to `undefined`] |

### Return type

[**AttendanceStatusResponse**](AttendanceStatusResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 記録した |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdEnterPost

> EnterResponse usersIdEnterPost(id)

入室（Web の入室ボタン）

すぐに入室にする。退室の保留中なら、入室の時刻を保ったまま保留を取り消す（resumed）。

### Example

```ts
import {
  Configuration,
  AttendanceApi,
} from '@office-manager/api-client';
import type { UsersIdEnterPostRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttendanceApi(config);

  const body = {
    // number | ユーザー ID
    id: 56,
  } satisfies UsersIdEnterPostRequest;

  try {
    const data = await api.usersIdEnterPost(body);
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
| **id** | `number` | ユーザー ID | [Defaults to `undefined`] |

### Return type

[**EnterResponse**](EnterResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 入室した |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdExitPost

> MessageResponse usersIdExitPost(id)

退室（Web の退室ボタン）

すぐに退室にする。すでに退室中なら 400。

### Example

```ts
import {
  Configuration,
  AttendanceApi,
} from '@office-manager/api-client';
import type { UsersIdExitPostRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttendanceApi(config);

  const body = {
    // number | ユーザー ID
    id: 56,
  } satisfies UsersIdExitPostRequest;

  try {
    const data = await api.usersIdExitPost(body);
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
| **id** | `number` | ユーザー ID | [Defaults to `undefined`] |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 退室した |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdLeavePost

> AttendanceStatusResponse usersIdLeavePost(id)

ビーコンの圏外になった（アプリ）

すぐには退室にせず保留にする。猶予（15 分）の間に戻らなければ、サーバーが退室を確定して Discord に通知する。 - 入室中 → 退室の保留を始める（pending） - 入室の保留中 → 前を通っただけなので保留を取り消す（exited） - 退室中 → 何もしない（exited） 

### Example

```ts
import {
  Configuration,
  AttendanceApi,
} from '@office-manager/api-client';
import type { UsersIdLeavePostRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttendanceApi(config);

  const body = {
    // number | ユーザー ID
    id: 56,
  } satisfies UsersIdLeavePostRequest;

  try {
    const data = await api.usersIdLeavePost(body);
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
| **id** | `number` | ユーザー ID | [Defaults to `undefined`] |

### Return type

[**AttendanceStatusResponse**](AttendanceStatusResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 記録した |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

