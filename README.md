# office-manager-api-client

入退室管理アプリの API を呼ぶための TypeScript クライアントです。iOS・Android アプリ（[office-manager-native](https://github.com/toma0705/office-manager-native)）が使っています。

> **このリポジトリのコードは手で書き換えないでください。**
> [okayama-office-manager](https://github.com/toma0705/okayama-office-manager)（web）の `openapi/openapi.yaml` から、[OpenAPI Generator](https://openapi-generator.tech/)（typescript-fetch）で自動生成しています。手で直しても、次の生成で消えます。

## 更新の流れ

```
web の openapi/openapi.yaml を変更して main にマージ
  ↓（web の GitHub Actions「API クライアントの更新」が自動で実行）
このリポジトリに「OpenAPI 仕様の更新を反映する」PR が作られる
  ↓ CI（ビルド）が通ったらマージ
package.json のバージョンでタグ（例: v8.0.0）が自動で付く
  ↓
native の package.json の "@office-manager/api-client" のタグを書き換える
```

バージョンは仕様の `info.version` です。互換性のない変更（項目やエンドポイントの削除・名前の変更）をしたら、先頭の数字を上げてください。

## 手元で生成する

web と api-client を同じフォルダに並べて置き、web で実行します（Java 17 以上が必要）。

```bash
cd web
npm run openapi:generate   # ../api-client に出力する
cd ../api-client
npm install && npm run build   # コンパイルが通るか確認する
```

## 使い方（native）

```ts
import { Configuration, UsersApi } from '@office-manager/api-client';

const api = new UsersApi(
  new Configuration({ basePath: 'https://okayama-office-manager.vercel.app/api', accessToken: token }),
);
const { user, enteredUsers } = await api.usersMeGet();
```

エンドポイントと型の一覧は [docs/](docs/) にあります（これも自動生成）。

## このリポジトリにあるもの

| パス | 内容 |
|---|---|
| `src/` | 生成されたコード（API と型） |
| `docs/` | 生成された説明 |
| `.openapi-generator-ignore` | 生成で上書きしないファイル（この README と `.github/`） |
| `.github/workflows/ci.yml` | PR でビルドが通るか確かめる |
| `.github/workflows/tag.yml` | main にバージョンが上がったら `v<バージョン>` のタグを付ける |
