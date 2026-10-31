# UsersApi

All URIs are relative to *https://okayama-office-manager.vercel.app/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**usersGet**](UsersApi.md#usersget) | **GET** /users | ユーザー一覧の取得 |
| [**usersIdDelete**](UsersApi.md#usersiddelete) | **DELETE** /users/{id} | ユーザー削除 |
| [**usersIdGet**](UsersApi.md#usersidget) | **GET** /users/{id} | ユーザー詳細の取得 |
| [**usersIdPatch**](UsersApi.md#usersidpatchoperation) | **PATCH** /users/{id} | メモの更新 |
| [**usersLoginPost**](UsersApi.md#usersloginpostoperation) | **POST** /users/login | ログイン |
| [**usersMeGet**](UsersApi.md#usersmeget) | **GET** /users/me | ログイン中のユーザーと、同じオフィスで入室中のユーザー |
| [**usersPost**](UsersApi.md#userspost) | **POST** /users | ユーザー新規登録 |
| [**usersResetPasswordRequestPost**](UsersApi.md#usersresetpasswordrequestpostoperation) | **POST** /users/reset-password-request | パスワード再設定の申請 |
| [**usersResetPasswordTokenPost**](UsersApi.md#usersresetpasswordtokenpostoperation) | **POST** /users/reset-password/{token} | パスワードの再設定 |



## usersGet

> Array&lt;UserListItem&gt; usersGet(officeCode)

ユーザー一覧の取得

ログイン中のユーザーに一覧を返す。&#x60;officeCode&#x60; を指定すると、そのオフィスのユーザーだけにする。

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new UsersApi(config);

  const body = {
    // string | 絞り込むオフィスのコード（大文字・小文字は区別しない） (optional)
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
| **officeCode** | `string` | 絞り込むオフィスのコード（大文字・小文字は区別しない） | [Optional] [Defaults to `undefined`] |

### Return type

[**Array&lt;UserListItem&gt;**](UserListItem.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 成功 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdDelete

> MessageResponse usersIdDelete(id)

ユーザー削除

本人のログイン用トークンでのみ操作できる。プロフィール画像も削除する。

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersIdDeleteRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new UsersApi(config);

  const body = {
    // number | ユーザー ID
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
| **200** | 削除成功 |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdGet

> UserSafe usersIdGet(id)

ユーザー詳細の取得

本人のログイン用トークンでのみ操作できる。

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersIdGetRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new UsersApi(config);

  const body = {
    // number | ユーザー ID
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
| **id** | `number` | ユーザー ID | [Defaults to `undefined`] |

### Return type

[**UserSafe**](UserSafe.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 成功 |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **404** | 対象が見つからない |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersIdPatch

> UserSafe usersIdPatch(id, usersIdPatchRequest)

メモの更新

本人のログイン用トークンでのみ操作できる。

### Example

```ts
import {
  Configuration,
  UsersApi,
} from '@office-manager/api-client';
import type { UsersIdPatchOperationRequest } from '@office-manager/api-client';

async function example() {
  console.log("🚀 Testing @office-manager/api-client SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new UsersApi(config);

  const body = {
    // number | ユーザー ID
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
| **id** | `number` | ユーザー ID | [Defaults to `undefined`] |
| **usersIdPatchRequest** | [UsersIdPatchRequest](UsersIdPatchRequest.md) |  | |

### Return type

[**UserSafe**](UserSafe.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | 更新成功 |  -  |
| **400** | リクエストが不正 |  -  |
| **401** | トークンがない、不正、または期限切れ |  -  |
| **403** | 本人以外のユーザーは操作できない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersLoginPost

> UsersLoginPost200Response usersLoginPost(usersLoginPostRequest)

ログイン

ログイン用トークン（JWT、180 日有効）を発行する。

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
| **400** | リクエストが不正 |  -  |
| **401** | メールアドレスまたはパスワードが違う |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersMeGet

> UsersMeGet200Response usersMeGet()

ログイン中のユーザーと、同じオフィスで入室中のユーザー

時間を過ぎた入退室の保留を確定してから返す。

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
| **401** | トークンがない、不正、または期限切れ |  -  |
| **404** | 対象が見つからない |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersPost

> UserSafe usersPost(name, email, password, icon, officeCode)

ユーザー新規登録

プロフィール画像（JPEG・PNG・GIF・WebP・HEIC）を 200KB 以下に圧縮して保存し、ユーザーを作る。 メールアドレスは @4nonome.com のみ。 

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
    // string | 登録先オフィスのコード（大文字・小文字は区別しない）
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
| **officeCode** | `string` | 登録先オフィスのコード（大文字・小文字は区別しない） | [Defaults to `undefined`] |

### Return type

[**UserSafe**](UserSafe.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | 作成成功 |  -  |
| **400** | リクエストが不正 |  -  |
| **409** | メールアドレスが登録済み |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersResetPasswordRequestPost

> MessageResponse usersResetPasswordRequestPost(usersResetPasswordRequestPostRequest)

パスワード再設定の申請

再設定ページの URL をメールで送る（30 分有効）。登録されていないメールアドレスでも同じ応答を返す。

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
| **200** | 申請を受け付けた |  -  |
| **400** | リクエストが不正 |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## usersResetPasswordTokenPost

> MessageResponse usersResetPasswordTokenPost(token, usersResetPasswordTokenPostRequest)

パスワードの再設定

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
    // string | メールで届いた再設定用のトークン
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
| **token** | `string` | メールで届いた再設定用のトークン | [Defaults to `undefined`] |
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
| **200** | パスワードを再設定した |  -  |
| **400** | リクエストが不正 |  -  |
| **500** | 予期しないエラー |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

