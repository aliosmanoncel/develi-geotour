# Sürüm notu

## 10.0.3 — 2026-11-22

- Mezarlı Mantar Kaya: yaklaşık bölge tarifi eklendi (Hüseyinli – Yenice – Avlağa – Gümüşören Barajı kıyısı); "hangi Yenice" sorusu yanıtlandı (Yenice köyü). Koordinat bekleniyor, haritada işaret yok.

## 10.0.2 — 2026-11-22

- Arayüz: haritaya kaydırıldığında üst kısmın yapışkan başlık altında kalması düzeltildi (`scroll-margin-top`). İçerik değişikliği yok.
- GitHub Pages ile yayımlandı: https://aliosmanoncel.github.io/develi-geotour/

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
