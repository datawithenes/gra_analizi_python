
# Python ile CSV dosyalarından veri çekip GRA analizi yapan program

Bu proje, **Gri İlişki Analizi (Grey Relational Analysis - GRA)** yöntemi ile karar destek sistemleri oluşturmak için tasarlanmış bir Python uygulamasıdır. Program, bir CSV dosyasından veri çekerek kriterlere göre normalize eder, kullanıcıdan giriş alınan yönlere ve ağırlıklara göre analiz yapar ve sonuçları bir CSV dosyasına kaydeder.

## Özellikler
- **Kriter Yönetimi:** Kullanıcıdan her kriter için "daha büyük daha iyi" (max) veya "daha küçük daha iyi" (min) şeklinde yön girişi alır.
- **Ağırlık Desteği:** Her bir kriter için ağırlık değerleri girilebilir.
- **Sonuç Kaydı:** Analiz sonuçlarını, girdi dosyasının yanına bir CSV dosyası olarak kaydeder.
- **Dinamik Kullanım:** Herhangi bir sayıdaki kriter ve alternatif ile çalışabilir.

## Gerekli Kütüphaneler
Proje, aşağıdaki Python kütüphanelerini kullanır:
- **pandas**: Veri manipülasyonu ve analiz için.
- **numpy**: Matematiksel işlemler ve hesaplamalar için.

Kurulum:
```bash
pip install pandas numpy
```

## Kullanım

1. **CSV Dosyası Hazırlama:**
   - Veri dosyanız, ilk sütununda alternatif isimleri olacak şekilde yapılandırılmalıdır. Diğer sütunlar kriter değerlerini içermelidir.
   - Örnek bir CSV formatı:

     | Alternatif | K1    | K2   | K3   | K4  |
     |------------|-------|------|------|-----|
     | A1         | 105000| 105  | 10   | 4   |
     | A2         | 120000| 110  | 15   | 4   |
     | A3         | 150000| 120  | 12   | 3   |

2. **Programı Çalıştırma:**
   - Programı başlatın ve istenen girişleri yapın:
     - **CSV dosyasının yolunu girin:** Veri dosyanızın tam yolunu belirtin.
     - **Kriter ağırlıklarını girin:** Her bir kriterin ağırlık değerlerini virgülle ayırın.
     - **Kriter yönünü belirtin:** Her kriter için "min" veya "max" girin.

3. **Sonuçları Kaydetme:**
   - Program, sonuçları CSV dosyasının bulunduğu dizine `sonuclar.csv` adıyla kaydeder.

## Kod Yapısı
1. **normalize_data(df, criteria_directions):**
   - Verilen kriter yönüne göre (min veya max) verileri normalize eder.

2. **gra_analysis(df, criteria_directions, weights):**
   - GRA analizi yaparak alternatiflerin skorlarını hesaplar.

3. **Ana Akış:**
   - CSV dosyası okuma.
   - Kullanıcıdan kriter ağırlıkları ve yönlerini alma.
   - Analizi çalıştırma ve sonuçları kaydetme.

## Örnek Kullanım
- **Girdi:**
  ```text
  CSV dosyası yolu: C:/Users/Enes/Desktop/example_gra_data.csv
  Kriter ağırlıkları: 0.05, 0.2, 0.1, 0.15, 0.1, 0.4
  Kriter yönleri:
  K1: min
  K2: max
  K3: min
  K4: max
  ```

- **Çıktı:**
  `sonuclar.csv` adında bir dosya:

  | Alternatif | GRA Skoru |
  |------------|-----------|
  | A2         | 0.800     |
  | A1         | 0.750     |
  | A4         | 0.700     |

## Katkı
Bu projeye katkıda bulunmak isterseniz, lütfen bir **Pull Request** oluşturun veya benimle (datawithenes)(enozkn.com) iletişime geçin.

## Lisans
Bu proje MIT Lisansı altında sunulmuştur. Detaylar için `LICENSE` dosyasına bakın.

