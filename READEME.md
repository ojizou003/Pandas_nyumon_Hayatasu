# 「Pandas入門」 はやたす youtube

2023/10/9 ~ 10/12  

jupyter notebook を python ファイルに変換するコマンド

```! jupyter nbconvert --to python your_notebook.ipynb```

## Pandasとは？Pandasを学習すべき3つの理由

1. データ分析系の実務で必須、かつ最も使うライブラリだから
2. スクレイピングの取得結果を、そのまま加工・保存できるから
3. 個人でもおこなう株価・テクニカル分析を簡単に実装できるから

## 拡張機能を使ったJupyter環境の作成

1. Conda仮想環境の作成
2. ライブラリのインストール
3. 拡張機能の導入

Condaコマンドを使って仮想環境を作成するためには、以下のコマンドを入力  

    ``` conda create -n 環境名 python=Python Version  ```  
    ※conda info -eを実行すると、作成済みのConda環境一覧を確認できます！  

拡張機能の導入  
    拡張機能を使うためには、jupyter_contrib_nbextensionsをインストールする必要がある  
    ``` pip install jupyter_contrib_nbextensions ```  

入れておきたい拡張機能

- Table of Contents : 目次を追加する  
- Variable Inspector : 変数の一覧を表示する  
- Hinterland : 入力補完を使えるようにする  
- Codefolding : セル内のコードを折り畳めるようにする  

## DataFrameの特徴と作成方法

ライブラリのインポート  

    ```python
    import pandas as pd
    import numpy as np
    ```

Pandasでは、DataFrameという表形式のデータを操作することで、スムーズなデータの加工・集計・可視化が可能になる  

Pandas.DataFrameには、作成方法が複数ある

パターン① : 二次元リストから作成  
パターン② : 辞書から作成  
パターン③ : 辞書を格納したリストから作成  

## おすすめのDataFrameの作成方法

100件のデータを取得するようにパラメータ設定  
params = {
    'per_page': 100
}

APIにアクセスした結果を変数rに格納する  
r = requests.get('url', params=params)  

APIの取得結果を基にDataFrameを作成する  
df = pd.DataFrame(r.json())  

## CSV・Excelファイルの読み込み

- パターン① : 純粋にCSVやExcelを読み込む  
    pd.read_csv('ファイルパス + ファイル名')  
    pd.read_exel('ファイルパス + ファイル名')  
- パターン② : ヘッダーを指定してCSVやExcelを読み込む  
    header = index番号  
- パターン③ : 型を指定してCSVやExcelを読み込む  
    dtype = {カラム名 : データ型}  

