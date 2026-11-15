# CNN-Sign-Classification: Deep Learning-Based Sign Direction Classifier

Üsküdar Üniversitesi Mühendislik ve Doğa Bilimleri Fakültesi kapsamında Altan Eroğlu ve Yousif Maergani tarafından geliştirilen, Convolutional Neural Networks (CNN) ve TensorFlow/Keras kullanarak görsel verileri işleyen ve ikili sınıflandırma (Sol/Sağ Tabela) yapan bir derin öğrenme projesidir[cite: 45].

## 📌 Proje Mimarisi ve İşlem Adımları
Proje, ham görüntü verilerinin işlenmesinden model tahminine kadar uçtan uca bir yapay zeka pipeline'ı sunar:

1. **Veri Hazırlığı ve Pipeline (`image_dataset_from_directory`):** Görüntülerin 256x256 boyutuna standartlaştırılması, `batch_size=32` ile bellek optimizasyonu ve etiketlerin otomatik çıkarılması[cite: 45].
2. **CNN Mimarisi (`Sequential`):** 
   * **Conv2D & MaxPooling2D:** Mekansal özelliklerin (kenarlar, desenler) çıkarılması ve boyut indirgeme katmanları (64 ve 128 filtre yapılandırmaları)[cite: 45].
   * **Flatten & Dense:** 2D özellik matrislerinin tek boyutlu vektörlere dönüştürülmesi ve tam bağlantılı katmanlar üzerinden karar mekanizması[cite: 45].
   * **Sigmoid Çıkış Katmanı:** İkili sınıflandırma (Binary Classification) için 0 ile 1 arasında olasılık üreten çıkış nöronu[cite: 45].
3. **Model Derleme ve Eğitimi:** `adam` optimizer, `binary_crossentropy` kayıp fonksiyonu (loss function) ve 10 epoch süresince doğrulama verisiyle (validation data) overfitting önleyici eğitim döngüsü[cite: 45].
4. **Tahmin Mekanizması (`tabela_tahmin`):** Yeni bir görselin modele uygun hale getirilmesi (`img_to_array`, `expand_dims`) ve 0.5 eşik değeri ile sınıf tespiti[cite: 45].

## 📂 Depo İçeriği
* `Presentation.pptx`: Projenin kod bloklarını, katman özetlerini (`model.summary()`) ve mimari mantığını detaylıca açıklayan sunum dosyası[cite: 45].
