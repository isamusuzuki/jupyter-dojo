# jupyter-dojo 概要

Jupyter 道場（Jupyter Notebook サンプルコード集）

作業日 2023/08/30、更新日 2023/09/03

## 01. ファイル・フォルダ構成

```text
--jupyter-dojo/
    |--p100knocks/  ... 「Python 実践データ分析 100 本ノック」を写経
    `--study101/    ... 自分で勉強したコード
```

## 02. Python 環境の構築

- OS は WSL 上の Ubuntu 22.04 を想定
- エディタは Visual Studio Code を想定

```bash
cd ~/jupyter-dojo
python3 -m venv venv
source venv/bin/activate

pip install wheel
pip install -r requirements.txt -c constraints.txt
```

### .vscode/settings.json 設定例

※ `{{YOURNAME}}`は各自自分の名前に置き換える

```json
{
    "autoDocstring.docstringFormat": "numpy",
    "[python]": {
        "editor.defaultFormatter": "ms-python.autopep8",
        "editor.formatOnSave": true,
        "editor.codeActionsOnSave": {
            "source.organizeImports": true
        },
    },
    "terminal.integrated.env.linux": {
        "PYTHONPATH": "/home/{{YOURNAME}}/jupyter-dojo"
    }
}
```

### インストールしておくべき Visual Studio Code の機能拡張

- autoDocstring
- autopep8
- Flake8
- IntelliCode
- isort
- Jupyter
- markdownlint
- Pylance
- Python
- Rainbow CSV

## 03. スクリプト実行

新しくノートブックを作成する方法は以下の通り

- `Ctrl+Shift+P`でコマンドパレットを開き、`Create: New Jupyter Notebook`コマンドを選択する
- ノートブックの右上に`カーネルの選択`があるので、`venv(Python3.10.12)`を指定する
