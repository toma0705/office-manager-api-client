# Office Manager API Client

Office Manager システムのバックエンド API と通信するための TypeScript クライアントライブラリです。`office-manager-next` (Web) の OpenAPI 定義から自動生成され、`office-manager-native` (Mobile) やその他のクライアントアプリケーションで共通利用されます。以下は仕様の概要、採用技術、実装上のポイント、利用方法をまとめたものです。

## 技術スタックと選定理由

| 技術              | バージョン/ライブラリ | 選定理由                                                                                                          |
| ----------------- | --------------------- | ----------------------------------------------------------------------------------------------------------------- |
| OpenAPI Generator | typescript-fetch      | API 定義書 (OpenAPI 3.0) から型安全なクライアントコードを自動生成し、手動実装のコストとミスを削減するため。       |
| TypeScript        | ~4.0                  | API のリクエスト・レスポンス型を厳密に定義し、利用側での開発効率と安全性を高めるため。                            |
| Fetch API         | Native                | ブラウザおよび React Native 環境で標準的に利用可能な Fetch API をベースとし、追加の依存関係を最小限に抑えるため。 |

## 機能概要

- **型安全な API コール**: リクエストパラメータ、レスポンスボディの型定義が完備されており、IDE の補完が効きます。
- **API モジュール**: 機能ごとに分割された API クラスを提供します。
  - `UsersApi`: ユーザー認証、プロフィール取得、パスワードリセットなど。
  - `OfficesApi`: オフィスの入退室、ユーザー一覧取得など。
  - `MaintenanceApi`: システムメンテナンス、ヘルスチェック用。
  - `NotificationsApi`: 通知関連の操作。
- **モデル定義**: API で使用されるデータ構造（DTO）の型定義を提供します（例: `UserDetail`, `Office`, `ErrorResponse`）。

## 技術的なポイント

- **OpenAPI 定義からの自動生成**: `office-manager-next` プロジェクトで管理されている `openapi.yaml` を正とし、そこから自動生成されます。これにより、サーバーサイドの実装とクライアントのインターフェースの乖離を防ぎます。
- **Isomorphic**: ブラウザ (Web) と React Native (Mobile) の両方の環境で動作するように設計されています。
- **Configuration**: ベース URL や認証ヘッダー（Bearer Token）などを `Configuration` オブジェクトを通じて注入可能です。ミドルウェア的な処理（トークンリフレッシュ等）は利用側のラッパーで実装することを想定しています。

## ディレクトリ構成

```
src/
  apis/               // API クラス群 (UsersApi, OfficesApi 等)
  models/             // データモデル型定義 (UserDetail, Office 等)
  index.ts            // エントリポイント
  runtime.ts          // Fetch API ラッパーや設定クラスを含むランタイム
```

## セットアップ手順

本パッケージは通常、他のプロジェクトから依存関係としてインストールされます。

1. 依存関係のインストール

   ```bash
   npm install
   ```

2. ビルド（開発時）

   TypeScript ソースコードを JavaScript にコンパイルします。

   ```bash
   npm run build
   ```

## 利用方法

### 初期化と API 呼び出し

`Configuration` クラスを使用して、API のベース URL や認証トークンを設定します。

```typescript
import {
  Configuration,
  UsersApi,
  OfficesApi,
} from "@office-manager/api-client";

// 設定の初期化
const config = new Configuration({
  basePath: "https://api.office-manager.example.com", // API のベース URL
  accessToken: async () => {
    // トークン取得ロジック (例: SecureStore や localStorage から取得)
    // 必要に応じて非同期処理が可能
    return "your-access-token";
  },
});

// API インスタンスの生成
const usersApi = new UsersApi(config);

// API 呼び出し例
async function fetchUserProfile() {
  try {
    const user = await usersApi.usersMeGet();
    console.log("User:", user);
  } catch (error) {
    console.error("Failed to fetch user:", error);
  }
}
```

## 更新フロー

API 仕様が変更された場合の更新手順は以下の通りです。

1. `office-manager-next` 側の `openapi/openapi.yaml` が更新される。
2. 生成スクリプト（例: `office-manager-next` 内の `npm run openapi:generate` 等）を実行し、クライアントコードを再生成する。
3. 生成されたコードを本リポジトリ（`office-manager-api-client`）に反映し、バージョンを更新してビルド・公開する。
