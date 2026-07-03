================================================================
E-TİCARET VERİ ANALİZİ VE RFM SEGMENTASYONU PROJESİ
================================================================

1. PROJE KİMLİĞİ
----------------------------------------------------------------
- Proje Başlığı: E-Ticaret Veri Analizi ve Müşteri Segmentasyonu
- Öğrenci No: 1306240061
- Ad Soyad: İlker Özdemir
- Hazırlanma Tarihi: 03.07.2026
- Proje GitHub URL: https://github.com/ilkerozdemir1/VeriBilimiFinalProjesi

2. VERİ KAYNAĞI VE LİSANS
----------------------------------------------------------------
- Veri Seti Adı: E-Commerce Data (Online Retail)
- Kaynak: Kaggle
- Veri Seti URL: https://www.kaggle.com/datasets/carrie1/ecommerce-data?resource=download
- Lisans: Unknown (Veri setinin kaynağında lisans bilgisi belirtilmemiştir.)
  * Proje, eğitim amaçlı ve kişisel analiz kapsamında yürütülmüştür. 
    Verinin ticari kullanımı için orijinal kaynak ile iletişime geçilmesi önerilir.

3. PROJEYİ ÇALIŞTIRMA TALİMATLARI (ADIM ADIM)
----------------------------------------------------------------
Adım 1: Gerekli ortamı hazırlayın. (Python 3.x yüklü olduğundan emin olun.)
Adım 2: Terminali açın ve gerekli kütüphaneleri şu komutla yükleyin:
        pip install pandas numpy matplotlib seaborn scikit-learn
Adım 3: Kaggle'dan indirdiğiniz 'data.csv' dosyasını proje ana dizinine kopyalayın.
Adım 4: Jupyter Notebook uygulamasını başlatın:
        jupyter notebook
Adım 5: 'proje_adi.ipynb' dosyasını açın.
Adım 6: Menüden 'Kernel' -> 'Restart & Run All' seçeneğine tıklayarak analizi başlatın.

4. PROJE GİRİŞİ
----------------------------------------------------------------
Bu çalışmanın amacı, e-ticaret platformu verilerini kullanarak müşteri davranışlarını anlamlandırmak ve RFM 
(Recency, Frequency, Monetary) analizi ile müşterileri segmentlere ayırmaktır.

Araştırma Soruları:
- Hangi ülkeler toplam ciroda en büyük paya sahip?
- Satın alma davranışlarında aylık ve günlük trendler nelerdir?
- Müşterileri harcama alışkanlıklarına göre nasıl segmente ederiz?

5. VERİ HAZIRLAMA VE TEMİZLEME ÖZETİ
----------------------------------------------------------------
- Veri seti 'unicode_escape' ile yüklendi.
- Eksik 'CustomerID' değerleri silindi, 'Description' eksiklikleri 'Bilinmiyor' olarak dolduruldu.
- 'InvoiceDate' datetime formatına çevrildi; Year, Month, Day, DayOfWeek, Hour sütunları oluşturuldu.
- İptal edilen işlemler ve hatalı fiyatlar temizlendi.
- 'Quantity' ve 'UnitPrice' sütunlarına IQR yöntemi ile baskılama (clipping) uygulandı.
- 'TotalPrice' = Quantity * UnitPrice sütunu oluşturuldu.

6. KEŞİFÇİ VERİ ANALİZİ (EDA) SONUÇLARI
----------------------------------------------------------------
- Birleşik Krallık veri setinde baskın konumdadır.
- Yıl sonuna doğru (Kasım/Aralık) ciroda sezonsal artış gözlemlenmiştir.
- Siparişler hafta içi günlerde yoğunlaşmaktadır.
- Ülkeler arası ciro farkı sepet büyüklüğünden ziyade işlem sıklığına dayanmaktadır.

7. RFM ANALİZİ VE KÜMELEME (Segmentasyon)
----------------------------------------------------------------
- RFM metrikleri hesaplandı (Recency, Frequency, Monetary).
- Veri logaritmik dönüşüm (np.log1p) ve StandardScaler ile ölçeklendirildi.
- K-Means algoritması ile k=4 küme oluşturuldu.

Segment Yorumları:
- Sadık/Şampiyon Müşteriler: Yüksek sıklık, yüksek harcama.
- Uykudaki Müşteriler: Uzun süredir işlem yapmamış.
- Potansiyel Müşteriler: Yeni kazanılmış, henüz düşük sıklıkta alışveriş yapmış.

8. KULLANILAN KÜTÜPHANELER
----------------------------------------------------------------
- pandas, numpy, matplotlib, seaborn, scikit-learn, datetime

================================================================
Bu çalışma, veri ön işleme, Keşifsel Veri Analizi (EDA) ve 
makine öğrenmesi süreçlerini içeren uçtan uca bir veri bilimi projesidir.
================================================================