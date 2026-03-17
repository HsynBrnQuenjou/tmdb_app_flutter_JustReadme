# 🎬 Film & Dizi — Flutter TMDB Uygulaması

<p align="center">
  <img src="screenshots/aciktema_anaekran_1.png" width="160"/>
  <img src="screenshots/karanliktema_anaekran_1.png" width="160"/>
  <img src="screenshots/aciktema_detay_1.png" width="160"/>
  <img src="screenshots/karanliktema_detay_1.png" width="160"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart&logoColor=white"/>
  <img src="https://img.shields.io/badge/TMDB%20API-v3-01D277?logo=themoviedatabase&logoColor=white"/>
  <img src="https://img.shields.io/badge/Platform-iOS%20%7C%20Android-lightgrey"/>
  <img src="https://img.shields.io/badge/Lisans-Ki%C5%9Fisel%20Kullan%C4%B1m-orange"/>
</p>

> **Film & Dizi**, [TMDB (The Movie Database)](https://www.themoviedb.org) API'si kullanılarak geliştirilmiş, tam özellikli bir Flutter film ve dizi keşif uygulamasıdır. Orijinal olarak Swift/SwiftUI ile yazılmış bir iOS uygulamasının birebir Flutter karşılığıdır.

---

## 📋 İçindekiler

- [Özellikler](#-özellikler)
- [Ekran Görüntüleri](#-ekran-görüntüleri)
- [Teknoloji Yığını](#️-teknoloji-yığını)
- [Proje Yapısı](#-proje-yapısı)
- [API Referansı](#-api-referansı)
- [Güvenlik ve Gizlilik](#-güvenlik-ve-gizlilik)
- [Bilinen Kısıtlamalar](#-bilinen-kısıtlamalar)
- [Lisans](#-lisans)

---

## ✨ Özellikler

### 🏠 Ana Sayfa

- **Film / Dizi** sekmesi arasında animasyonlu geçiş
- Ayrı kategorilerde yatay kaydırmalı içerik listeleri:
  - 🔥 Gündemde (Trending — günlük)
  - ⭐ En Yüksek Puanlı
  - 🎬 Vizyondakiler _(yalnızca film)_
  - 🗓️ Yakında _(yalnızca film)_
  - 📺 Güncel Diziler _(yalnızca dizi)_
  - 📡 Bugün Yayında _(yalnızca dizi)_
  - 🎯 En Çok İzlenen
  - 💡 Senin İçin _(rastgele karıştırılmış kişisel öneri)_
- **Pull-to-refresh** ile içerikleri yenileme
- Sağ üstte açık / karanlık tema geçiş düğmesi

### 🔍 Arama

- Gerçek zamanlı arama (yazarken sonuç güncellenir)
- **Tür filtresi:** Tümü, Filmler, Diziler, Oyuncular
- **Sıralama:** Popülerlik, Puan, Tarih
- Gelişmiş çoklu endpoint araması (`multi`, `movie`, `tv`, `person`)
- Oyuncuya göre içerik arama — oyuncunun filmografisini sonuçlara dahil eder
- Arama geçmişini temizleme butonu

### 🎥 Film / Dizi Detay

- Backdrop görseli üzerinde geri ve favori butonları
- Sol altta küçük poster, yanında başlık / yıl / tür / süre bilgisi ve puan
- **+ Listeye Ekle** — istenen özel listeye veya favori listesine ekleme
- **▶ Fragmanı Oynat** — önce Türkçe, sonra İngilizce, son olarak dil filtresi olmadan YouTube fragmanı
- Tagline (italik slogan)
- Özet (tam metin)
- Oyuncular (yatay kaydırmalı, fotoğraf + isim + karakter adı)
- Önerilen içerikler (yatay kaydırmalı)
- Favori durumu kalp ikonu ile anlık güncellenir

### 🎭 Oyuncu Detay

- Büyük yuvarlak profil fotoğrafı
- İsim ve meslek (OYUNCU / YÖNETMENvb.)
- Biyografi — TMDB'de Türkçe yoksa İngilizce biyografi otomatik çevrilir; uzunsa "Daha Fazla Oku / Daha Az Göster" ile katlama
- Kişisel bilgiler: Doğum tarihi, doğum yeri, yaş, meslek
- Filmografi — oyuncunun tüm yapımları puana göre sıralı, "Tümü" ile tüm liste

### 🧭 Keşfet

- Favoriler ve özel listeler baz alınarak TMDB `recommendations` ve `similar` endpointlerinden kişiselleştirilmiş öneri üretimi
- Maksimum 5 tohum içerik seçilerek çeşitli öneriler derlenir
- **Sizin İçin Seçtiklerimiz** ve **Gözden Kaçanlar** olarak iki grup halinde sunulur
- Pull-to-refresh ile yeni öneri seti üretme
- Favoriler / listeler boşsa yönlendirici boş durum ekranı

### ❤️ Favoriler

- Favori film ve dizileri ızgara görünümünde listeler
- **Sıralama:** Eklenme tarihi, İsim, Puan
- Her kartta: poster, başlık, puan, tür etiketi (Film / Dizi)
- Sağ üstteki × ile favoriden çıkarma (onay dialogu ile)
- Boş durum ekranı ile yönlendirme

### 📋 Listeler

- Özel liste oluşturma (isim + hazır şablon çipleri)
- Liste kartında: küçük poster önizleme (max 3), içerik sayısı, oluşturma tarihi
- Sola kaydırarak silme (Dismissible)
- **Liste Detay:**
  - Sıralama: Eklenme tarihi, İsim, Puan
  - İçerik sayacı
  - Sağ üstte ··· menüsü → İsmi Değiştir / Listeyi Sil
  - Her karttan içeriği çıkarma (onay dialogu ile)

### 🌙 Tema

- Açık ve karanlık tema — Material 3 tabanlı
- Tema tercihi `SharedPreferences`'a kaydedilir; uygulama yeniden açıldığında korunur
- Özel renk paleti: Ana renk `#6C5CE7` (mor), vurgu `#D6A054` (altın sarısı)
- Karanlık temada arka plan `#0D0D1A`, kart rengi `#1A1A2E`

### ♾️ Sonsuz Kaydırma

- "Tümü" ekranlarında sayfa sayfa yükleme (`page` parametresi ile)
- `combined_credits` endpoint'i sayfalamayı desteklemediğinden bu özel durum ele alınmıştır
- Yükleme sırasında iki adet `CircularProgressIndicator` gösterilir

---

## 📱 Ekran Görüntüleri

### 🏠 Ana Sayfa

|           Açık Tema — Filmler            |       Açık Tema — Vizyon & Yakında       |        Açık Tema — En Çok İzlenen        |
| :--------------------------------------: | :--------------------------------------: | :--------------------------------------: |
| ![](screenshots/aciktema_anaekran_1.png) | ![](screenshots/aciktema_anaekran_2.png) | ![](screenshots/aciktema_anaekran_3.png) |

|           Karanlık Tema — Filmler            |       Karanlık Tema — Vizyon & Yakında       |        Karanlık Tema — En Çok İzlenen        |
| :------------------------------------------: | :------------------------------------------: | :------------------------------------------: |
| ![](screenshots/karanliktema_anaekran_1.png) | ![](screenshots/karanliktema_anaekran_2.png) | ![](screenshots/karanliktema_anaekran_3.png) |

|                Açık — En Yüksek Puanlı                |                 Karanlık — Gündemde                 |
| :---------------------------------------------------: | :-------------------------------------------------: |
| ![](screenshots/aciktema_anasayfa_enyuksekpuanli.png) | ![](screenshots/karanliktema_anasayfa_gundemde.png) |

---

### 🎥 Film / Dizi Detay

|            Açık Tema — Üst            |            Açık Tema — Alt            |            Karanlık Tema — Üst            |            Karanlık Tema — Alt            |
| :-----------------------------------: | :-----------------------------------: | :---------------------------------------: | :---------------------------------------: |
| ![](screenshots/aciktema_detay_1.png) | ![](screenshots/aciktema_detay_2.png) | ![](screenshots/karanliktema_detay_1.png) | ![](screenshots/karanliktema_detay_2.png) |

---

### 🔍 Arama

|            Açık — Arama             |               Açık — Detay 1                |               Açık — Detay 2                |
| :---------------------------------: | :-----------------------------------------: | :-----------------------------------------: |
| ![](screenshots/aciktema_arama.png) | ![](screenshots/aciktema_arama_detay_1.png) | ![](screenshots/aciktema_arama_detay_2.png) |

|            Karanlık — Arama             |               Karanlık — Detay 1                |               Karanlık — Detay 2                |
| :-------------------------------------: | :---------------------------------------------: | :---------------------------------------------: |
| ![](screenshots/karanliktema_arama.png) | ![](screenshots/karanliktema_arama_detay_1.png) | ![](screenshots/karanliktema_arama_detay_2.png) |

---

### 🎭 Oyuncu Detay

|                Açık — Profil                |               Açık — Bilgiler               |                  Açık — Filmografi                   |
| :-----------------------------------------: | :-----------------------------------------: | :--------------------------------------------------: |
| ![](screenshots/aciktema_oyuncudetay_1.png) | ![](screenshots/aciktema_oyuncudetay_2.png) | ![](screenshots/aciktema_oyuncudetay_filmografi.png) |

|                Karanlık — Profil                |               Karanlık — Bilgiler               |                  Karanlık — Filmografi                   |
| :---------------------------------------------: | :---------------------------------------------: | :------------------------------------------------------: |
| ![](screenshots/karanliktema_oyuncudetay_1.png) | ![](screenshots/karanliktema_oyuncudetay_2.png) | ![](screenshots/karanliktema_oyuncudetay_filmografi.png) |

---

### 🧭 Keşfet

|            Açık — Keşfet             |                       Açık — Sizin İçin                       |                Açık — Gözden Kaçanlar                |
| :----------------------------------: | :-----------------------------------------------------------: | :--------------------------------------------------: |
| ![](screenshots/aciktema_kesfet.png) | ![](screenshots/aciktema_kesfet_sizin_icin_sectiklerimiz.png) | ![](screenshots/aciktema_kesfet_gozden_kacanlar.png) |

|            Karanlık — Keşfet             |                       Karanlık — Sizin İçin                       |                Karanlık — Gözden Kaçanlar                |
| :--------------------------------------: | :---------------------------------------------------------------: | :------------------------------------------------------: |
| ![](screenshots/karanliktema_kesfet.png) | ![](screenshots/karanliktema_kesfet_sizin_icin_sectiklerimiz.png) | ![](screenshots/karanliktema_kesfet_gozden_kacanlar.png) |

---

### 📋 Listeler

|            Açık — Listeler             |            Açık — Liste Detay             |            Karanlık — Listeler             |            Karanlık — Liste Detay             |
| :------------------------------------: | :---------------------------------------: | :----------------------------------------: | :-------------------------------------------: |
| ![](screenshots/aciktema_listeler.png) | ![](screenshots/aciktema_liste_detay.png) | ![](screenshots/karanliktema_listeler.png) | ![](screenshots/karanliktema_liste_detay.png) |

|            Karanlık — Liste Oluşturma             |
| :-----------------------------------------------: |
| ![](screenshots/karanliktema_liste_olusturma.png) |

---

## 🛠️ Teknoloji Yığını

| Katman              | Paket                    | Versiyon | Açıklama                               |
| ------------------- | ------------------------ | -------- | -------------------------------------- |
| **Framework**       | Flutter                  | ≥ 3.0    | UI çatısı                              |
| **Dil**             | Dart                     | ≥ 3.0    | Null-safety tam destek                 |
| **State Yönetimi**  | `provider`               | ^6.1.2   | `ChangeNotifier` tabanlı reaktif state |
| **HTTP İstemcisi**  | `dio`                    | ^5.7.0   | Retry, timeout, hata yönetimi          |
| **Yerel Depolama**  | `shared_preferences`     | ^2.3.3   | Favoriler, listeler, tema tercihi      |
| **Görsel Önbellek** | `cached_network_image`   | ^3.4.1   | Ağ görseli önbellekleme                |
| **Video Oynatıcı**  | `youtube_player_flutter` | ^9.1.1   | YouTube fragman oynatma                |
| **URL Açma**        | `url_launcher`           | ^6.3.1   | Harici bağlantı açma                   |
| **Görsel Seçici**   | `image_picker`           | ^1.1.2   | Özel poster seçimi                     |
| **UUID**            | `uuid`                   | ^4.5.1   | Özel liste ID üretimi                  |
| **Çeviri**          | `translator`             | ^1.0.4+1 | Biyografi otomatik çevirisi            |
| **Dinamik Yazı**    | `auto_size_text`         | ^3.0.0   | Taşmayı önleyen otomatik boyutlandırma |

---

## 📂 Proje Yapısı

```
lib/
│
├── main.dart
│
├── models/
│   ├── movie.dart
│   ├── actor.dart
│   └── favorite_item.dart
│
├── providers/
│   └── user_preferences_provider.dart
│
├── services/
│   └── tmdb_service.dart
│
├── screens/
│   ├── home_screen.dart
│   ├── search_screen.dart
│   ├── discover_screen.dart
│   ├── favorites_screen.dart
│   ├── lists_screen.dart
│   ├── movie_detail_screen.dart
│   ├── actor_detail_screen.dart
│   ├── custom_list_detail_screen.dart
│   └── see_all_screen.dart
│
└── widgets/
    ├── movie_card.dart
    ├── movie_section.dart
    └── favorite_card.dart
```

---

## 🌐 API Referansı

Uygulama [TMDB API v3](https://developer.themoviedb.org/docs) kullanmaktadır. Tüm istekler `tr-TR` dil parametresiyle gönderilir. Türkçe içerik yoksa İngilizce endpoint'e fallback yapılır.

| Endpoint                        | Açıklama                           |
| ------------------------------- | ---------------------------------- |
| `/trending/{type}/day`          | Günlük trend filmler / diziler     |
| `/movie/popular`                | Popüler filmler                    |
| `/tv/popular`                   | Popüler diziler                    |
| `/movie/top_rated`              | En yüksek puanlı filmler           |
| `/tv/top_rated`                 | En yüksek puanlı diziler           |
| `/movie/now_playing`            | Vizyondaki filmler                 |
| `/movie/upcoming`               | Yakında çıkacak filmler            |
| `/tv/airing_today`              | Bugün yayınlanan diziler           |
| `/tv/on_the_air`                | Güncel diziler                     |
| `/search/multi`                 | Çoklu arama (film + dizi + oyuncu) |
| `/search/movie`                 | Film araması                       |
| `/search/tv`                    | Dizi araması                       |
| `/search/person`                | Oyuncu araması                     |
| `/{type}/{id}`                  | Film / dizi detayı                 |
| `/{type}/{id}/credits`          | Oyuncu ve ekip bilgisi             |
| `/{type}/{id}/videos`           | Fragman ve klipler                 |
| `/{type}/{id}/recommendations`  | TMDB tabanlı öneriler              |
| `/{type}/{id}/similar`          | Benzer içerikler                   |
| `/person/{id}`                  | Oyuncu profili                     |
| `/person/{id}/combined_credits` | Oyuncunun tüm yapımları            |
| `/genre/movie/list`             | Film türleri                       |
| `/genre/tv/list`                | Dizi türleri                       |
| `/discover/{type}`              | Türe göre içerik keşfi             |

### Hata Yönetimi

| HTTP Kodu    | Durum          | Uygulama Davranışı                          |
| ------------ | -------------- | ------------------------------------------- |
| 401          | `unauthorized` | "API anahtarı geçersiz" mesajı              |
| 404          | `notFound`     | "İçerik bulunamadı" mesajı                  |
| 429          | `rateLimited`  | Üstel geri çekilme (max 3 deneme)           |
| 5xx          | `serverError`  | "Sunucu hatası" mesajı                      |
| Bağlantı yok | `noInternet`   | "İnternet bağlantınızı kontrol edin" mesajı |

---

## 🔐 Güvenlik ve Gizlilik

### ✅ Doğru yapılan uygulamalar

| Konu                               | Durum                                                              |
| ---------------------------------- | ------------------------------------------------------------------ |
| API anahtarı kaynak kodda          | ✅ Yok — `--dart-define` ile build zamanında enjekte edilir        |
| Kullanıcı verisi dışarıya gönderme | ✅ Yok — veriler yalnızca cihazda `SharedPreferences`'a kaydedilir |
| Analytics / reklam / izleme SDK'sı | ✅ Yok                                                             |
| Sabit kodlanmış parola veya token  | ✅ Yok                                                             |
| `debugPrint` production sızıntısı  | ✅ Release modda otomatik olarak no-op'tur                         |

---

## ⚠️ Bilinen Kısıtlamalar

- **TMDB Görsel Sunucusu:** Yavaş bağlantılarda posterler geç yüklenir; `cached_network_image` tekrar yüklemeyi önler.
- **`combined_credits` Sayfalama:** Bu endpoint sayfalamayı desteklemez; sonsuz kaydırma bu ekranda sayfa > 1 için boş liste döndürerek durur.
- **Çeviri Kalitesi:** Otomatik biyografi çevirisi makine çevirisi kalitesindedir.
- **YouTube Oynatma:** `youtube_player_flutter` arka plan oynatmayı desteklemez.
- **iOS Simülatör:** Görsel seçici fiziksel cihaz veya iOS 17+ simülatör gerektirir.

---

## 🗺️ Yol Haritası

- [ ] Backend proxy ile API anahtarını istemciden tamamen kaldırmak
- [ ] `freezed` + `json_serializable` ile tip güvenli model katmanı
- [ ] `go_router` ile bildirimsel navigasyon
- [ ] Görsel depolamasını dosya sistemi tabanlı yapıya taşımak
- [ ] Resmi Cloud Translation API entegrasyonu
- [ ] Birim ve widget testleri
- [ ] Türe göre keşif ekranı
- [ ] İzlendi / İzlenmedi / Puan ver sistemi
- [ ] Ana ekran widget desteği

---

## 📄 Lisans

Bu proje kişisel / eğitim amaçlıdır. İçerikler ve görseller [TMDB](https://www.themoviedb.org) tarafından sağlanmaktadır. Bu ürün TMDB API'sini kullanmaktadır ancak TMDB tarafından onaylanmamış veya sertifikalandırılmamıştır.
