
#  Tesla Müşteri Şikayetleri Analizi

## Müşteri İlişkileri ve Kriz Yönetimi

### (Sınıflandırma ve Churn Riski Yaklaşımı)

---

##  Proje Özeti

Bu proje, **Tesla markasına ait müşteri şikayetlerini** veri analitiği ve **kural tabanlı metin sınıflandırması (rule-based NLP)** yöntemleriyle incelemeyi amaçlamaktadır.
Çalışma kapsamında müşteri şikayetleri;

* **Kök neden**
* **İlgili operasyonel departman**
* **Müşteri kaybı (churn) riski**

açılarından analiz edilmiştir.

Analiz, **Türkiye pazarı (Türkçe veriler)** ve **global pazar (İngilizce veriler)** için ayrı ayrı yapılmış, ardından karşılaştırmalı olarak değerlendirilmiştir.

 Analize ait **grafikler, tablolar ve detaylı yorumlar PDF rapor dosyası içerisinde yer almaktadır.**

---

##  Projenin Amaçları

* Şikayetlerin **ürün kaynaklı mı (üretim/fabrika)** yoksa **insan ve süreç kaynaklı mı (servis, bayi, iletişim)** olduğunu belirlemek
* Müşteri memnuniyetsizliğinin **hangi departmanlarda yoğunlaştığını** tespit etmek
* **Kritik churn riski** taşıyan şikayetleri analiz ederek müşteri kaybına yol açan alanları ortaya koymak
* **Türkiye pazarı ile global pazar** arasındaki müşteri deneyimi farklarını karşılaştırmak

---

##  Veri Kaynakları

### 🇹🇷 Türkiye Pazarı (Türkçe Veriler)

* Şikayetvar – Tesla Genel
  [https://www.sikayetvar.com/tesla](https://www.sikayetvar.com/tesla)
* Şikayetvar – Tesla Model Y
  [https://www.sikayetvar.com/tesla/tesla-model-y](https://www.sikayetvar.com/tesla/tesla-model-y)
* Ekşi Sözlük – Tesla Model Y
  [https://eksisozluk.com/tesla-model-y--5029928](https://eksisozluk.com/tesla-model-y--5029928)

###  Global Pazar (İngilizce Veriler)

* Trustpilot – Tesla Motors
  [https://www.trustpilot.com/review/www.teslamotors.com](https://www.trustpilot.com/review/www.teslamotors.com)
* YouTube – Tesla Araç Deneyimi ve Eleştiri Videoları

  * [https://www.youtube.com/watch?v=d1zH2bV_tpk](https://www.youtube.com/watch?v=d1zH2bV_tpk)
  * [https://www.youtube.com/watch?v=xkyzMYNEcts](https://www.youtube.com/watch?v=xkyzMYNEcts)
  * [https://www.youtube.com/watch?v=_QN4jxGGWbc](https://www.youtube.com/watch?v=_QN4jxGGWbc)

---

##  Yöntem

### 1️. Veri Toplama

* **YouTube Data API v3** ile global pazara ait yüksek hacimli yorumlar çekilmiştir.
* **Selenium Web Scraping** kullanılarak API erişimi olmayan platformlardan (Şikayetvar, Ekşi Sözlük) veri toplanmıştır.

 Toplanan Ham Veri:

* Türkiye: **5.068** kayıt
* Global: **21.592** kayıt
* Toplam: **26.660** kayıt

---

### 2️. Veri Ön İşleme

* Boş (NaN) kayıtların temizlenmesi
* Tüm metinlerin küçük harfe dönüştürülmesi
* Emoji, URL ve özel karakterlerin temizlenmesi
* Anlamsız ve çok kısa yorumların elenmesi

 Analize Dahil Edilen Temiz Veri:

* Türkiye: **5.009**
* Global: **18.752**

---

### 3️. Kök Neden Etiketlemesi

Kural tabanlı anahtar kelimeler kullanılarak şikayetler üç gruba ayrılmıştır:

* **Üretim Hatası (Fabrika)**
* **Personel Davranışı (Bayi / Servis)**
* **Belirsiz**

 Kök neden dağılım grafiklerine **PDF raporun “Türkiye Pazarı” ve “Global Pazar” bölümlerinden** ulaşılabilir.

---

### 4️. Departman Bazlı Etiketleme

Şikayetler aşağıdaki departmanlara atanmıştır:

* Teknik Servis
* Lojistik
* Çağrı Merkezi
* Belirsiz

 Departman bazlı dağılım ve karşılaştırmalı grafikler **PDF raporda görsel olarak sunulmuştur.**

---

### 5️. Churn (Müşteri Kaybı) Riski Analizi

Şikayetler üç risk seviyesinde değerlendirilmiştir:

* **Kritik:** İade, dava, markayı terk etme ifadeleri
* **Orta:** Ciddi memnuniyetsizlik
* **Düşük:** Bilgi talebi veya hafif şikayet

 **Departman bazlı kritik churn grafikleri** ve oran analizleri PDF raporda yer almaktadır.

---

##  Türkiye Pazarı – Öne Çıkan Bulgular

* Kritik churn riski en yüksek departmanlar: **Çağrı Merkezi ve Lojistik**
* Müşteri memnuniyetsizliği ağırlıklı olarak **iletişim ve süreç yönetimi** kaynaklı
* Türkiye pazarında müşteri için sorun yaşamaktan çok, **sorunun nasıl yönetildiği** belirleyici

# İlgili grafikler:

<p align="center">
  <img src="https://github.com/user-attachments/assets/a4008a75-e887-4c54-9074-8413eb39557f" width="400" />
  <img src="https://github.com/user-attachments/assets/c92656d3-97f0-4c84-a5a4-16f1515b6ff1" width="400" />
</p>



---

##  Global Pazar – Öne Çıkan Bulgular

* Şikayetlerin büyük bölümü **üretim hataları ve lojistik süreçler** etrafında yoğunlaşmaktadır
* Kritik churn riski en çok **lojistik kaynaklı şikayetlerde** görülmektedir
* Ürün kalitesi ve teslimat süreçleri, global müşteri deneyiminde belirleyici rol oynamaktadır

 İlgili grafikler:
**“Global Kök Neden Dağılımı”** ve **“Global Departman – Churn Analizi”** (PDF)

---

##  Türkiye – Global Karşılaştırması

| Başlık             | Türkiye Pazarı   | Global Pazar       |
| ------------------ | ---------------- | ------------------ |
| Temel Sorun        | İletişim & Süreç | Ürün & Lojistik    |
| Kritik Churn       | Yüksek           | Daha Düşük         |
| En Riskli Alan     | Çağrı Merkezi    | Lojistik           |
| Müşteri Beklentisi | Hızlı geri dönüş | Ürün güvenilirliği |

---

##  Kullanılan Teknolojiler

* Python (Pandas, NumPy)
* Selenium WebDriver
* YouTube Data API v3
* Jupyter Notebook
* Kural Tabanlı NLP Yaklaşımı

---

##  Rapor

Bu repository’de yer alan **PDF dosyası**,

* Tüm grafikler
* Tablo analizleri
* Türkiye & Global karşılaştırmalar
* Akademik yorumlar

içermektedir.

---

##  Hazırlayan

**Reyyan Akbulut**
Yönetim Bilişim Sistemleri (YBS)
Veri Analitiği • Müşteri Analitiği • Kriz Yönetimi

---


