# oam4kusatsu
草津市航空写真データの OpenAerialMap 投入

## 成果物
* OpenAerialMap への航空写真データ投入


## 仕様
* 撮影年月日は 2020/01/01 10:00-11:00JST で統一
* 生成する GeoTIFFファイルの座標参照系は EPSG:4326 
* XYZタイル作成は Zoomレベル 12-21 
* 検索エリア https://map.openaerialmap.org/#/136.40625,35.45251649467912,5/square/1330020?date=year&_k=r42vls

<img  src="https://github.com/furuhashilab/oam4kusatsu/blob/master/data/%E4%BB%AE%E8%88%AA%E7%A9%BA%E5%86%99%E7%9C%9F%E6%92%AE%E5%BD%B1%E5%9B%B3%E9%83%AD%E5%89%B2%E5%9B%B32.jpg?raw=true" width="300">


## 作業手順
### データのダウンロード
* [元データ置き場 on Googleドライブ](KusatsuCity4OpenData) ※ Slackチャンネルでアクセス権限付与手続きが必要
* 必要なファイルは TIFFファイル(.tif)とワールドファイル(.twf)がワンセット

### GeoTIFFへのファイル変換処理
* QGIS 3.14 をインストール
* TIFFファイルとワールドファイルを同一フォルダ内に配置して、TIFFファイルをQGISにドラッグ&ドロップ
* 座標参照系 EPSG:6674 に設定
* TIFF画像レイヤ名右クリック → エクスポート → 名前をつけて保存
* 生データ、GeoTIFF、座標参照系 EPSG:4326 ファイル名命名規則は DTxxxxx_epsg4326geotiff.tif (xxxxxは図幅番号)
* 生成したGeoTIFFファイルを [指定したGドライブ](https://drive.google.com/drive/folders/1cp1ty4WZrOo3iXu1js5NwNb-7e_Vx1xN?usp=sharing) に格納

### XYZタイルの作成
* QGIS 3.14 の "プロセシング" メニューから "ツールボックス" を選択
* ツールボックス内の "ラスタ" → "XYZタイルの生成（ディレクトリ形式）" を選択
* Extent は "レイヤの領域を使う" を選択し、TIFFファイルレイヤを選択。
* Minimum zoom は 12
* Maximum zoom は 21
* Dpiは 96
* Tile Format は JPG
* Quality は 90
* 出力データの保存先はログに記載される。かなりわかりにくい場所にある。 Macだと例えば /private/var/folders/dg/w9dz_yfx17lfwzjygzv_03k40000gn/T/processing_8f4aa41a893848f286b0f35460c7369d/e35e21193cf441728b5f333f2a965485/OUTPUT_DIRECTORY といった深い階層にデータが保存される。Macの場合 Finderのメニューから "移動" → "フォルダへ移動" を選択し、OUTPUT_DIRECTORY フォルダへのパスを貼り付けて移動する。

## XYZタイルのGドライブへのアップロード
* [指定のフォルダ](https://drive.google.com/drive/u/0/folders/1rQEcL_wGmj8ssol6LQFgMTX11NsNylZZ) 内に、図幅名のフォルダを作成して、その中にZoomレベルごとのフォルダをアップロードする。


## 作業の進捗方法
* [管理用データリストスプレッドシート](https://docs.google.com/spreadsheets/d/1f9-mlXkaxld9TZroGTvkc4dBFSnolbSo1ffRgwdGz9k/edit#gid=0)に、それぞれ担当者名と進捗報告を行う。

## Members
@22hero1072, @reikomor, @shuntacarp, @naaao naaao, @MatsuyamaRan, @yunapanpan12, @Momotaroooo, @kokisano, @cancancanda and @mapconcierge


## slack
#hackathon202007openaerialmap

https://app.slack.com/client/T0AR23BM3/C018582BTUY/details/?cdn_fallback=2
