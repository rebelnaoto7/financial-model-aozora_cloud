# financial-model-aozora_cloud

「あおぞらクラウド」向けの財務モデルを、Python で作るためのリポジトリです。

> **English summary:** Repository scaffold for a Python-based financial model for "Aozora Cloud". It currently contains the folder structure, Git settings (`.gitignore` / `.gitattributes`) and working rules only; model code and data have not been added yet.

> [!NOTE]
> 現在は初期セットアップの段階です。フォルダ構成・Git の設定・運用ルールだけが入っていて、モデルのコードやデータは、まだありません。

## ディレクトリ構成

| パス | 役割 | Git で管理するか | 状態 |
|---|---|---|---|
| `data/raw/` | 外部から取得した生データ | しない（`.gitkeep` のみ） | 作成済み |
| `data/processed/` | 加工済みのデータ | しない（`.gitkeep` のみ） | 作成済み |
| `data/sample/` | ダミー・サンプルの CSV | する | 作成済み（空） |
| `outputs/` | モデルの出力（CSV・PNG など） | しない（`.gitkeep` のみ） | 作成済み |
| `models/` | Python のモデルスクリプト | する | 予定 |
| `notebooks/` | 検証用の Jupyter Notebook | する | 予定 |

## 環境構築

Windows（PowerShell）:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install pandas numpy matplotlib openpyxl
```

macOS / Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install pandas numpy matplotlib openpyxl
```

依存パッケージのバージョンを固定するときは、`pip freeze > requirements.txt` で `requirements.txt` を作ってコミットします。

## 運用ルール

- **データ**：`data/raw/` と `data/processed/` のデータ、`outputs/` の出力は Git に入れません（`.gitignore` で除外）。共有してよいサンプルだけを `data/sample/` に置きます。
- **文字コードと改行**：CSV は UTF-8（BOM 付き）・改行 LF で保存します。`.gitattributes` で `*.csv` `*.py` `*.md` `*.json` `*.yml` の改行を LF にそろえ、`*.xlsx` `*.xlsm` `*.pdf` `*.png` `*.jpg` はバイナリとして扱います。
- **コミットメッセージ**：`prefix: description` の形式にします。

  | prefix | 使うとき |
  |---|---|
  | `data:` | データの追加・更新 |
  | `model:` | モデルの追加・変更 |
  | `fix:` | 不具合の修正 |
  | `docs:` | ドキュメントの更新 |
  | `refactor:` | 動きを変えない整理 |

- **ブランチ**：`main` には直接 push せず、`feature/*` ブランチを作り、プルリクエストでマージします。

## 更新履歴

- 2026-06-18：初期セットアップ（フォルダ構成・`.gitignore`・`.gitattributes`・README）
