# UsersApi

All URIs are relative to *https://api.example.com*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**usersGet**](UsersApi.md#usersget) | **GET** /users | ユーザー一覧の取得 |
| [**usersIdDelete**](UsersApi.md#usersiddelete) | **DELETE** /users/{id} | ユーザー削除 |
| [**usersIdGet**](UsersApi.md#usersidget) | **GET** /users/{id} | ユーザー詳細の取得 |
| [**usersIdPatch**](UsersApi.md#usersidpatchoperation) | **PATCH** /users/{id} | ユーザーノートの更新 |
| [**usersLoginPost**](UsersApi.md#usersloginpostoperation) | **POST** /users/login | ログイン |
| [**usersMeGet**](UsersApi.md#usersmeget) | **GET** /users/me | 認証済みユーザー情報 |
| [**usersPost**](UsersApi.md#userspost) | **POST** /users | ユーザー新規登録 |
| [**usersResetPasswordRequestPost**](UsersApi.md#usersresetpasswordrequestpostoperation) | **POST** /users/reset-password-request | パスワードリセット申請 |
| [**usersResetPasswordTokenPost**](UsersApi.md#usersresetpasswordtokenpostoperation) | **POST** /users/reset-password/{token} | パスワードリセット実行 |



## usersGet

> Array&lt;UserListItem&gt; usersGet(officeCode)

ユーザー一覧の取得

登録フォームなどで利用するためのユーザー一覧を返します。&#x60;officeCode&#x60; を指定した場合は該当オフィスのユーザーのみに絞り込みます。

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // string | フィルタ対象のオフィスコード（大文字・小文字は区別されません） (optional)
    officeCode: officeCode_example,
  } satisfies UsersGetRequest;

  try {
    const data = await api.usersGet(body);
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
| **officeCode** | `string` | フィルタ対象のオフィスコード（大文字・小文字は区別されません） | [Optional] [Defaults to `undefined`] |

### Return type

[**Array&lt;UserListItem&gt;**](UserListItem.md)

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


## usersIdDelete

> MessageResponse usersIdDelete(id)

ユーザー削除

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersIdDeleteRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // number | ユーザーID
    id: 56,
  } satisfies UsersIdDeleteRequest;

  try {
    const data = await api.usersIdDelete(body);
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
| **id** | `number` | ユーザーID | [Defaults to `undefined`] |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 削除成功 |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdGet

> UserDetail usersIdGet(id)

ユーザー詳細の取得

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersIdGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // number | ユーザーID
    id: 56,
  } satisfies UsersIdGetRequest;

  try {
    const data = await api.usersIdGet(body);
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
| **id** | `number` | ユーザーID | [Defaults to `undefined`] |

### Return type

[**UserDetail**](UserDetail.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 成功 |  -  |
| **404** | 対象が見つかりません |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdPatch

> UserDetail usersIdPatch(id, usersIdPatchRequest)

ユーザーノートの更新

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersIdPatchOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // number | ユーザーID
    id: 56,
    // UsersIdPatchRequest
    usersIdPatchRequest: ...,
  } satisfies UsersIdPatchOperationRequest;

  try {
    const data = await api.usersIdPatch(body);
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
| **id** | `number` | ユーザーID | [Defaults to `undefined`] |
| **usersIdPatchRequest** | [UsersIdPatchRequest](UsersIdPatchRequest.md) |  | |

### Return type

[**UserDetail**](UserDetail.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 更新成功 |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersLoginPost

> UsersLoginPost200Response usersLoginPost(usersLoginPostRequest)

ログイン

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersLoginPostOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // UsersLoginPostRequest
    usersLoginPostRequest: ...,
  } satisfies UsersLoginPostOperationRequest;

  try {
    const data = await api.usersLoginPost(body);
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
| **usersLoginPostRequest** | [UsersLoginPostRequest](UsersLoginPostRequest.md) |  | |

### Return type

[**UsersLoginPost200Response**](UsersLoginPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 認証成功 |  -  |
| **400** | リクエストが不正です |  -  |
| **401** | 認証失敗 |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersMeGet

> UsersMeGet200Response usersMeGet()

認証済みユーザー情報

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersMeGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new UsersApi(config);

  try {
    const data = await api.usersMeGet();
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

[**UsersMeGet200Response**](UsersMeGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 成功 |  -  |
| **401** | 認証エラー |  -  |
| **404** | 対象が見つかりません |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersPost

> UserWithOffice usersPost(name, email, password, icon, officeCode)

ユーザー新規登録

フォームデータを受け取り、プロフィール画像をアップロードした上でユーザーを作成します。

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersPostRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // string
    name: name_example,
    // string
    email: email_example,
    // string
    password: password_example,
    // Blob | プロフィール画像ファイル
    icon: BINARY_DATA_HERE,
    // string | 登録先オフィスのコード（大文字・小文字は区別されません）
    officeCode: officeCode_example,
  } satisfies UsersPostRequest;

  try {
    const data = await api.usersPost(body);
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
| **name** | `string` |  | [Defaults to `undefined`] |
| **email** | `string` |  | [Defaults to `undefined`] |
| **password** | `string` |  | [Defaults to `undefined`] |
| **icon** | `Blob` | プロフィール画像ファイル | [Defaults to `undefined`] |
| **officeCode** | `string` | 登録先オフィスのコード（大文字・小文字は区別されません） | [Defaults to `undefined`] |

### Return type

[**UserWithOffice**](UserWithOffice.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | 作成成功 |  -  |
| **400** | リクエストが不正です |  -  |
| **409** | メールアドレス重複 |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersResetPasswordRequestPost

> MessageResponse usersResetPasswordRequestPost(usersResetPasswordRequestPostRequest)

パスワードリセット申請

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersResetPasswordRequestPostOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // UsersResetPasswordRequestPostRequest
    usersResetPasswordRequestPostRequest: ...,
  } satisfies UsersResetPasswordRequestPostOperationRequest;

  try {
    const data = await api.usersResetPasswordRequestPost(body);
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
| **usersResetPasswordRequestPostRequest** | [UsersResetPasswordRequestPostRequest](UsersResetPasswordRequestPostRequest.md) |  | |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 申請を受け付けました（対象ユーザーが存在しない場合も同様の応答） |  -  |
| **400** | リクエストが不正です |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersResetPasswordTokenPost

> MessageResponse usersResetPasswordTokenPost(token, usersResetPasswordTokenPostRequest)

パスワードリセット実行

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersResetPasswordTokenPostOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const api = new UsersApi();

  const body = {
    // string | リセットトークン
    token: token_example,
    // UsersResetPasswordTokenPostRequest
    usersResetPasswordTokenPostRequest: ...,
  } satisfies UsersResetPasswordTokenPostOperationRequest;

  try {
    const data = await api.usersResetPasswordTokenPost(body);
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
| **token** | `string` | リセットトークン | [Defaults to `undefined`] |
| **usersResetPasswordTokenPostRequest** | [UsersResetPasswordTokenPostRequest](UsersResetPasswordTokenPostRequest.md) |  | |

### Return type

[**MessageResponse**](MessageResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | パスワードをリセットしました |  -  |
| **400** | リクエストが不正です |  -  |
| **500** | 予期しないエラーが発生しました |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

