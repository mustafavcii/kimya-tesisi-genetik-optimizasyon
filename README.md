# kimya-tesisi-genetik-optimizasyon
# Genetik Algoritma ile Kimya Tesisi Optimizasyonu (Senaryo 5)

Bu proje, **Yapay Zeka Sistemleri** dersi kapsamında geliştirilmiştir. Genetik Algoritma (GA) kullanılarak, bir kimya tesisindeki reaksiyon süresi ve sıcaklık değerlerinin, üretim kısıtları altında maksimum verimi sağlayacak şekilde optimize edilmesi amaçlanmıştır.

## 📌 Proje Hakkında
* **Ders:** Yapay Zeka Sistemleri
* **Öğrenci:** [Mustafa Umut Avcı]
* **Numara:** [2212721045]
* **Senaryo:** 5 (Kimya Tesisi)

## 🧪 Problem Tanımı
Kimyasal üretimde reaksiyon süresi ($x_1$) ve sıcaklık ($x_2$) verimi etkilemektedir. Amaç, belirli güvenlik ve kapasite kısıtları altında verimi maksimize etmektir.

### Matematiksel Model
* **Amaç Fonksiyonu (Verim):** $$y = 8x_1 + 3x_2 - x_1x_2 + x_1^2$$

* **Değişken Sınırları:**
  * Reaksiyon Süresi ($x_1$): $[10, 60]$ dk
  * Sıcaklık ($x_2$): $[60, 120]$ °C (Problemde $x_2 \ge 60$ kısıtı olduğu için alt sınır güncellenmiştir.)

* **Kısıtlar:**
  * $x_1 + x_2 \le 140$

## 🧬 Kullanılan Yöntemler (Genetik Algoritma)
Problemi çözmek için Python dilinde, herhangi bir hazır GA kütüphanesi kullanılmadan saf kod (from scratch) yazılmıştır.

| Adım | Yöntem | Açıklama |
| :--- | :--- | :--- |
| **Kodlama** | Gerçek Sayı Kodlaması | Değişkenler doğrudan float değerler olarak temsil edildi. |
| **Seçim** | Turnuva Seçimi | Popülasyondan rastgele seçilen bireyler arasından en iyisi seçilir. |
| **Çaprazlama** | Aritmetik Çaprazlama | Ebeveynlerin ağırlıklı ortalaması alınarak yeni bireyler üretilir. |
| **Mutasyon** | Uniform Mutasyon | Genler belirli bir olasılıkla sınırlar içinde rastgele değiştirilir. |
| **Kısıt Yönetimi** | Ceza Fonksiyonu | $x_1 + x_2 > 140$ durumunda fitness değerine yüksek bir ceza uygulanır. |
| **Elitism** | Var | Her neslin en iyi bireyi bir sonraki nesle doğrudan aktarılır. |

## 🚀 Kurulum ve Çalıştırma
Proje Google Colab üzerinde çalıştırılabilir.

1. Repoyu klonlayın veya `.ipynb` dosyasını indirin.
2. Gerekli kütüphanelerin yüklü olduğundan emin olun:
   ```bash
   pip install numpy matplotlib
