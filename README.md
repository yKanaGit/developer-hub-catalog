# Developer Hub Catalog

このリポジトリは、Red Hat Developer Hubのカタログとテンプレートを管理します。

## 構成

- `catalog-info.yaml` - カタログのルート定義
- `users/org.yaml` - ユーザーとグループの定義
- `templates/` - Software Templatesディレクトリ
  - `quarkus-api/` - Quarkus REST APIテンプレート

## Developer Hubへの登録方法

1. Developer Hubにアクセス: https://redhat-developer-hub-ykanayam-dev.apps.rm1.0a51.p1.openshiftapps.com
2. GitHubでサインイン
3. 左メニューから "Create..." をクリック
4. "Register Existing Component" をクリック
5. このリポジトリのURLを入力:
   ```
   https://github.com/<your-username>/developer-hub-catalog/blob/main/catalog-info.yaml
   ```
6. "Analyze" → "Import" をクリック

## 開発者Aのオンボーディング手順

### 1. Developer Hubにアクセス
Developer AがGitHubアカウントでサインイン

### 2. 新しいプロジェクトの作成
1. 左メニューから "Create..." をクリック
2. "Quarkus REST API" テンプレートを選択
3. プロジェクト情報を入力:
   - Name: プロジェクト名（例: my-first-api）
   - Description: プロジェクトの説明
   - Owner: developer-a
4. リポジトリ情報を入力:
   - Owner: GitHubユーザー名
   - Repository: リポジトリ名
5. "Create" をクリック

### 3. 作成されたプロジェクトの確認
- GitHubに新しいリポジトリが自動作成されます
- Developer Hubのカタログに自動登録されます
- すぐに開発を開始できます

## 既存プロジェクトの登録

既存のプロジェクトをカタログに追加するには、リポジトリのルートに `catalog-info.yaml` を作成してください。

例:
```yaml
apiVersion: backstage.io/v1alpha1
kind: Component
metadata:
  name: my-existing-project
  description: My existing project description
  annotations:
    github.com/project-slug: <username>/my-existing-project
  tags:
    - java
    - quarkus
spec:
  type: service
  lifecycle: production
  owner: development-team
```
