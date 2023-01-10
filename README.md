# NDL Ngram Data
国立国会図書館が実施した「[令和3年度デジタル化資料のOCRテキスト化](https://lab.ndl.go.jp/data_set/ocr/r3_text/)」事業においてデジタル化資料から作成したOCRテキストデータのngram頻度統計情報のデータセットです。

## データセットの形式

1行ごとに「ngramキーワード」「総出現頻度」「出版年をキー、当該出版年における頻度を値とした頻度統計情報のjson」「データセット名」の4つの要素を含む、タブ区切り形式となっています。

例
```
いもほりに行く  6       {'1937': '1', '1922': '1', '1938': '1', '1935': '2', '1923': '1'}   tosho-pdm
```

分かち書きの条件等、詳細な集計方法については、[NDL Ngram Viewer(Version1)のソースコード](https://github.com/ndl-lab/ndlngramviewer_v1/tree/master/datacreationtools)を確認してください。

データサイズに比して総出現頻度の少ないngram（tosho-all及びzassi-allにおいて総出現頻度が概ね10未満のもの）については、集計時に取りこぼしが発生する場合があり、正確でない可能性があります。


なお、tosho-pdm、tosho-all及びzasshi-allは次のコマンドで辞書順にソート後、gzip圧縮しています。
```
LC_ALL=C.UTF-8 sort --buffer-size=300G --parallel=16 -t '\t' -k 1,1　(ソート元ファイル名) -o （公開データセット名）
```

### データセットの権利
「PDM（パブリック・ドメイン・マーク）」&lt; https://creativecommons.org/publicdomain/mark/1.0/deed.ja &gt;


このリポジトリで公開するデータセットは、自由な二次利用が可能です。ただし、二次利用に際しては、次の事項へのご配慮をお願いいたします。これらのお願いは法的な契約ではありませんが、できる限りご留意の上でご利用くださるよう、ご協力をお願いします。

- データを編集・加工等して利用する場合は、それを行ったことを記載してください。編集・加工等を、元となる作品・原資料の作者や当館が行なったかのような態様で公表しないようご留意ください。
- 当該データが自由に二次利用可能であることの表記を保持してください。
- 元となる作品や、その作者の名声を傷つける形での利用は行わないようご留意ください。また、元となる作品に関わる文化やコミュニティへの配慮を行ってください。
- 著作権以外の権利（著作者人格権、著作隣接権、肖像権、パブリシティ権、プライバシー権、商標権等）にも留意し、関連法令を遵守してください。


## 現在公開しているデータセットの情報

### 1. tosho-pdm: sorted-tosho-pdmngram.json.gz (20.7GB)

#### データセットのURL
https://lab.ndl.go.jp/dataset/ngramviewer/sorted-tosho-pdmngram.json.gz 

#### データセットの説明
著作権保護期間が満了した図書資料約28万点において、総出現頻度が4以上の1gramから5gramまで約8.3億ngram

### 2. tosho-all: sorted-tosho-allngram.json.gz (43.1GB)

#### データセットのURL
https://lab.ndl.go.jp/dataset/ngramviewer/sorted-tosho-allngram.json.gz

#### データセットの説明
図書資料約97万点において、総出現頻度が4以上の1gramから5gramまで約8.9億ngram


### 3. zasshi-all: sorted-zasshi-allngram.json.gz (38.6 GB)

#### データセットのURL
https://lab.ndl.go.jp/dataset/ngramviewer/sorted-zasshi-allngram.json.gz

#### データセットの説明
雑誌資料約132万点において、総出現頻度が4以上の1gramから5gramまで約8.5億ngram




