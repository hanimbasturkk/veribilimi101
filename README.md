# 🚗 Second-Hand Car Price Prediction with Machine Learning

Bu proje, ikinci el araba ilanları verisini kullanarak **fiyat tahmini** yapmak amacıyla geliştirilmiş bir **Makine Öğrenmesi (ML)** projesidir. Python, pandas, scikit-learn ve matplotlib gibi popüler kütüphaneler kullanılarak veri ön işleme, özellik mühendisliği ve regresyon modellemesi adım adım gerçekleştirilmiştir.

---

## 📁 Proje İçeriği

- [x] Veri Yükleme ve Keşifsel Veri Analizi (EDA)
- [x] Eksik Değer Analizi
- [x] Aykırı Değer Analizi
- [x] Özellik Mühendisliği (Feature Engineering)
- [x] Kategorik Değişken Kodlama (Label Encoding)
- [x] Veriyi Eğitim/Test olarak Ayırma
- [x] Regresyon Modeli Eğitimi (Random Forest)
- [x] Model Değerlendirme (RMSE, R²)
- [x] Öngörülerin Görselleştirilmesi

---

## 📊 Kullanılan Veri Seti

- **Kaynak:** [Craigslist Araba İlanları](https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data)
- **Gözlem Sayısı:** ~400.000+
- **Özellikler:** `price`, `year`, `manufacturer`, `model`, `fuel`, `condition`, `odometer`, `transmission`, `drive`, `type`, `paint_color`, `state`, `lat`, `long`, `description` ve daha fazlası.

---

## 🧹 Veri Ön İşleme

- **Fiyat:** 0 veya çok yüksek olan değerler çıkarıldı.
- **Tarih:** `posting_date` sütunundan `posting_year` ve `posting_month` türetildi.
- **Kategorik Değişkenler:** LabelEncoder kullanılarak sayısal formata dönüştürüldü.
- **Eksik Değerler:** Gerekirse düşürüldü veya dolduruldu.

---

## 🧠 Özellik Mühendisliği

- `car_age`: Arabanın yaşı (`2024 - year`)
- `price_log`: Fiyatın logaritmik dönüşümü (modelin stabilitesi için)
- `description_length`: İlan açıklamasının karakter uzunluğu

---

## 🧪 Modelleme

- **Model:** `RandomForestRegressor` (scikit-learn)
- **Veri Ayrımı:** %80 eğitim / %20 test
- **Hedef Değişken:** `price_log`
- **Değerlendirme Metriği:**
  - RMSE (Root Mean Squared Error)
