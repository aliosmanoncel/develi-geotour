# 🌋 Kayseri Develi Jeo-Tur | Erciyes–Zamantı Dijital Jeoturizm Atlası

Jeoloji, tarihsel depremler, arkeolojik miras, doğal çevre ve arıcılık katmanlarıyla etkileşimli bir coğrafi keşif.

> **Bilimsel durum:** Depo açık erişimlidir; içerik doğrulama sürecindedir. Deponun genel erişime açılması, bilimsel içeriğin nihai olarak onaylandığı anlamına gelmez. Doğrulama durumu her noktada ayrı ayrı belirtilir; açık konular `docs/ICERIK-DENETIMI.md` §4'tedir.

Develi, Erciyes ve Zamantı Irmağı boyunca jeoloji, diri faylar, tarihsel depremler, arkeoloji, doğa ve arıcılık katmanlarını **kaynaklarıyla** gösteren etkileşimli harita.

**Canlı:** https://aliosmanoncel.github.io/kayseri-develi-geotour/ (GitHub Pages, `main` dalı kökünden yayımlanır)
**Blog rehber sayfası:** https://aliosmanoncel.blogspot.com/p/kayseri-develi-geotour.html
**Önceki sürüm (v9, 2025):** [Develi Dijital Rehberi](https://aliosmanoncel.blogspot.com/2025/11/develidigitalguide.html)

> Depo adı 2026-11-22'de `develi-geotour` → `kayseri-develi-geotour` olarak değiştirildi. Eski depo adresi GitHub tarafından yönlendirilir; eski Pages adresi (`/develi-geotour/`) artık çalışmaz.

## İlke

1. **Fay çizgileri elle çizilmez.** Fay katmanı MTA 2026 Türkiye Diri Fay Haritası'nın bölge kesitidir (sadeleştirilmiş; özgün çizgiden sapma en fazla 127 m, ortanca 18 m — bu değer özgün haritanın konum doğruluğu değildir, bkz. `docs/TEKNIK-NOT.md`).
2. **Deprem işareti ≠ dış merkez.** Tarihsel deprem işaretleri yaklaşık hasar/yerleşim merkezidir; kaynak fay, kaynağında belirtilmedikçe ima edilmez.
3. **Her nokta iki rozet taşır:** konum (`doğrulandı / yaklaşık / konum yok`) ve içerik (`doğrulandı / kısmen / doğrulama bekliyor`).
4. **Katmanlar ayrıdır:** jeoloji, deprem, tarih, doğa, Zamantı rotası, arıcılık. Katmanlar arası nedensellik öne sürülmez.

## Yapı

```
index.html                         Uygulama (Leaflet 1.9.4, SRI)
data/points.json                   16 nokta, kaynak ve doğrulama durumu
data/faults-mta2026-develi.geojson 608 fay objesi (MTA 2026 kesiti)
data/vs30-usgs-kayseri.tif/.png    VS30 kesiti (USGS, eğim tabanlı yaklaşık)
docs/MIMARI-DEGERLENDIRME.md       kafz-geowalk ve bal-yolu-harita karşılaştırması
docs/ICERIK-DENETIMI.md            v9 → v10 iddia denetimi
docs/TEKNIK-NOT.md                 Fay kesiti üretimi ve sadeleştirme sapması
CHANGELOG.md
```

Yayın: GitHub Pages, kaynak `main` /(root); `.nojekyll` ile dosyalar işlenmeden sunulur. Yerelde çalıştırma: `python -m http.server` (veri `fetch` ile yüklendiği için dosyayı doğrudan açmak çalışmaz).

## Veri kaynağı ve atıf

Elmacı, H., Kürçer, A., Özalp, S., Altuntaş, G., Avcı, H.O., Aydoğan, H., Yüce, A.A., Öztürker, A.R., Karayazı, O., Bayrak, A., Özdemir, E., Çal, Ç., Güven, C., Yalvaç, O., 2026. *Türkiye Diri Fay Haritası.* Maden Tetkik ve Arama Genel Müdürlüğü, Özel Yayın Serisi-60. ISBN 978-625-8107-74-6. Ankara.

### MTA verisinin kullanım ve dağıtım koşulları

- **Kaynak ve mülkiyet:** Fay geometrisi ve öznitelikleri MTA Genel Müdürlüğü'ne (Jeoloji Etütleri Dairesi Başkanlığı) aittir. Yukarıdaki atıf her kullanımda zorunludur.
- **Lisans durumu:** MTA'nın 2026 sayısal verisi için açık bir yeniden dağıtım lisansı bu çalışmada bulunamadı. Bu depodaki kesit; kamuya tanıtılmış haritanın, ticari olmayan eğitim ve bilim iletişimi amacıyla, atıfla ve sadeleştirilmiş olarak türetilmiş küçük bir alt kümesidir. Özgün veri yerine geçmez.
- **Bu deponun lisansı (CC BY-NC-SA 4.0)** yalnız bu depodaki özgün katkıları (nokta verisi, kod, belgeler, kesitin üretimi) kapsar; MTA verisinin kendisine ek hak tanımaz.
- **Kaldırma:** MTA'nın talebi hâlinde fay kesiti depodan kaldırılır.
- **Özgün veriye erişim:** MTA yayınları ve AFAD'ın Türkiye Diri Fay Haritası sorgu sistemi.

Fay kesiti, [`fay-yolu-aricilik-veri-bankasi`](https://github.com/aliosmanoncel/fay-yolu-aricilik-veri-bankasi) deposundaki `data/turkiye_diri_fay.geojson` dosyasından türetilmiştir. Mühendislik veya planlama amacıyla özgün MTA verisine başvurun.

**VS30:** U.S. Geological Survey (2025). *The U.S. Geological Survey Global Vs30 Mosaic.* https://doi.org/10.5066/P1NV6UNM (kamu malı). Yöntem: Wald, D. J., & Allen, T. I. (2007). Topographic slope as a proxy for seismic site conditions and amplification. *BSSA, 97*(5), 1379–1395. https://doi.org/10.1785/0120060267. Eğim tabanlı yaklaşık değerdir; ölçülmüş zemin verisi değildir (bkz. `docs/TEKNIK-NOT.md` §7).

Nokta kaynakları `data/points.json` içinde her noktanın `kaynak` alanındadır.

## Katkı

Mezarlı Mantar Kaya (Yenice) önerisi: Nezir Ötegen (gazeteci-yazar), 2026-11-21.

## Lisans

CC BY-NC-SA 4.0 — © 2026 Ali Osman Öncel, İstanbul Üniversitesi-Cerrahpaşa. Harita altlığı © OpenStreetMap katkıcıları, © CARTO. Müzik: Pixabay İçerik Lisansı.
