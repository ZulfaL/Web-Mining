# Konten Materi Web Mining

### Crawling

Crawling sama seperti kinerja search engine, yang melakukan pengindeksan untuk mengambil kumpulan halaman dari sebuah web. Langkah-langkah untuk melakukan crawling web adalah

1. Mencari website yang ingin di crawl datanya

2. Install scrapy di cmd, "pip install scrapy"

3. di cmd, ketik "scrapy startproject nama_folder".

4. pergi ke vscode, ke terminal ketik "scrapy genspider nama_folder link_web_yang_akan_di_crawl".

5. kemudian pergi ke folder yang telah dibuat tadi dan ketikkan code nya
   `import scrapy`

   

   ​    `name = 'data_produk'`

   ​    `start_urls = ['https://www.urbanicon.co.id/sale-products.html/']`

   

   ​    `def parse(self, response):`

   ​        `for element in response.css(".item"):`

   ​            `yield{`

   ​                `"nama brand" : element.css(".product-brand::text").get(),`

   ​                `"nama produk": element.css(".product-name a::text").get(),`

   ​                `"harga" : element.css(".price::text").get()`

   ​            `}`

6. pada terminal, ketik "scrapy crawl nama_folder -o nama_folder.json" untuk menyimpan hasil crawlnya 

7. Hasil crawl dapat dilihat di folder berformat json

   `[`

   `{"nama brand": "\n\t\t\t\t\t\tApple\t\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 40mm Alumunium Silver Case Seashell Sport Loop", "harga": "\n                    Rp 7.999.000                "},`

   `{"nama brand": "\n\t\t\t\t\t\tApple\t\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 40mm Alumunium Space Grey Case Black Sport Loop", "harga": "\n                    Rp 7.999.000                "},`

   `{"nama brand": "\n\t\t\t\t\t\tApple\t\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 44mm Alumunium Space Grey Case Black Sport Band", "harga": "\n                    Rp 8.499.000                "},`

   `{"nama brand": "\n\t\t\t\t\t\tApple\t\t\t\t\t", "nama produk": "Apple Sport Band 38 mm (PRODUCT) RED", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Band 38 mm (PRODUCT) RED", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Band 38 mm Yellow", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Band 38 mm Pebble", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Navy/Tahoe Blue Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Orange Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Tahoe Blue Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Pollen Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Red Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 42 mm Orange Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 42 mm Berry Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 42 mm Tahoe Blue Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 42 mm Tahoe Pollen Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 44mm Alumunium Space Grey Case Black Sport Band", "harga": "\n                    Rp 8.499.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 40mm Alumunium Silver Case Seashell Sport Loop", "harga": "\n                    Rp 7.999.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 40mm Alumunium Space Grey Case Black Sport Loop", "harga": "\n                    Rp 7.999.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Band 38 mm Midnight Blue", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Berry Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 38 mm Midnight Blue Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 42 mm Light Pink/Midnight Blue Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Sport Loop 42 mm Blue Stripe Woven Nylon", "harga": "\n                    Rp 900.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 44mm Alumunium Space Grey Case Black Sport Loop", "harga": "\n                    Rp 8.499.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 40mm Alumunium Space Grey Case Black Sport Band", "harga": "\n                    Rp 7.999.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS 40mm Alumunium Gold Case Pink Sand Sport Loop", "harga": "\n                    Rp 7.999.000                "},`

   `{"nama brand": "\r\n\t\t\t\t\tApple\t\t\t\t", "nama produk": "Apple Watch Series 4 GPS Nike+ 40mm Alumunium Space Grey Case Black Sport Loop", "harga": "\n                    Rp 7.999.000                "}`

   `]`



### Preprocessing

Preprocessing adalah proses untuk mempersiapkan data sehingga dapat di proses dan diolah oleh sistem.

Berikut code dari preprocessing data

`import re`

`import string`

`import csv`

`import pandas as pd`

`from sklearn.feature_extraction.text import CountVectorizer`

`from sklearn.feature_extraction.text import TfidfTransformer`

`from nltk.tokenize.punkt import PunktSentenceTokenizer`

`from nltk.tokenize import word_tokenize`

`from Sastrawi.Stemmer.StemmerFactory import StemmerFactory`

`from Sastrawi.StopWordRemover.StopWordRemoverFactory import StopWordRemoverFactory`

`from newspaper import Article #melakukan import module newspaper`



`\#Scrapping`

`def getUrl(address):`

​    `url = address #isi url berita`

​    `article = Article(url) #membuat variabel yang digunakan untuk memanggil Class Article dan menambahkan parameter url`

​    `article.download() #melakukan download data dari sebuah halaman website`

​    `article.parse() #melakukan proses parsing atau pengambilan berita`

​    `berita = article.text`

​    `praproses(berita)`



`\#Text Processing`

`def praproses(text): #fungsi preprocesing text`

​    `\#----------- Step1 Case Folding merubah atau menghilangkan karakter yang tidak perlu ------------`

​    `text.lower() #merubah semua huruf ke huruf kecil`

​    `text = re.sub(r'\d+', '', text) #menghapus berdasarkan regular expression (angka 0 - 9)`



​    `\#----------- Step2 Tokenizing data / memisahkan setiap kata ------------`

​    `doc_tokenizer = PunktSentenceTokenizer()`

​    `sentences_list = doc_tokenizer.tokenize(text)`

​    `tempText2 = []`

​    `for i in sentences_list:`

​        `getTanslate = i.translate(str.maketrans("","",string.punctuation)) #menghapus tanda baca , . dsb`

​        `tempText2.append(getTanslate) #tokenizing kata dari data text dengan menggunakan nltk tokenizing`



​    `\#----------- Step3 Filtering stopword / penghapusan kata yang tidak penting  ------------`

​    `tempText3 = []`

​    `factory_stopword = StopWordRemoverFactory()`

​    `stopword = factory_stopword.create_stop_word_remover()`

​    `for i in tempText2:`

​        `removed = stopword.remove(i)`

​        `tempText3.append(removed)`



​    `\#----------- Step4 Stemming / menghilangkan infleksi atau kata imbuhan ke bentuk kata dasar ------------`

​    `hasil = []`

​    `factory_stemm = StemmerFactory()`

​    `stemm = factory_stemm.create_stemmer()`

​    `for i in tempText3:`

​        `stemmed = stemm.stem(i)`

​        `hasil.append(stemmed)`

​    `print(hasil)`



​    `vsmTfidf(hasil) #melakukan return berupa hasil akhir text yang sudah diproses tadi`



`\#VSM dan TfIdf`

`def vsmTfidf(text): #fungsi vsmtfidf`

​    `hasil = text`

​    `count = CountVectorizer()`

​    `bag = count.fit_transform(hasil)`

​    `feature = count.get_feature_names()`

​    `a = feature`

​    `matrik_vsm = bag.toarray()`

​    `dfVsm = pd.DataFrame(data=matrik_vsm,index=list(range(1, len(matrik_vsm[:,1])+1, )),columns=a)`

​    `dfVsm.to_csv(r'vsm.csv')`

​    `print(dfVsm)`



​    `tfidf = TfidfTransformer(use_idf=True, norm='l2', smooth_idf=True) #memanggil class tfidfTransformer dengan parameter dan menyimpannya ke variabel`

​    `convertarray = tfidf.fit_transform(count.fit_transform(hasil)).toarray() #menghitung data dari dataframe dan menyimpannya ke variabel dalam bentuk array`

​    `print(convertarray) #melakukan print hasil perhitungan`



​    `print("=========== Exporting to csv ===========")`

​    `dfbtf = pd.DataFrame(data=convertarray, columns=a) #membuat sebuah dataframe baru dengan data yang sudah kita hitung tfidf nya`

​    `dfbtf.to_csv(r'tfidftweet.csv') #melakukan export dataframe kedalam csv file`



`getUrl("https://www.medcom.id/teknologi/news-teknologi/yNL4VP2N-berita-teknologi-terpopuler-nokia-5-4-hingga-poco-x3/")`



### Modelling

Modelling adalah proses untuk menemukan kelompok pada sebuah kata dari dokumen yang diberikan. Misalnya seperti 'penyakit', 'kanker', 'pasien', 'dokter' akan mewakili kelompok 'kesehatan'.

![[1*cDwKSHmfp5awjqjobV707g.png () (medium.com)](https://miro.medium.com/max/2796/1*cDwKSHmfp5awjqjobV707g.png)]()

- Kasus penggunaan dari topik modelling adalah:
- Ringkasan Resume
- Search Engine Optimization
- Pengoptimalan Sistem Rekomendasi
- Meningkatkan Dukungan Pelanggan

Dalam industri perawatan kesehatan, pemodelan topik dapat membantu kita mengekstrak informasi yang berguna dan berharga dari laporan medis yang tidak terstruktur. Informasi ini dapat digunakan untuk pengobatan pasien dan tujuan penelitian ilmu kedokteran. 



### Metode Evaluasi Ringkasan Otomatis

ROUGE adalah yang paling banyak digunakan untuk mengevaluasi secara otomatis. Berikut metode yang paling banyak digunakan. 

- ROUGE-n. 
  Metode ukurannya didasarkan pada recall dan didasarkan pada membandingkan dari n-gram.
- ROUGE-L. 
  Ukuran ini menggunakan Uprangkaian bersama terpanjang (Longest
  common subsequence) diantara serangkaian teks. Artinya semakin panjang LCS antara dua
  ringkasan kalimat maka semakin mirip.
- ROUGE-W
  ROUGE-L mempertimbangkan LCS tetapi tidak memberikan preferensi pada kalimat yang
  memiliki kata-kata yang lebih berurutan.
- ROUGE-S
  ROUGE-S mengukur kejadian bersama skip bigram pada ringkasan rujukan dan ringkasan mesin.
- ROUGE-SU
  Kelemahan dari ROUGE-S adalah hanya memperhatikan bigrams. JIka kalimat tidak berisi satu bigram yang overlaping maka tidak a kan menghasilkan bobot pada kalimat. Untuk mengatasi masalah ini ROUGE-S ini maka munculllah ROUGE-SU yang merupakan pengembangannya yang juga memperhatikan unigram.

`Implementasi Rouge dengan python`
`Instalasi library`
`atau`
`pip install git+https://github.com/tagucci/pythonrouge.gitImplementasi kedua`
`pip install easy-rouge`
`from rouge.rouge import rouge_n_sentence_level`
`summary_sentence = 'the capital of China is Beijing'.split()`
`reference_sentence = 'Beijing is the capital of China'.split()`

`recall, precision, rouge = rouge_n_sentence_level(summary_sentence,`
`reference_sentence, 2)`
`print('ROUGE-2-R', recall)`
`print('ROUGE-2-P', precision)`
`print('ROUGE-2-F', rouge)`
`ROUGE-2-R 0.6`
`ROUGE-2-P 0.6`
`ROUGE-2-F 0.6`
`ROUGE-2-R 0.6`
`from rouge import rouge_n_sentence_level`
`from rouge import rouge_l_sentence_level`
`from rouge import rouge_n_summary_level`
`from rouge import rouge_l_summary_level`
`from rouge import rouge_w_sentence_level`
`from rouge import rouge_w_summary_level`
`reference_sentence = 'the police killed the gunman'.split()`
`summary_sentence = 'the gunman police killed'.split()`
`print('Sentence level:')`
`score = rouge_n_sentence_level(summary_sentence, reference_sentence, 1)`
`print('ROUGE-1: %f' % score.f1_measure)`
`_, _, rouge_2 = rouge_n_sentence_level(summary_sentence, reference_sentence, 2)`
`print('ROUGE-2: %f' % rouge_2)`
`_, _, rouge_l = rouge_l_sentence_level(summary_sentence, reference_sentence)`
`print('ROUGE-L: %f' % rouge_l)`
`_, _, rouge_w = rouge_w_sentence_level(summary_sentence, reference_sentence)`
`print('ROUGE-W: %f' % rouge_w)`
`Sentence level:`
`ROUGE-1: 0.888889`
`ROUGE-2: 0.571429`
`ROUGE-L: 0.666667`
`ROUGE-W: 0.550527Outputnya adalah`
`Outputnya adalah`
`from rouge import rouge_n_sentence_level`
`from rouge import rouge_l_sentence_level`
`from rouge import rouge_n_summary_level`
`from rouge import rouge_l_summary_level`
`from rouge import rouge_w_sentence_level`
`from rouge import rouge_w_summary_level`
`reference_sentences = ['The gunman was shot dead by the police before more`
`people got hurt'.split(),`
`'This tragedy causes lives of five , the gunman included'.split(),`
`'The motivation of the gunman remains unclear'.split(),`
`]`
`summary_sentences = [ 'Police killed the gunman . no more people got`
`hurt'.split(),`
`'Five people got killed including the gunman'.split(),`
`'It is unclear why the gunman killed people'.split(),`
`]`
`print('Summary level:')`
`_, _, rouge_1 = rouge_n_summary_level(summary_sentences, reference_sentences, 1)`
`print('ROUGE-1: %f' % rouge_1)`
`_, _, rouge_2 = rouge_n_summary_level(summary_sentences, reference_sentences, 2)`
`print('ROUGE-2: %f' % rouge_2)`
`_, _, rouge_l = rouge_l_summary_level(summary_sentences, reference_sentences)`
`print('ROUGE-L: %f' % rouge_l)`
`_, _, rouge_w = rouge_w_summary_level(summary_sentences, reference_sentences)`
`print('ROUGE-W: %f' % rouge_w)`
`Summary level:`
`ROUGE-1: 0.400000`
`ROUGE-2: 0.188679`
`ROUGE-L: 0.327273`
`ROUGE-W: 0.200430`
`recall, precision, rouge_1 = rouge_n_summary_level(summary_sentences,`
`reference_sentences, 1)`
`print('ROUGE-2-R', recall)`
`print('ROUGE-2-P', precision)`
`print('ROUGE-2-F', rouge)ROUGE-2-R 0.36666666666666664`
`ROUGE-2-P 0.44`
`ROUGE-2-F 0.6`