# Wine Quality EDA 📊

Bu repo, **Wine Quality** veri seti üzerinde keşifsel veri analizi (EDA) yapar. Çalışma; veri yapısını inceleme, eksik/tekrar kayıt kontrolü, dağılım görselleştirmeleri, korelasyon ısı haritası ve kalite sınıflarına göre özet istatistikler üretmeye odaklanır. **Makine öğrenmesi modeli içermez**; amaç, ileride kurulacak modeller için sağlam bir veri anlayışı oluşturmaktır.

---

## İçindekiler

* [Genel Amaç](#genel-amaç)
* [Kullanılan Teknolojiler](#kullanılan-teknolojiler)
* [Kurulum](#kurulum)
* [Veri Seti](#veri-seti)
* [Analiz Adımları](#analiz-adımları)
* [Görsel Çıktı Örnekleri](#görsel-çıktı-örnekleri)
* [Öne Çıkan Bulgular](#öne-çıkan-bulgular)
* [Gelecek Planları](#gelecek-planları)

---

## Genel Amaç

Kimyasal/fiziksel özellikler ile **quality** (kalite) etiketinin ilişkisini keşfetmek, değişken dağılımlarını görmek ve değişkenler arası ilişkileri özetlemek. Bu çalışma, daha sonra uygulanacak sınıflandırma/regresyon modelleri için veri öncesi içgörü sağlar.

---

## Kullanılan Teknolojiler

* Python 3.10+
* NumPy, Pandas
* Matplotlib, Seaborn
* Jupyter Notebook

---

## Kurulum

Gerekli kütüphaneleri kurun ve notebook'u açın:

```bash
pip install numpy pandas matplotlib seaborn jupyter
jupyter notebook WineQualtyDataset.ipynb
```

> Not: Notebook, kök dizinde bulunan **13-WineQT.csv** dosyasını okur. Dosyanın yolunu değiştirirseniz ilk hücrelerdeki `read_csv` yolunu güncelleyin.

---

## Veri Seti

* **Kaynak**: Wine Quality (kırmızı şarap) veri seti
* **Dosya**: `13-WineQT.csv`
* **Hedef Değişken**: `quality`
* **Örnek Özellikler**: `pH`, `alcohol`, `volatile acidity`, `sulphates`, vb.

---

## Analiz Adımları

Notebook içeriği aşağıdaki adımları uygular:

1. **Yükleme & İlk Bakış**: `info()`, `describe().T`, örnek satırlar.
2. **Eksik/Tekrar Kayıt Analizi**: `isnull().sum()`, `duplicated().sum()`.
3. **Uç Değer/Geçersiz Kontrol**: Negatif değer taraması (örn. `pH < 0`).
4. **Korelasyon Isı Haritası**: Özellikler arası ilişki matrisinin görselleştirilmesi.
5. **Dağılım İncelemeleri**: Histogramlar, `pairplot`, KDE grafikleri (tüm sütunlar için çoklu ızgara).
6. **Kaliteye Göre Özetler**: `groupby('quality').mean()` ile sınıf bazlı ortalamalar.
7. **Kutugrafikleri & Serpilim**: `boxplot` (ör. `alcohol` vs `quality`), `scatterplot` (örn. `pH` vs `alcohol`, `hue=quality`).

---

## Görsel Çıktı Örnekleri

* **Korelasyon ısı haritası**: Değişkenler arası güçlü/zayıf ilişkileri gösterir.
* **Histogramlar**: Her bir özelliğin dağılımını gözlemler.
* **Pairplot**: İkili değişken ilişkilerine genel bakış.
* **KDE ızgarası**: Tüm sütunlar için kalite sınıflarına göre yoğunluk eğrileri.

> Notebook içinde ilgili hücreler çalıştırıldığında bu grafikler ekranda görünür.

---

## Öne Çıkan Bulgular

* `alcohol` dağılımı kalite ile anlamlı farklılıklar gösterebilir (kutu grafikleri).
* Bazı değişkenler arasında orta düzey korelasyonlar bulunur (ısı haritası ile gözlenir).
* Sınıf dengesizliği: `quality` dağılımında bazı sınıflar daha yoğundur (bar grafiği).

> Bu bulgular EDA'ya dayalı gözlemlerdir; istatistiksel testler veya modelleme ile doğrulanması önerilir.

---

## Gelecek Planları

* Özellik mühendisliği (örn. asitlik oranlarından türetilmiş metrikler).
* Sınıflandırma ya da regresyon modeli kurulumu (Logistic Regression, Random Forest, XGBoost).
* Hiperparametre araması ve **mAP/F1/Accuracy** gibi metriklerle değerlendirme.
* Basit bir Streamlit arayüzü ile interaktif keşif ve tahmin modülü.

---
