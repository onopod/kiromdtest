# API設計

RESTful APIを想定し、JSON形式でデータをやり取りします。主なエンドポイントの例を以下に示します。

## 認証
- `POST /api/auth/register` : ユーザー登録
- `POST /api/auth/login` : ログイン
- `POST /api/auth/oauth/{provider}` : SNSログイン

## 求人
- `GET /api/jobs` : 求人一覧の取得（クエリパラメータで検索条件指定）
- `GET /api/jobs/{id}` : 求人詳細の取得
- `POST /api/jobs` : 求人の新規登録（企業向け）
- `PUT /api/jobs/{id}` : 求人情報の更新（企業向け）

## 応募
- `POST /api/jobs/{id}/apply` : 求人への応募
- `GET /api/applications` : 応募履歴一覧
- `PATCH /api/applications/{id}` : 応募ステータスの更新

## メッセージ
- `GET /api/messages` : メッセージ一覧
- `POST /api/messages` : メッセージ送信

## 通知
- `GET /api/notifications` : 通知一覧
- `PATCH /api/notifications/{id}` : 既読更新
