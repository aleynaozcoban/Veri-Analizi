## Author

Aleyna Özçoban 
Kaggle: [aleynaozcoban](https://www.kaggle.com/aleynazoban)  


# Talep Analizi ve Tahminleme

Bu proje, Product Demand Forecasting veri seti üzerinde talep analizleri yapmayı ve talep trendlerini 
anlamayı amaçlamaktadır. Çalışma, veri temizleme, keşifsel veri analizi (EDA) ve özellik mühendisliği adımları ile desteklenmiştir.
Proje, talep tahminlerini iyileştirerek iş kararlarını optimize etmeye yönelik öneriler sunmaktadır.

**Proje Amaçları**

Talep verilerini analiz ederek desenleri, trendleri ve aykırı değerleri anlamak.
Veriyi temizleyerek eksik değerleri ve aykırı değerleri yönetmek.
Veriye dayalı yeni özellikler türeterek analiz kalitesini artırmak.
Veri setini gelecekteki tahminleme modellerine uygun hale getirmek.
İş kararları için stok yönetimi ve talep planlaması konusunda öneriler sunmak.

**Veri Seti Genel Bakış**

Bu veri seti, ürün sipariş bilgilerini ve talep miktarlarını içermektedir.

**Dosya Adı:** HistoricalProductDemand.csv

**Sütunlar:** 
* Order_Demand (Sayısal, ürünlerin talep miktarını ifade eder.)
* Product_Code (Ürünün kodunu ifade eder.)
* Product_Category (Ürünün bulunduğu kategoriyi ifade eder.)
* Date (Satış tarihini ifaded eder.)
* Depo (Ürünün bulunduğu depoyu ifade eder.)

**Veri Sorunları:**
Kolonlarda eksik ve aykırı değerler bulunmaktadır.

Mevsimsel dalgalanmalar ve trendler fark edilmiştir.

**Yapılan Adımlar**
1. Veri Temizleme

Order_Demand kolonundaki eksik değerler medyan değeri ile doldurulmuştur.
Aykırı değerler, Çeyrekler Arası Aralık (IQR) yöntemi kullanılarak belirlenmiş ve yönetilmiştir.
Aykırı değer sınırları:
Alt Sınır: 
𝑄
1
−
1.5
×
𝐼
𝑄
𝑅
Q1−1.5×IQR
Üst Sınır: 
𝑄
3
+
1.5
×
𝐼
𝑄
𝑅
Q3+1.5×IQR

2. Keşifsel Veri Analizi (EDA)
Ana analizler:

Tanımlayıcı İstatistikler:
Ortalama, medyan ve standart sapma gibi özet istatistikler hesaplandı.
Görselleştirmeler:
Order_Demand dağılımını görmek için histogramlar.
Aykırı değerleri belirlemek için kutu grafikleri (boxplot).
Talepteki zaman trendlerini incelemek için çizgi grafikleri.

3. Future Engineering
Veri setine daha fazla anlam katmak için yeni değişkenler oluşturulmuştur:

**Talep Kategorileri:**
Order_Demand, Düşük, Orta, Yüksek talep kategorilerine ayrıldı.

**Mevsimsel Trendler:***
Eğer zaman bilgisi varsa, ay, mevsim veya haftanın günü gibi bilgiler türetildi.

**Hareketli Ortalamalar:**
Talep trendlerini pürüzsüz hale getirmek için hareketli ortalamalar hesaplandı (zaman verisi varsa).

4. Çıkarımlar ve Öneriler

Aykırı Değerler:
Bazı aykırı değerler, beklenmedik talep patlamalarını veya stok hatalarını gösterebilir. Bu nedenle, aykırı değerler dikkatle incelenmelidir.

Sezonsal Dalgalanmalar:
Veride belirli dönemlerde (örneğin, tatiller veya yıl sonu) talep artışları gözlemlenmiştir.

Talep Tahmini:
Tahmin modelleri ile gelecekteki talep eğilimleri daha iyi öngörülebilir.
**Gelecek Adımlar**
Modelleme: Veriyi, zaman serisi modelleri (ARIMA, Prophet) veya regresyon tabanlı yöntemler (XGBoost) için hazır hale getirin.

Özellik Geliştirme: Talep tahminlerini iyileştirmek için ek değişkenler türetin.

Uygulama: Analiz ve tahminleri gerçek iş ortamında test edin.

**Kullanılan Teknolojiler**

Python: Veri analizi ve görselleştirme için kullanılan ana dil.
**Kütüphaneler:**

pandas: Veri manipülasyonu.

numpy: Sayısal işlemler.

matplotlib ve seaborn: Görselleştirme.

scikit-learn: Veri ön işleme ve modelleme.

statsmodels: Zaman serisi analizi.

# Sonuç ve Öneriler


**Taleplerin Tahmin Edilmesi:** 
 Order_Demand ve DATE  verisini kullanarak, gelecekteki taleplerin tahmin edilmesi sağlanmaktadır. Bu tahminler, işletmenin stok yönetimini optimize etmesine ve ürün tedarik süreçlerini daha verimli hale getirmesine yardımcı olur. Sezonsallık, trend, lag özellikleri gibi zaman serisi analizlerini kullanarak, gelecekteki talep artışları veya azalmaları öngörülebilir. Öneri: Modellemeyi, ARIMA, SARIMA gibi yöntemler ile gerçekleştirebilir.

**Stok ve Envanter Yönetimi:**
Order_Demand ve Warehouse verisini analiz ederek, hangi ürünlerin daha fazla talep gördüğünü ve hangilerinin daha az talep aldığını belirleyebilirsiniz. Bu bilgiyi kullanarak, envanter yönetimi ve sipariş miktarlarını optimize edebilir, stok fazlası veya eksikliği risklerini azaltılabilir. Taleplerin sezonluk değişimleri göz önünde bulundurularak, stok seviyeleri ayarlanabilir.

**Ürün Segmentasyonu ve Satış Stratejileri:**
ürünlerin pazarlanması ve fiyatlandırılması stratejik olarak belirlenebilir.
Order_Demand verisini kullanarak, ürünleri düşük, orta ve yüksek talep gruplarına ayırarak bu segmentlere göre, her ürün için özelleştirilmiş pazarlama stratejileri geliştirilebilir. Yüksek talep gören ürünler için promosyonlar düzenlenebilir ve düşük talep gören ürünleri indirimle tanıtılabilir.
