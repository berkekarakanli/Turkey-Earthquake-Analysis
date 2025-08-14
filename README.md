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
Türkiye genelinde 1999-2025 yılları arasında kaydedilen depremlerin merkez üsleri (epicenter) turuncu noktalarla gösterilmektedir.

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

### 1️⃣ LazyPredict ile Model Karşılaştırma

| Model | Accuracy |
|-------|----------|
| **XGBClassifier** | 0.87 |
| **RandomForestClassifier** | 0.87 |
| GradientBoostingClassifier | 0.84 |
| DecisionTreeClassifier | 0.82 |
| LogisticRegression | 0.78 |

📌 En yüksek doğruluğu veren **ilk 3 model**:  
- XGBClassifier  
- RandomForestClassifier  
- GradientBoostingClassifier  

---

### 2️⃣ Cross-Validation & RandomizedSearchCV Sonuçları

| Model | En İyi Parametreler | CV Skor (Mean) |
|-------|--------------------|---------------|
| **RandomForestClassifier** | `{'n_estimators': 200, 'max_features': 'sqrt', 'max_depth': None}` | **0.8635** |
| **XGBClassifier** | `{'subsample': 1.0, 'n_estimators': 200, 'max_depth': 5, 'learning_rate': 0.1, 'colsample_bytree': 0.8}` | **0.8565** |
| **GradientBoostingClassifier** | `{'learning_rate': 0.1, 'n_estimators': 100, 'max_depth': 3}` | **0.8377** |

---

### 3️⃣ Sonuçlar

- **Random Forest** modeli en yüksek doğruluk oranına ulaştı (**%86.35**)
- LazyPredict ile hızlı model karşılaştırması yapıldı, ardından Cross Validation ve RandomizedSearchCV ile en iyi parametreler belirlendi.
- Yaygın deprem türlerinde yüksek başarı, nadir türlerde daha düşük doğruluk elde edildi.

---

## 📌 Kaynaklar

- [Kaggle Notebook ve Veri Seti](https://www.kaggle.com/code/yarenzoul/t-rkiye-deprem-analizi)

---

## 📜 Lisans
Bu proje **MIT Lisansı** ile lisanslanmıştır.
