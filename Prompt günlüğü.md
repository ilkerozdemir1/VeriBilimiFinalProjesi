### PROMPT GÜNLÜĞÜ

##### 

##### Aşama 1: Veri Yükleme ve Temizleme

Prompt 1 (Kütüphaneler ve Yükleme):



"Bir veri bilimi projesine başlıyorum. Veri setim 'Online Retail.csv'. Pandas, NumPy, Matplotlib ve Seaborn kütüphanelerini içe aktaran, veriyi bir DataFrame'e yükleyen (encoding='unicode\_escape' kullanarak) ve ilk 5 satırını, veri tiplerini (df.info()) gösteren Python kodunu yazar mısın? Lütfen kod bloklarına açıklayıcı yorum satırları ekle."



Prompt 2 (Eksik Veriler):



"Şimdi veri setindeki eksik değerleri analiz etmek istiyorum. Her sütundaki eksik veri sayısını ve oranını gösteren bir kod yaz. Ardından, 'CustomerID' sütunu eksik olan satırları veri setinden tamamen çıkaran ve 'Description' sütunundaki eksiklikleri 'Bilinmiyor' olarak dolduran kodu ekle."



Prompt 3 (Tip Dönüşümleri):



"Veri setindeki 'InvoiceDate' sütunu şu an string formatında. Bu sütunu datetime formatına çeviren, ardından bu tarihten 'Year', 'Month', 'Day', 'DayOfWeek' ve 'Hour' isimli 5 yeni özellik (feature) üreten kodu yazar mısın?"



Prompt 4 (Aykırı Değerler ve Mantıksal Hatalar):



"E-ticaret verisinde iptal edilen siparişler 'InvoiceNo' sütununda 'C' harfi ile başlıyor ve 'Quantity' değerleri negatif. Negatif veya sıfır 'Quantity' ve 'UnitPrice' değerine sahip satırları veri setinden temizleyen kodu yaz. Ayrıca 'Quantity' ve 'UnitPrice' için çeyrekler açıklığı (IQR) yöntemini kullanarak aşırı uç (outlier) değerleri baskılayan (clipping) bir fonksiyon yaz."

##### 

##### 

##### Aşama 2: Keşifsel Veri Analizi (EDA)

Prompt 5 (Temel İstatistikler ve Toplam Tutar):



"Veri setinde her işlem için 'Quantity' ve 'UnitPrice' çarpımıyla 'TotalPrice' (Toplam Tutar) adında yeni bir sütun oluştur. Ardından sayısal değişkenler için temel istatistiksel özetleri (describe) gösteren kodu yaz."



Prompt 6 (Görselleştirme 1 \& 2 - Çubuk Grafik ve Zaman Serisi):



"Şimdi EDA aşamasına geçiyoruz. 1. En çok sipariş verilen ilk 10 ülkeyi (Birleşik Krallık hariç, çünkü veriyi çok domine ediyor) gösteren bir yatay çubuk grafik (bar chart) çiz. 2. Aylara göre toplam ciro (TotalPrice) değişimini gösteren bir çizgi grafik (line chart) çiz. Grafikler Matplotlib/Seaborn ile olsun ve başlık, eksen isimleri içersin."



Prompt 7 (Görselleştirme 3 \& 4 - Kutu Grafiği ve Histogram):



"EDA'ya devam ediyoruz. 3. Haftanın günlerine göre sipariş sayılarının dağılımını gösteren bir histogram veya sayım grafiği (count plot) çiz. 4. En çok sipariş veren ilk 5 ülkenin sipariş tutarı (TotalPrice) dağılımlarını karşılaştırmak için bir kutu grafiği (boxplot) çiz. Aykırı değerleri grafikte gizleyebilirsin (showfliers=False)."

##### 

##### 

##### Aşama 3: Araştırma Sorularının Yanıtlanması

Prompt 8 (RQ1 \& RQ2 Yorumlama):



"Şu ana kadar yaptığımız EDA adımlarına dayanarak şu iki araştırma sorusuna notebook içinde markdown formatında yanıt yaz: 1) Hangi ülkeler toplam ciroda en büyük paya sahip? 2) Müşterilerin satın alma davranışlarında aylık ve günlük nasıl bir trend var? Kısa ve veriye dayalı yorumlar olsun."

##### 

##### 

##### Aşama 4: Basit Modelleme (RFM \& K-Means Kümeleme)

Prompt 9 (RFM Metriklerinin Hazırlanması):



"Üçüncü araştırma sorumuz (RQ3) olan müşteri segmentasyonu için RFM (Recency, Frequency, Monetary) analizi yapacağız. Veri setindeki en son işlem tarihinden 1 gün sonrasını referans tarihi alarak; her 'CustomerID' için Recency (son alışverişten geçen gün), Frequency (eşsiz fatura sayısı) ve Monetary (toplam harcama) değerlerini hesaplayan kodu yaz."



Prompt 10 (Veri Ölçeklendirme):



"RFM verilerindeki çarpıklığı gidermek için Recency, Frequency ve Monetary sütunlarına logaritmik dönüşüm (np.log1p) uygulayan ve ardından StandardScaler ile veriyi standartlaştıran kodu yazar mısın?"



Prompt 11 (K-Means ile Kümeleme):



"Standartlaştırılmış RFM verisi üzerinde Scikit-Learn kullanarak K-Means kümeleme modeli kurmak istiyorum. Önce Elbow (Dirsek) yöntemini kullanarak optimum küme sayısını bulmak için bir grafik çizen kod yaz. Grafikten sonra, n\_clusters=3 (veya 4) seçerek modeli eğiten ve küme etiketlerini orijinal RFM veri setine 'Cluster' olarak ekleyen kodu sağla."



Prompt 12 (Model Sonuçlarının Yorumlanması):



"Oluşturduğumuz kümelerin (Cluster) her biri için Recency, Frequency ve Monetary medyan (ortanca) değerlerini gruplayarak (groupby) gösteren kodu yaz. Ardından bu 3 kümeyi iş bağlamında yorumlayan (Örn: 'Sadık Müşteriler', 'Kaybedilmek Üzere Olanlar', 'Yeni Müşteriler') kısa bir markdown metni oluştur."

