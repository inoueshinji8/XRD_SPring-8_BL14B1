# 放射光XRD高温高圧プレス装置　SPring-8_BL14B1-XRDPress


## 概要

SPring-8のQST専用ビームライン（BL14B1）に設置されているXRD高温高圧プレス装置のデータについて，特定の条件に基づいた連続する測定ファイルからスタック図を作成する．


![image](https://user-images.githubusercontent.com/38028745/133562394-ff25452d-9d4f-4af3-903e-fdfc3910da10.png)


## 対応機器

* **装置名**:　XRD高温高圧プレス装置
* **設置場所**：　SPring-8 BL14B1
* **設置機関**：　量子科学技術研究開発機構 (QST) 


## 想定利用

ユーザーからの測定依頼を機器管理者が受け，そのレポートとしてオリジナルファイル（rawデータ）のほかに，構造化されたデータおよびスタック図をサービスとして提供する．


* 一連の実験記録はExcelの『実験記録テンプレート』で記述し，実験記録を定点的に保全することができる．
* 記入されたテンプレートからスタック図を作成することで現場作業者の軽減を図ることができる．


## 動作確認環境

**IDE**:　anaconda　（spyder 4.X/ 5.X）  
**バージョン**：　python 3.8 , requirements.txtを参照

--------------------------------------------------------
## データ数値化・可視化コード (スペクトル出力)

必要なもの

* **rawデータ**: 	
  * .npdファイル　（複数ファイル可）

* **計測記録テンプレート**: 	
  * Bl14B1_XRDPress_Data_template_StackPlot.xlsx

* **コード**：	
  * SPring-8_BL14B1-XRDPress.py

❶　計測記録テンプレート（.xslx）に可視化図の低エネルギー，高エネルギ値，スタック間隔を記入．そのexcelファイルとrawデータ（.npd）とを"data"フォルタに配置．

❷　コードを走らせると”output”フォルダが作成される．その中に投入されたデータについて個別にスペクトルを描画，および数値ファイルをcsv化する．

❸　スタック図の作成は計測記録テンプレートの中の数値を参照してpng出力する．

--------------------------------------------------------
メタデータ抽出コード（XMLパーサー）
--------------------------------------------------------

必要なもの

* **rawデータ**：	
     * .npdファイル　（複数ファイル可）

* **コード**：	
     * SPring-8_BL14B1-XRDPress_xml.py　（パーサー）
     * metadata_schema.xml　（xmlテンプレート：スキーマ）
     * keypara.csv　（変換辞書）

❶　rawデータ（.npd）を"data"フォルタに配置.xmlのテンプレートと.csvの辞書は.pyと同じ階層に配置．  
❷　.pyをIDEでRunさせると同一階層にテンプレートとは別の抽出されたパラメータの.xmlが出力

<br>

<div align="center">                                                                                                                
<img src="https://user-images.githubusercontent.com/38028745/138789951-01ea1497-be71-437d-bf6e-33c96a9aa8c2.png" width = "800px">
</div>

<hr>

## 演習コード
Google Colabでステップ・バイ・ステップで動作を確認しながら進めます．下記のボタンを押して進んでください．

<div align="center">
  <a href="https://colab.research.google.com/github/inoueshinji8/XRD_SPring-8_BL14B1/blob/main/XRD_SPring-8_BL14B1_Training.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>
</div>

