# 人流データ標準変換ツール 

![概要](./img/MFConverter.png) <!-- OSSの対象物のスクリーンショット（画面表示がない場合にはイメージ画像）を貼り付けください -->


## 1. 概要
本リポジトリでは、Project PLATEAUの令和6年度のユースケース開発業務の一部であるUC24-07「汎用的な人流シミュレーションシステム」について、その成果物である「人流データ変換ツール」のソースコードを公開しています。

「人流データ標準変換ツール」は、様々な形式の人流データを読み込み、移動体データの国際標準形式である「MF-JSON」形式に変換するためのツールです。

## 2. 「人流データ標準変換ツール」について 
「汎用的な人流シミュレーションシステム」では、都市開発、観光関連施策、イベント開催等での歩行空間設計や群衆制御といった分野において、企画立案・合意形成・効果検証等における人流シミュレーションの活用促進を目的として本システムを開発しました。
本リポジトリでは、汎用的な人流シミュレーションシステムに実装された機能の一つである、様々な形式の人流データを国際規格である「MF-JSON」形式に変換する機能（人流データ標準変換ツール）を公開しています。
本ツールは、行政職員向けのGUIを備えたオープンソースソフトウェアとして開発されています。\
本ツールの詳細については[技術検証レポート](https://www.mlit.go.jp/plateau/file/libraries/doc/plateau_tech_doc_0102_ver01.pdf)を参照してください。

## 3. 利用手順
本システムの構築手順及び利用手順については[利用チュートリアル](https://project-plateau.github.io/MF-JSON-Converter/)を参照してください。

## 4. システム概要 
### 【人流データのMF-JSON形式への変換】
#### ①人流データ読み込み機能
- 所定の人流データを読み込みます。
- [株式会社ブログウォッチャー](https://www.blogwatcher.co.jp/)、[株式会社Agoop](https://agoop.co.jp/)、[株式会社Unerry](https://www.unerry.co.jp/)の提供する人流データのフォーマットに対応しています。
- 変換ルールを定義したiniファイルを別途作成し読み込むことでその他のデータフォーマットを取る人流データの変換（csv、json、xml形式）にも対応できます。

##### ②人流データ変換機能
- 読み込んだ人流データを汎用フォーマット人流データに変換します。
- 読み込んだ人流データが変換に対応しているフォーマットでなかった場合は、処理を中断します。

## 5. 利用技術
| 種別        | 名称     | バージョン   | 内容                        |
| ----------- | --------|-------------|-----------------------------|
| ソフトウェア | [Python](https://www.python.org/) |3.11  | インタープリンタ型の高水準汎用プログラミング言語 |
| ライブラリ   | [MF-JSON](https://docs.ogc.org/is/19-045r3/19-045r3.html) | なし | 3次元形状の物体の移動データをJSONを用いて記述する簡潔な記述形式 |
|             | [Pandas](https://pandas.pydata.org/) |2.2.3  | Pythonで利用可能なデータ解析を支援するライブラリ |
|             | [PySide6](https://pypi.org/project/PySide6/) |6.7.2  | Pythonで利用可能なGUI開発フレームワーク |

## 6. 動作環境
| 項目               | 最小動作環境                            | 推奨動作環境                                  | 
| ------------------ | -------------------------------------- | ------------------------------------------- | 
| OS                 | Microsoft Windows 10 または 11（64bit） | 同左                                        | 
| CPU                | Intel Core i5以上                      | 同左                                         | 
| GPU                | NVIDIA製GPU                            | NVIDIA Geforce GTX1650以上（4GB以上のメモリ） | 
| メモリ          　  | 4GB以上                                | 32GB以上                                    | 
| ストレージ          | 最低30GB以上の空き容量                  | SSDドライブ<br>最低60GB以上の空き容量          | 
| ディスプレイ解像度   | 1920×1080以上                          | 同左          　　　　　　　　               | 
| ネットワーク        | 必須                                   | 同左                                        | 

## 7. 本リポジトリのフォルダ構成

| フォルダ名Lv1　　| フォルダ名Lv2   　   |　詳細  |
|--------------|------------------|--------|
|MFConverter   |　　　　　　　　　　　| システムのソースコード |
|              |FormatData　　　　　|変換するデータの定義の管理  |
|              |GUI  　　　　　　　　|各GUIのデザインと動作の管理  |
|              |Utils　　　　　　　　| 経過時間管理 |


## 8. ライセンス

- ソースコード及び関連ドキュメントの著作権は国土交通省に帰属します。
- 本ドキュメントは[Project PLATEAUのサイトポリシー](https://www.mlit.go.jp/plateau/site-policy/)（CCBY4.0及び政府標準利用規約2.0）に従い提供されています。

## 9. 注意事項

- 本リポジトリは参考資料として提供しているものです。動作保証は行っていません。
- 本リポジトリについては予告なく変更又は削除をする可能性があります。
- 本リポジトリの利用により生じた損失及び損害等について、国土交通省はいかなる責任も負わないものとします。

## 10. 参考資料
- 技術検証レポート: https://www.mlit.go.jp/plateau/file/libraries/doc/plateau_tech_doc_0102_ver01.pdf
- PLATEAU WebサイトのUse caseページ「汎用的な人流シミュレーションシステム」: https://www.mlit.go.jp/plateau/use-case/uc24-07/
