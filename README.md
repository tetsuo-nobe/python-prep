# Python の開発・実行環境を用意する際の基本的な構成手順

---
## VS Code Server (on Ubuntu) で Python の開発・実行環境を用意する場合

### pyenv をインストールして 使用する Python のバージョンを決める

1. pyenv のインストール

    ```
    sudo apt update
    sudo apt install build-essential libffi-dev libssl-dev zlib1g-dev liblzma-dev libbz2-dev \
      libreadline-dev libsqlite3-dev libopencv-dev tk-dev git
    
    ```

1. githubより pyenvをクローン
    ```
    git clone https://github.com/pyenv/pyenv.git ~/.pyenv
    ```

1. .bashrcにpyenvの情報を追記して.bashrcを再読み込み

    ```
    echo '' >> ~/.bashrc
    echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
    echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
    source ~/.bashrc
    ```

1. pyenv の確認

    ```
    pyenv -v 
    ```

1. インストール可能なpythonバージョン一覧を表示

    ```
    pyenv install --list
    ```


1. 使用する Python をインストール

    ```
    pyenv install 3.11.13
    ```


1. 全体(デフォルト)で利用するバージョンの設定

    ```
    pyenv global 3.11.13
    ```

    ```
    python3 --version
    ```

---

### venv を起動してパッケージをインストール

    ```
    python -m venv .venv
    ```

    ```
    source .venv/bin/activate
    ```

* 終了するとき

    ```
    deactivate
    ```

---

### 環境で使用するパッケージをインストールする

    ```
    pip install streamlit
    pip install strands-agents
    pip install nest_asyncio
    pip install strands-agents-tools strands-agents-builder
    ```




