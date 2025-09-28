#ベースイメージ
FROM python:3.13.7-slim

#作業ディレクトリ
WORKDIR /app

#wait-for-it.sh(appコンテナがdbコンテナの起動完了を待つスクリプト)をコンテナにコピー
COPY wait-for-it.sh /wait-for-it.sh

#必要パッケージのインストール
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# requirements.txtをコンテナに
COPY backend/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt