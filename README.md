# 🚗 GTSRB Traffic Sign Classifier (Python Only Version)

本プロジェクトは、**自動運転分野における交通標識の分類**を題材に、  
**PyTorchによるモデル構築・学習・推論までをPythonで一貫して行う**ものです。

---

## 🎯 目的

本プロジェクトの目的は、**深層学習による画像分類タスクの流れを実践的に理解すること**です。

特に以下のプロセスを一通り体験することで、実務でも求められる機械学習の基礎スキルを習得できます：

- **EDA（探索的データ分析）によるデータ理解**
- **PyTorchによる軽量CNNモデルの構築**
- **学習済みモデルの保存（`.pt`, `.ts`）と再利用**
- **TorchScriptによる推論モデルのデプロイ準備**
- **Pythonでの推論処理と結果の可視化**

当初はC++（libtorch）による推論実装も検討していましたが、対象環境が `aarch64（ARM）` であり、libtorchのC++バイナリが未対応だったため、本プロジェクトでは **Pythonベースに一本化**しています。

---

## 🛠 使用技術

| 領域       | 使用技術                           |
|------------|------------------------------------|
| モデル開発 | Python, PyTorch, TorchScript       |
| 可視化     | matplotlib, PIL                    |
| データ処理 | pandas, torchvision.transforms     |
| 開発環境   | VS Code, venv, Jupyter Notebook    |

---

## 📁 ディレクトリ構成

```
project-root/
├── data/               # GTSRB画像（Train/Test）
├── model/              # TorchScript保存モデル（.pt）
├── notebooks/          # EDA用Notebook
├── python_training/    # Python学習コード（train_model.py など）
├── README.md           # このプロジェクトについて
├── requirements.txt    # Python依存関係
└── venv/               # Python仮想環境
```

---


---

## 📋 WBS（作業分解構造）

| No | タスク名                           | 工数(h) | 予定日  | 実施日  | ステータス | 備考 |
|----|------------------------------------|---------|---------|---------|------------|------|
| 1  | GTSRBのデータDLと展開とWBS作成    | 1.0     | 5/12    | 5/12    | ✅ 完了     | Kaggleより取得・解凍 |
| 2  | データ可視化・EDA                 | 3.0     | 5/13    | 5/15    | ✅ 完了     | クラス分布、画像数など |
| 3  | モデル構築（PyTorch）             | 4.0     | 5/13    | 5/19    | ✅ 完了     | 軽量CNNを設計 |
| 4  | モデル学習＆TorchScript保存       | 4.0     | 5/14    | 5/19    | ✅ 完了     | `.pt`形式と`.ts`形式で保存 |
| 5  | Pythonで推論実装（TorchScript）   | 2.0     | 5/20    | 5/19       | ✅ 完了   | `.ts`モデルを読み込んで推論 |
| 6  | 推論結果の可視化と検証            | 2.0     | 5/20    | 5/19       | ✅ 完了    | ラベル対応表、画像と出力の確認 |
| 7  | 成果物整理（Notebook/GitHub公開） | 2.0     | 5/21    | 5/19       | ✅ 完了    | 実行方法、Notebook整理、README |

---

## 🔽 データの入手方法

本プロジェクトで使用しているデータセットは Kaggle にて公開されています：  
[GTSRB - German Traffic Sign Recognition Benchmark](https://www.kaggle.com/datasets/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign)

上記ページから `gtsrb-german-traffic-sign.zip` をダウンロードし、展開後、`data/` フォルダとしてプロジェクト直下に配置してください。

---

## 📈 実行例・成果物（予定）

- 分類精度：約98.8%
- サンプル推論結果（画像＋予測クラス）
- `.pt`, `.ts` ファイルを使った再利用可能なモデル
- Notebookベースでの再現可能な分析＆推論フロー
