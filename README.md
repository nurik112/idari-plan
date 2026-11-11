# İdari Plan — GitHub Pages (sunucusuz, tamamen ücretsiz)

Tek dosya: `index.html`. Sunucu yok. Veriler **sizin Google Drive'ınızda** `idari-plan.json` dosyasında tutulur.
Okul ağı `github.io` adresini engellemez, site her zaman açık, hiçbir ücret yok.

## Nasıl çalışır / güvenlik
- Sayfa herkese açıktır (kodu görünür) **ama veriniz değildir.**
- Uygulama yalnızca `drive.file` izni kullanır: her hesap **kendi** Drive'ındaki dosyayı görür.
- Başkası sitenize girip kendi Google hesabıyla giriş yaparsa **kendi boş sürümünü** görür, sizin işlerinizi değil.
- Sizin verinizi görmenin tek yolu sizin Google hesabınızla giriş yapmaktır.
- İsterseniz "Bu hesaba kilitle" ile tarayıcıyı yalnızca kendi hesabınıza bağlayabilirsiniz (ayarlardan).

---

## Kurulum (bir kez, ~10 dk)

### 1. GitHub'a yükleyin
1. [github.com](https://github.com) → hesap açın / giriş yapın
2. Sağ üst **+ → New repository** → isim: `idari-plan` → **Public** → **Create repository**
3. Açılan sayfada **uploading an existing file** bağlantısına tıklayın
4. `index.html` dosyasını sürükleyip bırakın → **Commit changes**

### 2. GitHub Pages'i açın
1. Repo → **Settings → Pages**
2. **Source:** "Deploy from a branch" → **Branch:** `main` → klasör `/ (root)` → **Save**
3. 1-2 dakika sonra adresiniz hazır olur:
   `https://KULLANICIADINIZ.github.io/idari-plan/`

### 3. Google ayarı
Daha önce OAuth istemcisi oluşturduysanız **yenisini açmayın**, sadece adres ekleyin:

1. [console.cloud.google.com](https://console.cloud.google.com) → projeniz
2. **APIs & Services → Credentials** → OAuth istemcinize tıklayın (Web application)
3. **Authorized JavaScript origins → Add URI** → elle yazın (yapıştırmayın, boşluk hatası olur):
   ```
   https://KULLANICIADINIZ.github.io
   ```
   > Sadece bu kısım — sonunda `/` veya `/idari-plan` **yok**. Yalnızca site kök adresi.
4. **Save**
5. (Gerekiyorsa) **APIs & Services → Library → Google Drive API → Enable**
6. (Gerekiyorsa) **OAuth consent screen → Test users →** kendi e-postanızı ekleyin

> Client Secret artık **gerekmiyor** — bu sürüm tarayıcıda çalışıyor, gizli anahtar kullanmıyor.

### 4. İlk açılış
1. `https://KULLANICIADINIZ.github.io/idari-plan/` adresini açın
2. "İlk kurulum" kutusuna **Client ID**'nizi yapıştırın → **Kaydet ve başla**
   (Client ID, Google Console'daki istemci sayfasında yazar; `...apps.googleusercontent.com` ile biter.)
3. **Google ile giriş yap** → hesabınızı seçin → Drive iznini onaylayın
4. Hazır. Artık her değişiklik otomatik olarak Drive'a kaydedilir.

Telefon ve bilgisayardan aynı adrese girip aynı hesapla oturum açınca aynı veriyi görürsünüz.

---

## Günlük kullanım
- **+ Yeni iş** veya bir güne çift tıkla
- **Geçen yıldan aktar:** tekrar eden işleri bir yıl ileri taşır
- **Excel: kaydet / içe aktar:** yedek al, eski veriyi yükle, telefon takvimine (.ics) aktar
- **Sürüm geçmişi:** Drive eski sürümleri saklar; ayarlardan geri dönebilirsiniz
- Üstteki hesap satırına (ya da "Excel" linkine) tıklayınca ayarlar açılır

## Güncelleme
GitHub'da `index.html` dosyasını yenisiyle değiştirin (repo → dosyaya tıkla → kalem simgesi → içeriği yapıştır → Commit). Birkaç dakikada yayınlanır.

## Sorun giderme
- **Giriş penceresi açılmıyor:** açılır pencere engelini kaldırın.
- **"origin_mismatch":** Authorized JavaScript origins'teki adres `https://KULLANICIADINIZ.github.io` ile birebir aynı olmalı (sonda `/` yok). Yeni eklediyseniz 5 dk bekleyin.
- **"access blocked / OAuth politikası":** consent screen'de kendi e-postanızı Test users'a ekleyin.
- **Veri gelmiyor:** aynı Google hesabıyla giriş yaptığınızdan emin olun.
