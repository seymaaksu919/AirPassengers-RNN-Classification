# 🛫 AirPassengers RNN Classification

Bu proje, **AirPassengers** veri setini kullanarak **Yolcu Talep Kategorisi** (düşük, orta, yüksek) tahmini yapan bir **RNN (Recurrent Neural Network)** modelini içermektedir. 

Model, geçmiş **12 aylık yolcu sayısı verisini** kullanarak bir sonraki ayın talep kategorisini tahmin eder.

---

## 🎯 Proje Amacı
- Zaman serisi verisini kullanarak **çok sınıflı sınıflandırma** yapmak.
- RNN mimarisini temel düzeyde uygulamak.
- Yolcu sayısı verilerini kategorilere ayırarak gelecekteki talep seviyesini tahmin etmek.

---

## 🛠 Kullanılan Teknolojiler
- Python 3.x
- pandas
- numpy
- scikit-learn
- TensorFlow / Keras

---

## 📊 Veri Seti
- **AirPassengers.csv**
- 1949-1960 yılları arasındaki aylık yolcu sayıları.
- Sütunlar:
  - `Month` → Ay bilgisi
  - `#Passengers` → Yolcu sayısı

---

## 🔍 Çalışma Mantığı
1. **Veri Yükleme**  
   CSV dosyası okunur, yalnızca yolcu sayıları alınır.

2. **Normalizasyon**  
   `MinMaxScaler(feature_range=(0,1))` ile veriler 0-1 aralığına ölçeklenir.

3. **Kategorilere Ayırma**  
   Yolcu sayısı üç kategoriye ayrılır:
   - Düşük talep
   - Orta talep
   - Yüksek talep

4. **Girdi ve Çıktı Setlerinin Oluşturulması**  
   - **12 aylık geçmiş veri** giriş olarak alınır.
   - 13. ayın kategorisi çıktı olur.

5. **One-Hot Encoding**  
   Etiketler `[1,0,0]`, `[0,1,0]`, `[0,0,1]` formatına dönüştürülür.

6. **RNN Modeli**  
   - `SimpleRNN` katmanı
   - Dense çıkış katmanı (softmax aktivasyonlu, 3 sınıf)

---

