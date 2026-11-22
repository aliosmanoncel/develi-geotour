# Mimari değerlendirme — Kayseri Develi Jeo-Tur v10

**Tarih:** 2026-11-22 · **Karşılaştırılan:** `kafz-geowalk` (index.html, 644 satır, Şubat 2026) ve `bal-yolu-harita` (bal-yolu-harita.html, 1029 satır, Haziran 2026, v11) · **Temel:** Develi Jeo-Tur v9 (Kasım 2025)

## 1. Bulgu özeti

| Bileşen | Develi v9 | kafz-geowalk | bal-yolu-harita | v10 kararı |
|---|---|---|---|---|
| Kod kökeni | Tek HTML | v9 ile aynı soy (standby, müzik, yorum, tema) | Bağımsız, Leaflet | kafz-geowalk düzeni temel alındı, yeniden yazıldı |
| Veri/kod ayrımı | Veri JS içinde | Veri JS içinde (`PTS`, `RUPS`) | Veri JS içinde | **`data/points.json` + `data/*.geojson`**, fetch ile |
| Fay çizgileri | Yok (yalnız 3 nokta) | `RUPS` — elle girilmiş koordinatlar | 16 `L.polyline`, kendi notu: "genelleştirilmiş hat" | **MTA 2026 diri fay kesiti** (608 obje), elle çizim yok |
| Fay hiyerarşisi | — | Tek renk, kesikli | Faylar soluk arka plan, rota parlak ön plan | bal-yolu ilkesi + **MTA etkinlik sınıfına göre** renk (DYK / Holosen / Kuvaterner-olası) |
| Katman kontrolü | Çip filtre | Çip filtre | `L.control.layers` + lejant | Her ikisi: çip + `L.control.layers` + lejant |
| Rehberli tur | Yok | `gwTour/Step/Pause/Resume` (9 sn zamanlayıcı) | Yok | Elle ileri/geri; otomatik zamanlayıcı yok (okuma hızına saygı) |
| Sesli anlatım | Düğme, işlevsiz | `gwVoice()` = `alert()` | Yok | **Web Speech API** (`tr-TR`), isteğe bağlı |
| Paylaşım | `alert()` | `navigator.share` | Yok | `navigator.share` + pano yedeği + `#nokta` derin bağlantı |
| Google Earth | `@lat,lon,...` kamera URL'si | `@lat,lon,...` | `@lat,lon,...` | **Arama-URL biçimi** (page-to-post v4.17 kuralı) |
| KML dışa aktarma | Yok | Yok | Yok | Var (v4.17 iskeleti) |
| Yorumlar | Yerel, kalıcı değil | Yerel, kalıcı değil | Yok | Kaldırıldı → blog yorumlarına bağlantı |
| Müzik | Otomatik başlatma katmanı, 2 parça (aynı dosya adı) | Aynı | Yok | Varsayılan kapalı, tek parça, dürüst etiket |
| `alert()` kullanımı | 3 | 3 | 0 | 0 (toast) |
| Kaynak gösterimi | Yok | Yok | Altbilgi | **Her noktada kaynak listesi + doğrulama rozeti** |
| XSS güvenliği | `innerHTML` + şablon dize | Aynı | Aynı | Kartlar `textContent` ile; açılır pencerede kaçışlı metin |
| CDN bütünlüğü | Yok | Yok | Yok | Leaflet 1.9.4 SRI (npm paketiyle doğrulandı) |

## 2. Neden yeniden yazım, neden kopyala-yapıştır değil

`kafz-geowalk` en yakın akraba, ancak üç kusuru v10'un bilimsel ilkesiyle çelişiyor: (1) fay geometrisi elle girilmiş, (2) sesli rehber ve yorumlar işlevsiz, (3) veri kodun içinde. Bu yüzden *desen* alındı (tur, paylaşım, tema), kod yeniden yazıldı. `bal-yolu-harita`'dan görsel hiyerarşi ve katman kontrolü alındı; elle çizilmiş fay hatları alınmadı.

## 3. İleriye dönük öneri (bu sürümde uygulanmadı)

- `kafz-geowalk` ve `bal-yolu-harita` da aynı `data/` + MTA kesiti desenine taşınabilir; böylece üç uygulama ortak bir yükleyiciyi paylaşır.
- `fay-yolu-aricilik-veri-bankasi/scripts/eq_fetch_turkey.py` hattı, ileride "son depremler" katmanı için kullanılabilir (bu sürümde canlı veri yok).
