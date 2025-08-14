# Türkiye Deprem Analizi Projesi

Bu proje, Türkiye'deki depremleri **veri bilimi**, **görselleştirme** ve **makine öğrenmesi** teknikleriyle analiz etmektedir.  
Amaç, deprem verilerini anlamak, görselleştirmek ve makine öğrenmesi ile deprem türü tahmini yapmaktır.
---

## 📂 Veri Seti

Bu projede kullanılan veri seti **Kaggle** üzerinden alınmıştır:  
🔗 [Türkiye Deprem Verileri - Kaggle](https://www.kaggle.com/datasets/yarenzoul/turkiye-deprem-verileri)

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
  - Sonuç doğruluk oranı: **%86.35**

---


## 📂 Veri Seti

Bu projede kullanılan veri seti **Kaggle** üzerinden alınmıştır:  
🔗 [Türkiye Deprem Verileri - Kaggle](https://www.kaggle.com/datasets/yarenzoul/turkiye-deprem-verileri)

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

## 📈 Makine Öğrenmesi Süreci

### 1️⃣ LazyPredict ile Model Karşılaştırma

| Model | Accuracy |
|-------|----------|
| **XGBClassifier** | 0.87 |
| **RandomForestClassifier** | 0.87 |
| GradientBoostingClassifier | 0.84 |
| DecisionTreeClassifier | 0.82 |
| LogisticRegression | 0.78 |

📌 En yüksek doğruluğu veren **ilk 3 model** seçildi:
- XGBClassifier
- RandomForestClassifier
- GradientBoostingClassifier

---

### 2️⃣ Cross Validation & Hyperparameter Tuning

- **RandomizedSearchCV** kullanılarak en iyi parametreler bulundu.
- 5 katlı çapraz doğrulama ile test edildi.

| Model | En İyi Parametreler | CV Skor (Mean) |
|-------|--------------------|---------------|
| **RandomForestClassifier** | `{'n_estimators': 200, 'max_features': 'sqrt', 'max_depth': None}` | **0.8635** |
| **XGBClassifier** | `{'subsample': 1.0, 'n_estimators': 200, 'max_depth': 5, 'learning_rate': 0.1, 'colsample_bytree': 0.8}` | **0.8565** |
| **GradientBoostingClassifier** | `{'learning_rate': 0.1, 'n_estimators': 100, 'max_depth': 3}` | **0.8377** |

---

## 📊 Sonuçlar

- **Doğruluk (Accuracy)**: %86.35 (Random Forest ile)
- **Confusion Matrix** görselleştirildi
- LazyPredict ile hızlı model karşılaştırması yapıldı, ardından Cross Validation ve RandomizedSearchCV ile en iyi parametreler belirlendi
- Yaygın deprem türlerinde yüksek başarı, nadir türlerde daha düşük doğruluk gözlendi

---


## 💻 Nasıl Çalıştırılır

Aşağıdaki adımları terminalde çalıştırın:

```bash
git clone https://github.com/berkekarakanli/Turkey-Earthquake-Analysis.git
pip install -r requirements.txt
jupyter notebook Turkey-Earthquake-Analysis.ipynb
