# DB設計（論理・物理）

| テーブル名 | 主なカラム | 説明 |
|------------|------------|------|
| users | id, email, password_hash, role | 求職者・企業共通のアカウント情報 |
| profiles | user_id, name, occupation, skills, history, avatar_path, resume_path, is_public | 求職者プロフィール |
| companies | id, name, description, logo_path, tech_stack | 企業情報 |
| jobs | id, company_id, title, description, employment_type, salary_range, location, tags, is_public | 求人情報 |
| applications | id, job_id, user_id, status, applied_at | 求職者の応募履歴 |
| favorites | id, user_id, job_id, created_at | 求人のお気に入り |
| messages | id, sender_id, receiver_id, content, sent_at, thread_id | 企業と求職者のメッセージ |
| notifications | id, user_id, type, payload, is_read, created_at | 各種通知 |

各テーブルは外部キー制約を用いて関連付けられ、ユーザーおよび企業の操作履歴を追跡できるよう設計します。履歴書ファイルなどの大容量データはオブジェクトストレージに保存し、DBにはパスのみを保持します。
