# 🎯 AI Destekli Müşteri Analitiği Projesi
## Customer Segmentation + Churn Prediction + Behavioral Analysis

Müşteri kaybını (churn) azaltmak, yüksek değerli müşterileri belirlemek ve davranış kalıplarını anlamak için makine öğrenmesi ve veri analizi tekniklerini kullanan kapsamlı bir projedir.

---

## 📊 Proje Özeti

Bu notebook, müşteri verilerinde aşağıdaki soruları yanıtlamak amacıyla uçtan uca bir analiz pipeline'ı sunar:

✅ **Müşteriler hangi davranışsal gruplara ayrılır?**  
✅ **Hangi müşteriler ayrılma riski taşır?**  
✅ **Hangi davranış örüntüleri churn ve sadakatle ilişkilidir?**

---

## 🔄 Pipeline Akışı

```
1. Veri Yükleme & Ön İşleme
   ↓
2. Öznitelik Mühendisliği (RFM Scoring)
   ↓
3. Müşteri Segmentasyonu (K-Means, k=4)
   ↓
4. Churn Tahmini (Logistic Regression + Random Forest)
   ↓
5. Davranışsal Kural Çıkarımı
   ↓
6. Müşteri Değeri Analizi
   ↓
7. Özet Dashboard
   ↓
8. Model Açıklanabilirliği (Feature Importance + SHAP)
   ↓
9. Bonus: Birliktelik Analizi (Apriori)
```

---

## 🛠️ Kullanılan Teknolojiler

| Kategori | Teknoloji |
|----------|-----------|
| **Veri İşleme** | Pandas, NumPy |
| **Görselleştirme** | Matplotlib, Seaborn |
| **Kümeleme** | Scikit-learn (K-Means) |
| **Sınıflandırma** | Logistic Regression, Random Forest |
| **Model Açıklanabilirliği** | SHAP (TreeExplainer) |
| **İlişki Kuralları** | MLxtend (Apriori) |
| **Python Versiyonu** | 3.9+ |

---

## 📁 Dosya Yapısı

```
├── CRM_Project_Aciklamali.ipynb      # ⭐ Ana notebook (Türkçe açıklamalar)
├── CRM_Project.ipynb                 # Orijinal notebook (kod-yoğun)
├── CRM_EDA.ipynb                     # Exploratory Data Analysis
├── customer.ipynb                    # Ek müşteri analizi
├── customers.csv                     # 5000+ müşteri verisi
├── requirements.txt                  # Python bağımlılıkları
├── README.md                         # Bu dosya
└── images/
    ├── cofusion matris.png           # Random Forest Confusion Matrix
    ├── kolerasyon matrisi.png        # Feature Correlation Heatmap
    ├── crm müşteri analitği.png      # 4-Panel Dashboard
    └── müşteri değer analizi.png     # Segment Value Analysis
```

---

## 📈 Temel Bulgular

### 1️⃣ Korelasyon Analizi
![Korelasyon Matrisi](kolerasyon%20matrisi.png)
*Öznitelikler arasındaki ilişkileri gösteren Pearson korelasyon heatmap'ı*

---

### 2️⃣ Churn Model Performansı
![Confusion Matrix](cofusion%20matris.png)
*Random Forest modelinin test setindeki tahmin başarısı - Recall odaklı değerlendirme*

---

### 3️⃣ Özet Dashboard - 4 Panel
![CRM Müşteri Analitiği](crm%20müşteri%20analitği.png)
*Segment dağılımı | Segment bazında Churn | Yaşam Boyu Değer | Cart Abandonment vs Churn*

---

### 4️⃣ Müşteri Değeri Analizi
![Müşteri Değer Analizi](müşteri%20değer%20analizi.png)
*Segment bazında toplam ve ortalama yaşam boyu değeri*

---

## 🎯 Segmentler (K-Means, k=4)

| Segment | Müşteri % | Özellikleri | Churn Oranı |
|---------|-----------|-------------|------------|
| **High Value** | ~20% | Yüksek LTV, Sık satın alma | ✅ Düşük |
| **Discount Lovers** | ~25% | Indirim avcısı, Orta satın alma | ⚠️ Orta |
| **Standart** | ~30% | Dengeli davranış | ⚠️ Orta |
| **Passive / At Risk** | ~25% | Düşük aktivite, Az login | 🔴 Yüksek |

---

## 🔍 Model Metrikleri

### Logistic Regression (Baseline)
- **Accuracy:** 0.710
- **Precision:** 0.590
- **Recall:** 0.685
- **F1:** 0.634
- **ROC-AUC:** 0.754

### Random Forest (Ana Model) ⭐
- **Accuracy:** 0.745
- **Precision:** 0.650
- **Recall:** 0.721
- **F1:** 0.684
- **ROC-AUC:** 0.802

> Random Forest, churn'ü yakalama oranında (**Recall**) baseline'ı geride bırakıyor.

---

## 💡 İş Önerileri

### At Risk Segmenti için:
- ✉️ Hedefli yeniden kazanım (win-back) kampanyaları
- 🎁 Kişiselleştirilmiş indirim ve teklifler
- 📞 Proaktif müşteri desteği

### High Value Segmenti için:
- 🏆 Sadakat programı (VIP tier) ile değer koruma
- 🎖️ Özel avantajlar ve erken erişim
- 📊 Düzenli segmentasyon ve takip

### Sepet Terki Yüksek Kullanıcılar için:
- 🔔 Hatırlatma bildirimleri (SMS/E-mail)
- 💰 Dinamik teşvik (sepet değerine göre)
- 🔄 Tamamlama adımlarını basitleştirme

---

## 🚀 Nasıl Kullanılır

### 1. Ortamı Hazırla
```bash
# Virtual environment oluştur (varsa geç)
python -m venv .venv
source .venv/bin/activate  # macOS/Linux
# ya da
.venv\Scripts\activate  # Windows

# Bağımlılıkları kur
pip install -r requirements.txt
```

### 2. Notebook'u Aç
```bash
jupyter notebook CRM_Project_Aciklamali.ipynb
```

### 3. Hücreleri Sırayla Çalıştır
- Kurulum → Veri Yükleme → ... → Sonuç
- Her hücrenin üstünde **açıklamalar** vardır

### 4. Kendi Verini Kullan
- `customers.csv` yerine kendi CSV'ni koy
- Sütun isimlerini adapt et (bkz. Cell 2)

---

## 📋 requirements.txt

```txt
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=0.24.0
shap>=0.40.0
mlxtend>=0.19.0
jupyter>=1.0.0
```

---

## 🔬 Metodolojik Notlar

### Standartlaştırma (StandardScaler)
- K-Means, Logistic Regression için **gerekli**
- Random Forest için **isteğe bağlı**

### Sınıf Dengeleme
- `class_weight="balanced"` kullanılmıştır
- Churn (azınlık sınıf ~29%) daha fazla ağırlık alır

### Sızıntı Riski ⚠️
- `Days_Since_Last_Purchase` churn etiketini sızdırabilir
- Etiket tanımı öncesinde doğrulanmalı

### Stratified Train/Test
- Hem eğitim hem test setinde aynı churn oranı korunur
- Adil ve güvenilir değerlendirme sağlar

---

## 📊 Veri Özeti

```
Müşteri Sayısı:     5,000+
Öznitelik Sayısı:   40+ (ön işlemeden sonra 30+)
Target (Churn):     %29 (dengesiz veri)
Eksik Değer:        <2% (imputation ile çözüldü)
Aykırı Değer:       Düzeltildi (yaş, satın alma vb.)
```

---

## 🎓 Yetkinlikler Gösterildi

✅ **Veri Analizi:** EDA, korelasyon, dağılım analizi  
✅ **Makine Öğrenmesi:** Gözetimli (sınıflandırma) + Gözetimsiz (kümeleme)  
✅ **İş Zekâsı:** Dashboard oluşturma, segment profili, değer analizi  
✅ **Model Açıklanabilirliği:** Feature importance, SHAP değerleri  
✅ **Python:** Pandas, Scikit-learn, Matplotlib/Seaborn, SHAP, MLxtend  

