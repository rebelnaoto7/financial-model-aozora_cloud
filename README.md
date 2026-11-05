\# financial-model-aozora\_cloud



あおぞらクラウド向け財務モデルのリポジトリ。



\## ディレクトリ構成



| パス | 役割 | Git追跡 |

|---|---|---|

| `data/raw/` | 外部から取得した生データ | ❌ サンプル除く |

| `data/processed/` | 加工済みデータ | ❌ サンプル除く |

| `data/sample/` | ダミー/サンプルCSV | ✅ |

| `models/` | Pythonモデルスクリプト | ✅ |

| `outputs/` | モデル出力（CSV/PNG等） | ❌ |

| `notebooks/` | 検証用Jupyter Notebook | ✅ |



\## 環境構築


powershell  

python -m venv .venv

.\\.venv\\Scripts\\Activate.ps1

pip install pandas numpy matplotlib openpyxl

pip freeze > requirements.txt




\## 運用ルール



\- CSVは UTF-8 (BOM付き) / LF で保存

\- コミットメッセージは `prefix: description` 形式

&#x20; - `data:` / `model:` / `fix:` / `docs:` / `refactor:`

\- `main` への直push禁止。`feature/\*` ブランチでPR運用



\## 更新履歴



\- 2026-06-18: 初期セットアップ

