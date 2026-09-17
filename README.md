# Strabismus (Göz Kayması) Ensemble Sınıflandırma Modeli

Bu proje, göz fotoğraflarından şaşılık (strabismus) durumunu tespit etmek için geliştirilmiş bir makine öğrenmesi boru hattıdır (pipeline). Projenin derin öğrenme mimarisi, veri ön işleme (preprocessing) adımları ve model optimizasyonu benim tarafımdan geliştirilmiş olup, modelin entegre edildiği mobil uygulama ekip arkadaşım tarafından hazırlanmıştır.

## 🚀 Eğitilmiş Model Dosyası
GitHub'ın tekil dosya boyutu sınırı (25 MB) aşıldığı için, projede Flutter mobil uygulamasına entegre edilmek üzere Flex Ops ile dışa aktarılmış nihai model dosyası Google Drive üzerinden açık kaynaklı olarak paylaşılmıştır:

👉 **[Eğitilmiş Modeli İndirmek İçin Tıklayın](https://drive.google.com/file/d/1TNidKtRI3xOBDJNRvdQPNnj-JcMylPtf/view?usp=sharing)**

## 🧠 Model Mimarisi ve Optimizasyon
Sınıflandırma başarısını maksimize etmek için Soft Voting stratejisiyle bir **Ensemble Model** kurgulanmıştır:
* **Temel Modeller:** MobileNetV2 (%60 ağırlık) ve EfficientNetB0 (%40 ağırlık).
* **Sınıflar:** `DIKEY_KAYMA`, `NORMAL`, `YATAY_KAYMA` (3 Sınıf).
* **Test Başarısı (Accuracy):** %92.73.
* **Veri Artırımı (Augmentation):** Görüntüler üzerinde sadece yatay çevirme, kontrast ve parlaklık rastgeleliği kullanılarak modelin fiziksel kayma yönlerini karıştırmadan genelleme yapması sağlanmıştır.

## 📂 Veri Seti ve Colab Kurulumu
Eğitim veri seti Kaggle üzerinden derlenmiştir. Bu projedeki `.ipynb` eğitim kodunu kendi Colab ortamınızda çalıştırmak için:
1. İlgili şaşılık (strabismus) veri setini Kaggle'dan indirin.
2. Google Drive ana dizininizde (MyDrive) `STRABISMUS_3_CLASSES` adında bir klasör oluşturup görüntüleri buraya aktarın.
3. Repodaki `.ipynb` dosyasını Colab üzerinde açıp çalıştırdığınızda, kod veri setini otomatik olarak bu yoldan çekecektir.
