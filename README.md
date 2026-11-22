# Develi Jeo-Tur v10 — Erciyes'ten Seyhan'a

Develi, Erciyes ve Zamantı Irmağı boyunca jeoloji, diri faylar, tarihsel depremler, arkeoloji, doğa ve arıcılık katmanlarını **kaynaklarıyla** gösteren etkileşimli harita.

**Canlı:** `https://aliosmanoncel.github.io/develi-geotour/` (GitHub Pages; yayımlanınca etkin)
**Blog:** [Develi Dijital Rehberi (2025)](https://aliosmanoncel.blogspot.com/2025/11/develidigitalguide.html)

## İlke

1. **Fay çizgileri elle çizilmez.** Fay katmanı MTA 2026 Türkiye Diri Fay Haritası'nın bölge kesitidir (sadeleştirilmiş, ~130 m).
2. **Deprem işareti ≠ dış merkez.** Tarihsel deprem işaretleri yaklaşık hasar/yerleşim merkezidir; kaynak fay, kaynağında belirtilmedikçe ima edilmez.
3. **Her nokta iki rozet taşır:** konum (`doğrulandı / yaklaşık / konum yok`) ve içerik (`doğrulandı / kısmen / doğrulama bekliyor`).
4. **Katmanlar ayrıdır:** jeoloji, deprem, tarih, doğa, Zamantı rotası, arıcılık. Katmanlar arası nedensellik öne sürülmez.

## Yapı

```
index.html                         Uygulama (Leaflet 1.9.4, SRI)
data/points.json                   16 nokta, kaynak ve doğrulama durumu
data/faults-mta2026-develi.geojson 608 fay objesi (MTA 2026 kesiti)
docs/MIMARI-DEGERLENDIRME.md       kafz-geowalk ve bal-yolu-harita karşılaştırması
docs/ICERIK-DENETIMI.md            v9 → v10 iddia denetimi
CHANGELOG.md
```

Yerelde çalıştırma: `python -m http.server` (veri `fetch` ile yüklendiği için dosyayı doğrudan açmak çalışmaz).

## Veri kaynağı ve atıf

Elmacı, H., Kürçer, A., Özalp, S., Altuntaş, G., Avcı, H.O., Aydoğan, H., Yüce, A.A., Öztürker, A.R., Karayazı, O., Bayrak, A., Özdemir, E., Çal, Ç., Güven, C., Yalvaç, O., 2026. *Türkiye Diri Fay Haritası.* Maden Tetkik ve Arama Genel Müdürlüğü, Özel Yayın Serisi-60. ISBN 978-625-8107-74-6. Ankara.

Fay kesiti, [`fay-yolu-aricilik-veri-bankasi`](https://github.com/aliosmanoncel/fay-yolu-aricilik-veri-bankasi) deposundaki `data/turkiye_diri_fay.geojson` dosyasından türetilmiştir. Mühendislik veya planlama amacıyla özgün MTA verisine başvurun.

Nokta kaynakları `data/points.json` içinde her noktanın `kaynak` alanındadır.

## Katkı

Mezarlı Mantar Kaya (Yenice) önerisi: Nezir Ötegen (gazeteci-yazar), 2026-11-21.

## Lisans

CC BY-NC-SA 4.0 — © 2026 Ali Osman Öncel, İstanbul Üniversitesi-Cerrahpaşa. Harita altlığı © OpenStreetMap katkıcıları, © CARTO. Müzik: Pixabay İçerik Lisansı.
