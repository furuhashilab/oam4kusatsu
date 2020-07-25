# oam4kusatsu
草津市航空写真データの OpenAerialMap 投入

## 成果物
* OpenAerialMap への航空写真データ投入


## 仕様
* 撮影年月日は 2020/01/01 10:00-11:00JST で統一
* 
* 検索エリア https://map.openaerialmap.org/#/136.40625,35.45251649467912,5/square/1330020?date=year&_k=r42vls


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


<img  src="https://github.com/furuhashilab/oam4kusatsu/blob/master/data/%E4%BB%AE%E8%88%AA%E7%A9%BA%E5%86%99%E7%9C%9F%E6%92%AE%E5%BD%B1%E5%9B%B3%E9%83%AD%E5%89%B2%E5%9B%B32.jpg?raw=true" width="300">


## Members
@22hero1072, @reikomor, @shuntacarp, @naaao naaao, @MatsuyamaRan, @yunapanpan12, @Momotaroooo, @kokisano, @cancancanda and @mapconcierge


## slack
#hackathon202007openaerialmap

https://app.slack.com/client/T0AR23BM3/C018582BTUY/details/?cdn_fallback=2
