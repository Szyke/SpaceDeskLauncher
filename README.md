# SpaceDesk Launcher

Android tableti profesyonel bir ikinci ekran (SpaceDesk) terminaline dönüştüren,
tamamen Java ile yazılmış, Material Design 3 tabanlı bir Android Launcher (HOME) uygulaması.

## Projeyi Açma

1. Android Studio'yu aç → **Open** → bu klasörü (`SpaceDesk Launcher`) seç.
2. Gradle senkronizasyonunun bitmesini bekle (ilk açılışta Gradle 8.4 wrapper'ı internetten indirilecektir).
3. Bir tablet/emülatöre (min SDK 26 / Android 8.0) çalıştır.
4. Uygulama kurulduktan sonra tablet, cihaz ayarlarından **"Varsayılan Uygulamalar" → "Ana Ekran"**
   bölümünden SpaceDesk Launcher'ı varsayılan launcher olarak seçmelidir
   (uygulama içindeki Ayarlar ekranındaki **"Varsayılan Launcher Yap"** butonu da doğrudan bu ekrana yönlendirir).

   https://mega.nz/file/62hHhBwA#99NcyTUdOha4dzSfdSJ6igQRJUh7_c4F7YKt2xBFcmc

## Proje Yapısı

```
app/src/main/java/com/vero/displayos/
├── MainActivity.java        → Ana launcher ekranı (HOME)
├── StatsActivity.java       → Kullanım istatistikleri
├── SettingsActivity.java    → Ayarlar
├── AboutActivity.java       → Hakkında
├── core/                    → Sabitler, loglama, tercihler, istatistik hesaplama, zaman biçimlendirme
├── spacedesk/                → SpaceDesk paketiyle ilgili tüm işlemler (başlatma, sürüm bilgisi, Play Store yönlendirme)
└── receivers/                → USB/pil durumu ve cihaz açılış (boot) alıcıları
```

## Önemli Notlar

- **SpaceDesk paket adı:** `ph.spacedesk.beta` (tüm başlatma/tespit işlemleri `SpaceDeskManager` sınıfında).
- **USB tespiti:** Android, "bir bilgisayara USB ile bağlı" durumunu doğrudan bildiren bir sistem yayını sunmaz.
  Bu proje, endüstri standardı olan `BatteryManager.BATTERY_PLUGGED_USB` sinyalini kullanır
  (bkz. `UsbStateReceiver.java` içindeki yorum).
- **"SpaceDesk çalışıyor mu" tespiti:** Android güvenlik politikaları gereği bir uygulama, başka bir
  uygulamanın o an ön planda olup olmadığını doğrudan sorgulayamaz. Bu nedenle "bağlantı süresi",
  launcher'ın ön plandan ayrılıp tekrar ön plana dönmesi aralığı olarak yaklaşık hesaplanır
  (bkz. `UsageTracker.java` içindeki yorum). Bu, bu tür ikinci-ekran uygulamalarında yaygın kullanılan bir yöntemdir.
- **Güncelleme kontrolü:** SpaceDesk için resmi/genel bir sürüm API'si bulunmadığından,
  uygulama içinde "Güncelleme durumu doğrulanamıyor" mesajı gösterilir (spesifikasyona uygun olarak).
- İzinler minimumdur: sadece `RECEIVE_BOOT_COMPLETED` (otomatik SpaceDesk başlatma ayarı için) ve `VIBRATE`
  (dokunma geri bildirimi için). Reklam, takip sistemi veya arka planda veri toplama yoktur.

## Eksik / Sizin Tamamlamanız Gerekenler

- Gerçek bir launcher ikonu (şu an basit bir vektör "V" harfi kullanılmıştır, isterseniz kendi logonuzla değiştirin).
- `values-en/strings.xml` eklenirse dil seçici gerçek çeviriyi de değiştirebilir hale gelir
  (şu an sadece bir tercih olarak saklanıyor, arayüz metinleri hâlâ Türkçe).
