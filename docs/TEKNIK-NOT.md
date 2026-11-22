# Teknik not — fay kesitinin üretimi ve sadeleştirme sapması

**Sürüm:** 10.0.1 · **Tarih:** 2026-11-22

## 1. Girdi

- Dosya: `turkiye_diri_fay.geojson` (MTA 2026 Türkiye Diri Fay Haritası, 12.963 obje, EPSG:4326), `fay-yolu-aricilik-veri-bankasi/data/` deposundaki kopya.
- Atıf: Elmacı vd. (2026), MTA Özel Yayın Serisi-60, ISBN 978-625-8107-74-6.

## 2. Kırpma

Bir obje, en az bir köşe noktası boylam 34,75–36,85 ve enlem 37,35–39,05 kutusuna düşüyorsa alınır; obje kesilmez, tümüyle tutulur. Sonuç: 608 obje.

Korunan öznitelikler: `fay_adi`, `segment`, `aktivite`, `kayma_turu`, `fay_tipi`, `dep_tarih`, `dep_mag`. `&lt;Null&gt;` değerleri `null` yapıldı. `atif` alanı her objede aynı olduğu için koleksiyon düzeyine (`kaynak`) taşındı.

## 3. Sadeleştirme

1. Koordinatlar 4 ondalığa yuvarlandı (≈ 11 m enlem, ≈ 9 m boylam adım), ardışık yinelenen noktalar atıldı.
2. Her çizgiye Douglas–Peucker uygulandı; tolerans **0,0012°**, derece uzayında dik uzaklıkla.
3. Köşe sayısı 14.796 → 1.538; dosya 1,3 MB → 155 KB.

## 4. Sapmanın ölçülmesi

**Tanım:** Her özgün MTA köşe noktasının, karşılık gelen sadeleştirilmiş çizgiye en kısa dik uzaklığı (metre).

**Yöntem:** Her çizgi için ilk köşenin enlemi φ₀ alınarak yerel eşdikdörtgen izdüşüm: x = λ·R·cos φ₀, y = φ·R; R = 6.371.008,8 m. Nokta–doğru parçası uzaklığı bu düzlemde hesaplandı. Ölçek ve kesitin boyutu (~2°) için izdüşüm hatası sapma değerlerinin yanında ihmal edilebilir düzeydedir.

**Sonuç (n = 14.800 özgün köşe):**

| İstatistik | Metre |
|---|---|
| En fazla | 127,2 |
| %99 | 101,2 |
| %95 | 78,3 |
| Ortalama | 25,8 |
| Ortanca | 17,7 |

Değerler, yuvarlama ve Douglas–Peucker etkisini birlikte içerir.

## 5. Bu değer ne değildir

Bu sayılar **yalnızca sadeleştirilmiş gösterimin özgün MTA çizgisinden ne kadar uzaklaştığını** ölçer. Özgün haritanın arazideki fay izine göre **mutlak konum doğruluğu değildir**; o doğruluk MTA'nın haritalama ölçeğine, yöntemine ve segmentin türüne bağlıdır ve bu çalışmada değerlendirilmemiştir. Toplam belirsizlik, özgün haritanın belirsizliği ile buradaki sadeleştirme farkının birleşimidir.

Bu kesit görselleştirme ve eğitim içindir; parsel, yapı veya planlama kararında kullanılmaz. Yerel sorgu için AFAD'ın Türkiye Diri Fay Haritası sistemi ve MTA yayınlarına başvurulmalıdır.

## 6. Yeniden üretim

Kırpma ve sadeleştirme, Python standart kitaplığıyla (json, math) yapıldı; harici GIS paketi kullanılmadı. Aynı girdi ve parametrelerle aynı çıktı elde edilir.

## 7. VS30 katmanı (v10.1.0)

**Kaynak:** USGS Global Vs30 Mosaic (U.S. Geological Survey, 2025; https://doi.org/10.5066/P1NV6UNM). Bu bölgede değerler Wald ve Allen (2007) topoğrafik eğim yöntemine dayanır. Kesit, USGS Vs30 Map Viewer üzerinden 2026-11-22'de kullanıcı tarafından alındı (ArcGIS "VS30_extract" aracı).

**Dosyalar:** `data/vs30-usgs-kayseri.tif` (+ `.tfw`, özgün kesit), `data/vs30-usgs-kayseri.png` (gösterim).

**Izgara:** 410 × 207 piksel, 0,0083333° (30 açı saniyesi, ~0,83 km), WGS84. Kenar sınırları: B 33,929167 · D 37,345833 · G 37,720833 · K 39,445833. Değer aralığı 180–900 m/s (eğim yönteminin tipik sınırları).

**Nokta değeri:** Noktayı içeren piksel değeridir; `min3x3`–`max3x3` komşu dokuz pikselin aralığıdır ve 0,83 km'lik çözünürlükteki konum duyarlılığını gösterir. Göksu birleşme noktası (37,61 K) kesitin dışındadır.

**Gösterim:** 8 aralık (Allen & Wald, 2007, OFR 2007-1357 lejant aralıkları): <180, 180–240, 240–300, 300–360, 360–490, 490–620, 620–760, >760 m/s; saydamlık %25.

**Yaklaşık TBDY 2018 karşılığı:** Yalnız VS30 eşiklerine göre (Tablo 16.1): ZA >1500, ZB 760–1500, ZC 360–760, ZD 180–360, ZE <180 m/s. TBDY'de yerel zemin sınıfı saha etüdüyle (VS30, (N60)30, (cu)30 ve zemin cinsi) belirlenir; buradaki karşılık bir **yaklaşım**dır, zemin sınıfı değildir.

**Sınırlılık:** Eğim tabanlı VS30, düz havzalarda (ör. Sultan Sazlığı) ve volkanik platolarda büyük sapma gösterebilir. Ölçülmüş bir zemin verisi değildir; mühendislik, parsel veya yapı kararında kullanılmaz.
