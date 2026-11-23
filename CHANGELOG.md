# Sürüm notu

## 10.1.3 — 2026-11-23

- **Google Earth bağlantısı koordinata gider.** Önceden düğme yer adını arıyordu (ör. Mezarlı Mantar Kaya → "Yenice, Develi" köyü). Artık koordinatı olan 12 noktada bağlantı doğrudan noktanın koordinatını açar; koordinatsız 5 noktada ad araması kalır. Düğme etiketi hangisi olduğunu söyler: "Google Earth (koordinat)" / "(ad araması)".
- Doğrulanmamış ya da yaklaşık konumlarda (ör. Kırgıbayır = Şıhlı merkezi) bağlantının ipucu ve açılır penceresi, işaretin yerin kendisi olmayabileceğini belirtir.
- Amaç: kaynaklı bilgi (atlas kartı, Zotero/web) → Google Earth 3B'de yerin kendisi.

## 10.1.2 — 2026-11-23

- Mezarlı Mantar Kaya (Yenice köyü): konum eklendi — 38,25042 K, 35,68350 D (38°15′01,5″ K, 35°41′00,6″ D). Koordinat, öneren Nezir Ötegen'in gönderdiği harita işaretidir; yeni konum durumu **"öneren konumu (doğrulanmadı)"** ile gösterilir (doğrulanmamış işaret biçimi). Bağımsız saha/uydu doğrulaması ve kaya mezarının tescil durumu bekliyor; içerik iddiaları değişmeden "doğrulama bekliyor".
- Noktanın VS30 değeri: 394 m/s (komşu pikseller 272–437), yaklaşık TBDY karşılığı ZC (USGS eğim tabanlı vekil).
- Yeni nokta: **Bostanlık Yaylası Kırgıbayır (Badlands) Bölgesi (Şıhlı)** — Nezir Ötegen'in önerisi ve derlemesi (22 Kasım 2026). Kesin yer bilinmiyor; işaret Şıhlı yerleşim merkezidir (konum durumu "yaklaşık"; GeoNames türevi koordinat 38,0883 K, 35,6281 D). Kaynak düzeyi "yok", içerik "doğrulama bekliyor". VS30 666 m/s (458–900), ≈ ZC.
- Haritada 12/17 nokta.

## 10.1.1 — 2026-11-22

- Başlık sadeleşti: "Kayseri Develi Jeo-Tur | Erciyes–Zamantı Dijital Jeoturizm Atlası" (Seyhan, havza bağlantısı olarak içerikte ve haritada kalır).
- Arıcılık katmanı "araştırma aşamasında" olarak etiketlendi: 1 nokta tanımlı, haritada 0; tamamlanmış bir harita katmanı değildir.
- Blog rehber sayfası yayında: https://aliosmanoncel.blogspot.com/p/kayseri-develi-geotour.html

## 10.1.0 — 2026-11-22

- Yeni katman: **VS30** (USGS Global Vs30 Mosaic, eğim tabanlı yaklaşık; varsayılan kapalı) ve lejantı.
- Her noktada VS30 değeri, komşu piksel aralığı ve yaklaşık TBDY 2018 karşılığı. Göksu birleşmesi kesit dışında.
- `docs/TEKNIK-NOT.md` §7: kaynak, ızgara, sınıflama ve sınırlılıklar.

## 10.0.5 — 2026-11-22

- Proje adı **Kayseri Develi Jeo-Tur**; depo `kayseri-develi-geotour`. Yeni canlı adres: https://aliosmanoncel.github.io/kayseri-develi-geotour/
- Başlık: "Kayseri Develi Jeo-Tur | Erciyes–Zamantı–Seyhan Dijital Jeoturizm Atlası". İçerik değişikliği yok.

## 10.0.4 — 2026-11-22

- Üçüncü doğrulama boyutu: **kaynak güvenilirliği** (birincil / ikincil / yok). Her nokta ve her kaynak etiketlendi; uygulamada üçüncü rozet. Dağılım: 5 birincil, 9 ikincil, 2 kaynaksız.

## 10.0.3 — 2026-11-22

- Mezarlı Mantar Kaya: yaklaşık bölge tarifi eklendi (Hüseyinli – Yenice – Avlağa – Gümüşören Barajı kıyısı); "hangi Yenice" sorusu yanıtlandı (Yenice köyü). Koordinat bekleniyor, haritada işaret yok.

## 10.0.2 — 2026-11-22

- Arayüz: haritaya kaydırıldığında üst kısmın yapışkan başlık altında kalması düzeltildi (`scroll-margin-top`). İçerik değişikliği yok.
- GitHub Pages ile yayımlandı: https://aliosmanoncel.github.io/develi-geotour/ (eski adres; 10.0.5'te değişti)

## 10.0.1 — 2026-11-22

- Uygulamaya ve README'ye "bilimsel durum" uyarısı: açık erişim ≠ nihai bilimsel onay.
- 1940 depremi: tarih (20/21 Şubat) ve büyüklük (M 5,4 / Ms 5,2 / Mw ≈ 6,7) "doğrulama bekliyor"; işaret katalog dış merkezine (38,40 K 35,30 D) taşındı.
- Gereme ve Elbiz Parkı koordinatları haritadan kaldırıldı (v9 kaynaklı, doğrulanmamış). Haritada 10/16 nokta.
- README: MTA verisinin kullanım ve dağıtım koşulları.
- Yayın: GitHub Pages `main` /(root) dalından; özel Actions iş akışı (deploy-pages@v4 artifact hatası) kaldırıldı.
- `docs/TEKNIK-NOT.md`: kesit üretimi ve sapma ölçümü (en fazla 127 m, ortanca 18 m; mutlak doğruluk değildir).

## 10.0.0 — 2026-11-22

**Mimari**
- Veri koddan ayrıldı: `data/points.json`, `data/faults-mta2026-develi.geojson`.
- Fay katmanı: elle girilmiş koordinat yerine MTA 2026 Diri Fay Haritası kesiti; etkinliğe göre üç sınıf (yüzey kırığı / Holosen / Kuvaterner-olası), lejant ve açılır pencerede özgün öznitelik.
- `L.control.layers` ile katman aç/kapa (bal-yolu-harita deseni); çip süzgeci korundu.
- Zamantı rehberli turu (kafz-geowalk deseni), elle ileri/geri; Web Speech API ile isteğe bağlı sesli anlatım.
- Google Earth bağlantıları arama-URL biçimine geçti (page-to-post v4.17); KML dışa aktarma eklendi.
- `navigator.share` + pano yedeği; `#nokta` derin bağlantı.
- Kalıcı olmayan yorum kutuları kaldırıldı; blog yorumlarına yönlendirme.
- Müzik varsayılan olarak kapalı; tek parça, doğru etiket.
- `alert()` kaldırıldı; XSS'e karşı `textContent`; Leaflet SRI.

**İçerik** (ayrıntı: `docs/ICERIK-DENETIMI.md`)
- 1940 depremi: 20 Şubat, 37 can kaybı (Salomon-Calvi); "300 hane" çıkarıldı.
- 1717: fay (Ecemiş) ve büyüklük (7,4) ataması kaldırıldı.
- "2023 Sarız Fayı" noktası kaldırıldı; 2023 yüzey kırıkları MTA katmanında.
- Zamantı rotası düzeltildi: Sarız durağı → Pınarbaşı; kaynak Uzunyayla/Şerefiye (~1500 m); Göksu birleşmesi ~45 km düzeltildi (Aladağ).
- Faraşa = Çamlıca; "peribacası" tanımı kaldırıldı.
- "Spistra", "dünya klasmanı rafting", "2300 m karstik kaynak" çıkarıldı.
- Yeni: Mezarlı Mantar Kaya (öneri: Nezir Ötegen; doğrulama bekliyor), Erciyes gezgin arıcılığı, arıcılık katmanı.

## 9 — 2025-11 (Zamantı Özel Final)
Blogger yazısına gömülü tek HTML; Deprem, Tarih, Doğa, Zamantı katmanları.
