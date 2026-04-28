# training-db

MySQL 8.0 を Docker Compose で起動するための開発用 DB 環境です。

## 導入手順

### 1. 前提条件
- Docker Desktop（または Docker Engine + Docker Compose）がインストール済みであること

### 2. 環境変数ファイルを作成
`.env.sample` をコピーして `.env` を作成し、値を設定します。

```bash
cp .env.sample .env
```

`.env` の例:

```env
MYSQL_ROOT_PASSWORD=rootpass
MYSQL_USER=testuser
MYSQL_PASSWORD=testpass
```

### 3. コンテナを起動
以下のコマンドで MySQL コンテナをバックグラウンド起動します。

```bash
docker compose up -d
```

### 4. 起動確認
コンテナが起動していることを確認します。

```bash
docker compose ps
```

### 5. 停止する場合

```bash
docker compose down
```

データ（ボリューム）も削除する場合:

```bash
docker compose down -v
```

### 6. コンテナに入る
MySQL コンテナのシェルに入る場合:

```bash
docker compose exec mysql bash
```

### 7. MySQL に入る
MySQL クライアントに接続する場合:

```bash
docker compose exec mysql mysql -u root -p
```

`-p` 実行後に、`.env` に設定した `MYSQL_ROOT_PASSWORD` を入力してください。
