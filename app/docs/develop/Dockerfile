# ベースイメージとしてGoの公式ARM64対応版を使用
FROM --platform=linux/arm64 golang:1.23.4

# 環境変数を設定
ENV GO111MODULE=on \
    GOPATH=/go \
    PATH=$GOPATH/bin:/usr/local/go/bin:$PATH

# 必要なディレクトリを作成
WORKDIR /repo
COPY .. /repo

# 必要なツールをインストール
RUN apt-get update && apt-get install -y \
    git \
    vim \
    curl \
    zip \
    unzip \
    build-essential \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# ホスト側のファイルを同期するためにVOLUMEを設定
VOLUME ["/repo"]

# 開発用のシェルをデフォルトで起動
CMD ["bash"]
