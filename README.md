# Türkiye Deprem Analizi Projesi

Bu proje, Türkiye'deki depremleri **veri bilimi**, **görselleştirme** ve **makine öğrenmesi** teknikleriyle analiz etmektedir.  
Amaç, deprem verilerini anlamak, görselleştirmek ve makine öğrenmesi ile deprem türü tahmini yapmaktır.

---

## 📊 Proje İçeriği

- **Veri Toplama ve Ön İşleme**  
  Kaggle üzerinde yer alan Türkiye deprem verileri kullanıldı.  
  Eksik değerler temizlendi ve veri tipleri uygun formatlara dönüştürüldü.

- **Görselleştirmeler**  
  - Çubuk grafikler ve dağılım grafikleri
  - Etkileşimli haritalar (Folium)
  - Isı haritaları (Seismic yoğunluk analizi)

- **İstatistiksel Analizler**  
  Deprem büyüklük tipleri (ML, MW, Md, MI, Mwp) açıklanarak veriye anlam kazandırıldı.

- **Makine Öğrenmesi ile Deprem Türü Tahmini**
  - **LazyPredict** ile 5 farklı model test edildi.
  - En iyi 3 model seçildi ve **Cross-Validation** ile doğrulandı.
  - **RandomizedSearchCV** kullanılarak hiperparametre optimizasyonu yapıldı.
  - En iyi performans **Random Forest Classifier** modelinde elde edildi.
  - Sonuç doğruluk oranı: **%86**

---

## 🌍 Görseller

### Deprem Noktaları Haritası
Türkiye genelinde 1999-2024 yılları arasında kaydedilen depremlerin merkez üsleri (epicenter) turuncu noktalarla gösterilmektedir.

![Deprem Noktaları](https://github.com/user-attachments/assets/9cf23a92-6cec-4253-8f95-77ea67eeb454)

---

### Deprem Isı Haritası
Aynı verinin yoğunluk analizi; kırmızı alanlar yüksek deprem aktivitesini, mavi/yeşil alanlar düşük aktiviteyi gösterir.

![Deprem Isı Haritası](https://github.com/user-attachments/assets/0a39bfcf-00c8-4295-ae87-f28fbb0da650)

---

## 🛠 Kullanılan Teknolojiler ve Kütüphaneler

- **Python** – Veri işleme ve analiz
- **Pandas, NumPy** – Veri manipülasyonu
- **Matplotlib, Seaborn** – Statik görselleştirme
- **Plotly, Folium** – Etkileşimli görselleştirme
- **Scikit-learn** – Makine öğrenmesi algoritmaları
- **LazyPredict** – Hızlı model karşılaştırma
- **RandomizedSearchCV** – Hiperparametre optimizasyonu

---

## 📈 Makine Öğrenmesi Süreci

1. **LazyPredict ile Model Karşılaştırma**  
   - 5 farklı model denendi.
   - En yüksek doğruluk veren ilk 3 model seçildi.

2. **Cross-Validation**  
   - Seçilen 3 model 5 katlı çapraz doğrulama ile test edildi.

3. **Hiperparametre Optimizasyonu**  
   - `RandomizedSearchCV` ile en iyi parametreler belirlendi.
   - En iyi sonuç **Random Forest Classifier** ile elde edildi.

4. **Sonuçlar**  
   - Genel doğruluk: **%86**
   - Yaygın deprem tiplerinde yüksek başarı, nadir tiplerde düşük doğruluk

---

