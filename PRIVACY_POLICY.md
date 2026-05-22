# MatchXMatch — Gizlilik Politikası (Privacy Policy)

**Son güncelleme:** 22 Mayıs 2026
**Yürürlük tarihi:** 22 Mayıs 2026

---

## 1. Bu Politika Kim Hakkındadır?

Bu Gizlilik Politikası, **MatchXMatch** mobil uygulamasını ("Uygulama", "Hizmet") kullanan kişilerin ("kullanıcı", "siz") kişisel verilerinin nasıl toplandığını, kullanıldığını, saklandığını ve paylaşıldığını açıklar.

**Veri Sorumlusu (Data Controller):**
- **Geliştirici adı:** BAB Universe Creative
- **Konum:** Bologna, Italy
- **E-posta (gizlilik talepleri için):** matchmatchx@gmail.com
- **İletişim:** matchmatchx@gmail.com

> Uygulama, küresel olarak Google Play üzerinden dağıtılmaktadır. Türkiye'de KVKK, Avrupa Birliği'nde GDPR, Birleşik Krallık'ta UK GDPR ve diğer ülkelerde geçerli yerel veri koruma kanunlarına tabidir.

---

## 2. Topladığımız Veriler

Aşağıdaki kategorilerdeki kişisel verileri topluyoruz.

### 2.1 Hesap ve Kimlik Doğrulama Verileri

Uygulamaya kayıt olduğunuzda aşağıdaki bilgileri toplarız:

- **E-posta adresi** (zorunlu)
- **Şifre** — geri döndürülemez şekilde hashlenmiş olarak Supabase Authentication üzerinden saklanır; düz metin olarak hiçbir yerde tutulmaz
- **Kullanıcı adı** (benzersiz, en az 3 karakter)
- **Telefon numarası** — SMS OTP doğrulaması için (E.164 formatında normalize edilir)
- **Cinsiyet** — `male` veya `female` (eşleşme algoritması için zorunlu)
- **Doğum tarihi** — yaş doğrulaması (18+) ve eşleşme tercihleri için
- **Davet kodu** (varsa) — kim tarafından davet edildiğinizi kayıt eder
- **İlgi duyduğunuz cinsiyet** — `male`, `female`, `both` (isteğe bağlı)

### 2.2 Profil Verileri

Profilinizi oluşturduğunuzda ve düzenlediğinizde aşağıdaki bilgileri toplarız:

- **Profil fotoğrafı (avatar)** ve **6 adete kadar ek fotoğraf** — cihazınızın galerisinden yüklenir; Supabase Storage'da `avatars/{userId}/...` yolunda saklanır
- **Biyografi metni (bio)**
- **Şehir bilgisi** — manuel olarak girebilir veya konum izniyle GPS'ten otomatik tespit ettirebilirsiniz (yalnızca şehir adı saklanır; ham koordinatlar saklanmaz)
- **İlgi etiketleri (hashtag'ler)**
- **Eşleşme tercihleri** — yaş aralığı (min/max), ilgi duyulan cinsiyet
- **Sosyal medya bağlantıları** (isteğe bağlı) — Instagram, Facebook, Snapchat kullanıcı adları/linkleri
- **Tercih edilen diller** — uygulama varsayılan olarak `["tr"]` tutar
- **Davet kodunuz** — uygulama tarafından otomatik oluşturulur (8 karakterlik nanoid)

### 2.3 Konum Verisi

- Konum izni vermeniz halinde, **profilde şehir alanını otomatik doldurmak için** `expo-location` ile cihazınızın yaklaşık (Balanced accuracy) GPS koordinatlarını okuruz.
- Koordinatlar ters coğrafi kodlama (reverse geocoding) ile şehir adına çevrilir ve **yalnızca şehir bilgisi** veritabanımıza yazılır. Ham enlem/boylam veya hassas konum tutulmaz, paylaşılmaz.
- Konum izni isteğe bağlıdır; manuel olarak şehir yazarak Uygulamayı kullanabilirsiniz.
- Arka planda (background) konum izlemesi yapmıyoruz.

### 2.4 Cihaz ve Teknik Veriler

- **Push bildirim token'ı (Expo Push Token)** — eşleşme ve mesaj bildirimleri için
- **Cihaz bilgileri** (`expo-device`, `expo-application` üzerinden): cihaz modeli, işletim sistemi sürümü, uygulama sürümü — yalnızca hata ayıklama ve uyumluluk kontrolü amaçlı
- **IP adresi** — API isteklerinde otomatik olarak iletilir; rate limiting (kötüye kullanım önleme) ve güvenlik amacıyla kısa süreli loglarda tutulur
- **Bağlantı durumu** (`@react-native-community/netinfo`) — uygulamanın çalışması için cihaz hafızasında, sunucuya gönderilmeden
- **JWT oturum token'ı** — cihazınızda `expo-secure-store` üzerinde güvenli olarak saklanır

### 2.5 Aktivite ve Oyun Verileri

- **Lig puanı (score)** ve **kredi bakiyesi**
- **Kredi işlem geçmişi** — maç harcamaları, günlük ödüller, davet bonusları, oyun kazançları
- **Günlük giriş bilgisi** — son giriş tarihi, ardışık gün sayısı
- **Eşleşme kuyruğu durumu** — kuyrukta mısınız bilgisi
- **Eşleşme kayıtları** — eşleştiğiniz kullanıcılar, maç durumu, oyun skoru, mesaj sayaçları, beğen/geç kararları, terk bilgisi, rematch talepleri
- **Oyun oturumu kayıtları** — başlangıç/bitiş zamanı, soru sayısı, toplam puan

### 2.6 İletişim Verileri (Anonim Sohbet)

- **Sohbet mesajları** — her iki taraf 20'şer mesaj atana kadar profiller gizli kalır; mesajlar `messages` tablosunda `(gönderen ID, eşleşme ID, içerik, zaman damgası)` ile saklanır
- Mesaj içeriği uçtan uca şifreli **DEĞİLDİR**; sunucumuz mesajları okuyabilecek teknik kapasitedeyiz. Kötüye kullanım şikâyetleri ve yasal yükümlülüklerimiz için bu erişim gerekli olabilir
- Mesajlar maksimum 1000 karakter ile sınırlıdır

### 2.7 Güvenlik ve Şikâyet Verileri

- **Kullanıcı şikâyetleri** (`user_reports` tablosu) — kimi, kim, hangi eşleşmede şikâyet ettiğiniz
- **Karma puanı** — şikâyetlere ve davranışınıza bağlı dahili güven skoru
- **Geri bildirimler** (`feedback` tablosu) — hata bildirimi/öneri olarak gönderdiğiniz metinler

### 2.8 Otomatik Toplanan Veriler

- **Loglar** — sunucu hataları, API istek metaverisi (endpoint, durum kodu, zaman damgası)
- **Önbellek verisi** (Redis) — OTP doğrulama kodları (5 dk), oyun durumu (oturum sırasında), rate limiting sayaçları — bunlar geçicidir ve TTL süresiyle otomatik silinir

---

## 3. Topladığımız Veri Türlerini KULLANMADIĞIMIZ Şeyler

Şunları **toplamıyoruz veya kullanmıyoruz**:

- Reklam izleme tanımlayıcıları (advertising ID), üçüncü taraf reklam ağları
- Cihaz mikrofonu veya kamera (kullanıcı doğrudan tetiklemediği sürece — bkz. fotoğraf yükleme)
- Sağlık, biyometrik veya finansal hesap verileri
- Rehber/kişiler listesi
- SMS/çağrı geçmişi
- Hassas (sub-city) konum verisi

---

## 4. Verileri Hangi Amaçlarla Kullanırız?

Kişisel verilerinizi yalnızca aşağıdaki amaçlar için işleriz:

| Amaç | Veri kategorisi | Hukuki dayanak |
|------|-----------------|---------------|
| Hesap oluşturma ve kimlik doğrulama | E-posta, şifre, telefon, OTP | Sözleşmenin ifası |
| Eşleştirme algoritması | Cinsiyet, yaş, lig puanı, tercihler, şehir | Sözleşmenin ifası |
| Profil görüntüleme (reveal sonrası) | Fotoğraflar, bio, sosyal linkler, kullanıcı adı | Sözleşmenin ifası |
| Anonim sohbet | Mesajlar, gönderen/alıcı kimliği | Sözleşmenin ifası |
| Kredi ve lig sistemi | Skor, kredi, işlem geçmişi | Sözleşmenin ifası |
| Push bildirimleri | Expo push token | Açık rıza (izninizle) |
| Kötüye kullanım önleme | Şikâyetler, karma, IP, rate limiting | Meşru menfaat |
| OTP/SMS gönderimi | Telefon numarası | Sözleşmenin ifası |
| Yasal yükümlülükler | Tüm veriler (gerekirse) | Hukuki yükümlülük |
| Hata ayıklama ve iyileştirme | Cihaz, log, hata mesajları | Meşru menfaat |

Verilerinizi **otomatik karar verme** veya **profilleme** süreçlerinde, eşleştirme algoritması ve lig sıralaması dışında kullanmıyoruz. Bu süreçlerin hukuki ya da benzer ölçüde önemli sonuçları yoktur.

---

## 5. Verileri Kimlerle Paylaşıyoruz? (Üçüncü Taraf Hizmet Sağlayıcılar)

Verilerinizi satmıyor, kiralamıyor veya pazarlama amacıyla paylaşmıyoruz. Aşağıdaki hizmet sağlayıcılarla, yalnızca Uygulamanın çalışması için gerekli ölçüde paylaşıyoruz:

| Hizmet | Sağlayıcı | Veri | Konum |
|--------|-----------|------|-------|
| Veritabanı, Auth, Storage | **Supabase** (Supabase Inc.) | Tüm yapısal veriler ve fotoğraflar | AB (eu-central-1) |
| Önbellek / oyun durumu | **Redis** (Railway üzerinde barındırılır) | Geçici OTP, oturum, rate limit | AB (Railway EU West, Amsterdam) |
| Push bildirim altyapısı | **Expo (Expo Push Service)** | Push token, bildirim içeriği | ABD |
| Backend hosting | **Railway** | API trafiği, IP, loglar | AB (EU West, Amsterdam) |
| SMS OTP gönderimi | Şu an entegre değil — test aşamasında OTP kodları üçüncü taraf bir SMS sağlayıcısı üzerinden iletilmemektedir. Üretim sürümüne geçmeden önce bir sağlayıcı (örn. Twilio) entegre edilecek ve bu politika güncellenecektir. | Telefon numarası, OTP kodu | — |

**Profil görünürlüğü diğer kullanıcılar:** İki taraf da 20 mesaj atıp reveal aşamasına geçtikten sonra fotoğraflarınız, kullanıcı adınız, biyografiniz, şehir, ilgi etiketleri ve isteğe bağlı sosyal medya bağlantılarınız eşleştiğiniz kullanıcıya gösterilir. Reveal'a kadar profiliniz tamamen anonimdir.

**Yasal taleplerle paylaşım:** Mahkeme kararı, savcılık talebi veya geçerli yasal süreçler kapsamında, yasalarla zorunlu olduğumuz ölçüde kullanıcı verilerini yetkili mercilerle paylaşabiliriz.

---

## 6. Veri Saklama Süreleri

| Veri | Saklama Süresi |
|------|----------------|
| Hesap profili (aktif hesap) | Hesabınız aktif olduğu sürece |
| Hesap silindiğinde profil | 30 gün içinde tüm kişisel bağlantılar silinir |
| Sohbet mesajları | Eşleşme silinene veya hesabınız kapanana kadar |
| Kredi işlem geçmişi | 12 ay (muhasebe/şeffaflık) |
| Sunucu logları | 30 gün |
| OTP kodu | 5 dakika (sonra otomatik silinir) |
| Oyun oturumu (Redis) | Oturum süresi (genellikle <30 dk) |
| Şikâyet kayıtları | Aktif hesap süresi boyunca + güvenlik amacıyla anonimleştirilerek 12 ay |
| Push token | Bildirimi devre dışı bırakana veya hesabınız kapanana kadar |

---

## 7. Veri Güvenliği

Verilerinizin güvenliği için aldığımız önlemler:

- **Şifreleme:** Tüm istemci–sunucu trafiği HTTPS/TLS ile şifrelenir. Veritabanı bağlantısı SSL üzerinden yapılır
- **Şifre güvenliği:** Şifreler Supabase Auth tarafından bcrypt benzeri tek yönlü algoritmayla hashlenir; biz dahil kimse düz metni göremez
- **Cihaz tarafı:** JWT oturum token'ları cihazda `expo-secure-store` (iOS Keychain / Android Keystore) ile şifrelenir
- **Erişim kontrolü:** Veritabanında Row-Level Security (RLS) politikaları aktiftir; API yalnızca yetkili işlemler için service role kullanır
- **Rate limiting:** OTP, kayıt ve giriş endpoint'lerinde IP/telefon bazlı hız sınırlama
- **Yetkilendirme:** Tüm korumalı endpoint'ler JWT doğrulamasından geçer (Supabase JWT)
- **Helmet:** HTTP güvenlik başlıkları aktiftir

Hiçbir sistem %100 güvenli değildir; bir veri ihlali durumunda yasal yükümlülüklerimiz çerçevesinde sizi ve yetkili otoriteleri makul süre içinde bilgilendiririz.

---

## 8. Çocuklara Yönelik Kullanım

Uygulama **18 yaşından küçük kişiler için tasarlanmamıştır**. Kayıt sırasında doğum tarihinizi sorar ve 18 yaş altı kullanıcı tespit edersek hesabı oluşturmayız veya tespit edildiği anda sileriz. 18 yaş altı bir kullanıcının veri verdiğini fark ederseniz lütfen matchmatchx@gmail.com adresine bildirin.

---

## 9. Haklarınız

Aşağıdaki haklara sahipsiniz (yerel kanunlara göre kapsam değişebilir):

- **Erişim hakkı:** Hakkınızda tuttuğumuz verilerin kopyasını isteyebilirsiniz
- **Düzeltme hakkı:** Yanlış/eksik verileri düzeltmemizi isteyebilirsiniz (çoğu alan Uygulama içinden zaten düzenlenebilir)
- **Silme hakkı ("unutulma hakkı"):** Hesabınızı ve verilerinizi silmemizi isteyebilirsiniz
- **İşleme itiraz hakkı:** Belirli işleme amaçlarına itiraz edebilirsiniz
- **Veri taşınabilirliği:** Verilerinizi yapısal, makine tarafından okunabilir formatta isteyebilirsiniz
- **Rıza geri çekme:** Rıza ile dayandığımız işlemler (örn. push bildirimleri) için izninizi geri alabilirsiniz
- **Şikâyet hakkı:** Bulunduğunuz ülkenin veri koruma otoritesine şikâyet edebilirsiniz (Türkiye'de KVKK, AB'de yerel DPA)

### Hesap Silme

Hesabınızı silmek için:
1. Uygulama içinden **Ayarlar → Hesabımı Sil** seçeneğini kullanın, **veya**
2. matchmatchx@gmail.com adresine kayıtlı e-postanızdan talep gönderin.

Talebiniz alındıktan sonra 30 gün içinde verileriniz silinir (yasal saklama zorunluluğu olan bazı veriler — örn. kredi/işlem kayıtları — anonimleştirilerek tutulabilir).

---

## 10. Uluslararası Veri Aktarımı

Verileriniz aşağıdaki bölgelerde işlenebilir:

- Supabase: **AB (Frankfurt / eu-central-1)**
- Expo Push Service: **ABD**
- Backend sunucumuz: AB (Railway EU West, Amsterdam)

ABD'ye aktarımlar, Standart Sözleşme Maddeleri (SCC) veya eşdeğer mekanizmalar kapsamında yapılır.

---

## 11. Üçüncü Taraf Bağlantılar

Profilinizde paylaştığınız Instagram/Facebook/Snapchat bağlantıları, eşleştiğiniz kullanıcı tarafından açıldığında ilgili üçüncü taraf platformuna yönlendirir. Bu platformların kendi gizlilik politikaları geçerlidir; biz onların veri uygulamalarından sorumlu değiliz.

---

## 12. Çerezler ve Benzer Teknolojiler

Mobil uygulama klasik anlamda çerez kullanmaz. Yerel depolama için şunları kullanır:

- `expo-secure-store` — JWT token (şifreli)
- `@react-native-async-storage/async-storage` — uygulama içi tercihler
- `expo-sqlite` — yerel önbellek (offline destek için)

---

## 13. Politika Değişiklikleri

Bu politikayı zaman zaman güncelleyebiliriz. Önemli değişikliklerde:
- Uygulama içinde bildirim göndeririz
- "Son güncelleme" tarihini en üstte değiştiririz
- Önemli kategori eklemelerinde tekrar rıza isteyebiliriz

---

## 14. İletişim

Gizlilik soruları, hak talepleri veya şikâyetler için:

- **E-posta:** matchmatchx@gmail.com
- **Konum:** Bologna, Italy
- **Veri Koruma Sorumlusu (DPO):** Atanmamıştır (şahıs yayıncı için zorunlu değildir).

---

## 15. Google Play Data Safety (Bilgilendirme)

Bu politika, Google Play Console > **App content > Data safety** formunda beyan ettiğimiz veri toplama davranışlarını yansıtır. Beyanımıza göre:

- Veri **toplanır**: Hesap, kişisel kimlik, fotoğraflar, yaklaşık konum, mesajlar, uygulama aktivitesi, cihaz veya diğer kimlikler
- Veri **paylaşılır**: Üçüncü taraf hizmet sağlayıcılarla (yukarıda Bölüm 5'te listelenmiştir)
- Veri **şifrelenir**: İletim sırasında (HTTPS/TLS)
- Veri **silinebilir**: Kullanıcı talebiyle (Bölüm 9)

---

*Bu dokümanın resmi ve bağlayıcı sürümü İngilizce'dir. Türkçe sürüm yalnızca kolaylık amacıyla sağlanmıştır; çeviriler arasında herhangi bir çelişki olması durumunda İngilizce metin esas alınır.*
