# BetterRightClick

## git環境

### 初回リポジトリ作成

    git init
    git remote add origin <接続するリポジトリ名>
    git pull
    git config --local user.name [name]
    git config --local user.email [email]
    git add Instructions.md
    git commit -m "first commit"
    git branch -M main
    git push -u origin main

## 初回準備

### 前提

WSL2 + docker環境は構築済みであること

### VSCode上で有効にしておく拡張機能

Dockerコンテナ上の環境で作業するために必要となる拡張機能を有効化しておくこと。  

    ms-vscode-remote.vscode-remote-extensionpack
    ms-vscode-remote.remote-wsl
    ms-vscode-remote.remote-containers
    ms-vscode-remote.remote-ssh
    ms-vscode.remote-server
    ms-vscode.remote-explorer


### docker起動

予めDockerのサービスを起動しておく。  
WSL2の起動に合わせることも出来る。  

    sudo service docker start

以下に実行権限を与えることで、Dockerサービスの起動とWorkSpaceの起動を同時に行う。  

    exec.sh

### コンテナの起動

#### workspaceをコンテナ上で開き直す。

コマンドパレットより以下を選択する。  

    Reopen in Container（コンテナーで再度開く）

※ この操作は初回時だけでなく、二度目以降も起動する際に必要となる操作。  

#### DockerImageのビルド

DockerImageが存在しないときに必要となる手順。  
「コンテナで再度開く」を選択後にメニューが続くので以下を選ぶ。  

    From 'Dockerfile' (DockerFileから)」となる

オプションで追加する環境を問われるが、何も選択せずにOKを押せば次に進む。  

ビルド成功後、コンテナに接続するとVSCodeが開き直す。  

### コンテナ環境の確認

以下コマンドでnode.jsとnpmのバージョンを確認しておく。  
以下は2024/6/06時点の実行結果  

    nUser@a265575f6bbd:/workspaces/CaptureSearchResult$ node -v
    v21.7.3
    nUser@a265575f6bbd:/workspaces/CaptureSearchResult$ npm -v
    10.5.0
    nUser@a265575f6bbd:/workspaces/CaptureSearchResult$
