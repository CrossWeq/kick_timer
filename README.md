# Kick Timer Overlay

🔗 **Kurulum linki:** https://crossweq.github.io/kick_timer/

OBS için özel olarak tasarlanmış, **Kick** yayıncılarına yönelik sohbet komutları (örn: `!sus`) ve sadakat ödülleri ile tetiklenen süre eklemeli zamanlayıcı (Timer) overlay projesi.

## Özellikler
- **Kolay Kurulum Paneli (index.html):** Modern arayüzlü yapılandırma sayfası ile Kick kanal adınızı doğrulayabilir; yetkili kişileri, tetikleyici komutu, renkleri, fontları, saydamlık ve çerçeve özelliklerini canlı önizleme (Live Preview) ile ayarlayabilirsiniz.
- **Sohbet Komutu ile Kontrol (Pusher JS):** Cloudflare Worker köprüsü ve Kick resmi webhook altyapısı sayesinde sadece izin verdiğiniz kişilerin yazdığı `!` komutları işlenir.
- **✨ Dinamik Süre Ekleme (Örn: `!sus 20` / `!sus 12`):** Komuttan sonra boşluk bırakıp bir sayı yazarak (örn: `!sus 20` veya `!sus 12`) tek seferde doğrudan belirtilen dakika kadar süre ekleyebilirsiniz. Sayı yazılmazsa panelde ayarlanan varsayılan süre eklenir.
- **Botrix & Sadakat Puanı Uyumu:** Kanal puanı hediyeleriyle tetikleme yapılabilir (izleyici ödülü aldığında Botrix chate komutu atar, sayaç otomatik başlar). Farklı puanlar için farklı süreler (örn: `!sus 5`, `!sus 20`) tanımlanabilir.
- **Otomatik Süre Ekleme ve Parlama Efekti:** İzin verilen bir kişi komutu yazdığında mevcut süreye ekleme yapılır ve sayaç belirlediğiniz renkte parlar.
- **Sesli Uyarı Sistemi:** Sayaç süresi tamamen bittiğinde otomatik olarak uyarıcı bir zil/bip sesi çalar.

---

## 🚀 Kick Timer Nedir & Nasıl Kurulur?

### 1. Kanal Doğrulaması
Kick kullanıcı adınızı girin. Sistem kanalınızı başarıyla doğruladıktan sonra **Devam Et** butonuna tıklayarak sonraki aşamaya geçin.

### 2. Komut ve Yetki Ayarları
Sayacı yönetecek komutları ve bu komutları kimlerin kullanabileceğini belirleyin:
- **Yetkili Kişiler:** Chate komut yazarak süreye ekleme yapabilecek kişileri seçin.  
  *(Öneri: Güvenlik için sadece yayıncının kendisini ve botrix'i yetkilendirmeniz tavsiye edilir. Gerekirse güvenilir moderatörlerinizi de ekleyebilirsiniz.)*
- **Tetikleyici Kelime:** Sayacı çalıştıracak komutu belirleyin *(Varsayılan olarak `!sus` şeklindedir, isteğinize göre değiştirebilirsiniz)*.
- **Varsayılan Eklenecek Süre (Dakika):** Komut sade yazıldığında sayaca eklenecek süredir.
- **Dinamik Süre Ekleme (Örn: `!sus 20` / `!sus 12`):** Komuttan sonra boşluk bırakıp herhangi bir sayı yazarak istenen dakika doğrudan eklenebilir:
  - `!sus` ➔ Panelde belirlediğiniz varsayılan süre (örn: 1 dakika) eklenir.
  - `!sus 20` ➔ Sayaca doğrudan **20 dakika** eklenir.
  - `!sus 12` ➔ Sayaca doğrudan **12 dakika** eklenir.  
Ayarları tamamladıktan sonra **Devam Et** butonuna tıklayın.

### 3. Tasarım Ayarları
Sayacınızın yayındaki görünümünü özelleştirin:
- **Sayaç Üstü Metni:** Sayacın hemen üzerinde görünecek bilgilendirme yazısını belirleyin (Örn: *Konuşma yasağının bitmesine*).
- **Görünüm:** Font (yazı tipi), renk ve saydamlık (transparanlık) ayarlarını temanıza göre yapın.
- **Çerçeve (Stroke):** Yazıların daha okunaklı olması için metin dışına siyah çerçeve ekleme seçeneğini açıp kapatabilirsiniz.  
Tasarımınız hazır olduğunda **Bağlantı Oluştur** butonuna tıklayın ve ekranda beliren linki kopyalayın.

### 4. OBS'e Ekleme
1. Kopyaladığınız bağlantıyı OBS'te yeni bir **Tarayıcı (Browser)** kaynağı oluşturarak URL kısmına yapıştırın.
2. **Önerilen Boyutlar:** Genişlik 800, Yükseklik 300 *(Zorunlu değildir, sahnenize göre değiştirebilirsiniz)*.
3. ⚠️ **Çoklu Sahne Kullanımı (Önemli):** Zamanlayıcıyı OBS'te birden fazla sahnede kullanacaksanız, sahneler arası geçiş yaparken sayacın sıfırlanmaması ve sürenin kesintisiz akması için diğer sahnelere yeni kaynak açmak yerine her zaman **"Var Olanı Ekle" (Add Existing)** seçeneği ile tek bir kaynak olarak ekleyin.
4. ⚠️ **ÖNEMLİ SES AYARLARI:**
   - Kaynağı eklerken **"Sesi OBS üzerinden kontrol et" (Control audio via OBS)** seçeneğini **KESİNLİKLE** işaretleyin.
   - Ardından OBS **Ses Karıştırıcısı** panelinde bu kaynağın yanındaki **Kulaklık sembolünü açık** (Ses İzleme) durumuna getirin (veya Gelişmiş Ses Özellikleri'nden *"İzleme ve Çıkış"* seçin). Bu sayede süre bittiğinde çalacak olan alarm sesinden siz de anında haberdar olabilirsiniz.

### 5. Botrix ile Sadakat Puanı Entegrasyonu
*(Sadakat ödülleri ile otomatik çalıştırmak isteyenler için)*  
Sayacınızı izleyicilerin sadakat puanı (kanal puanı) ile aldıkları bir hediye üzerinden otomatik tetiklemek için:
1. **Botrix paneline** gidin ve **Sadakat (Loyalty)** sekmesini açın.
2. Kick sadakat puanları kısmından istediğiniz ödülü seçin veya sayaca özel yeni bir ödül oluşturun.
3. Ödül ayarlarına girerek, bu ödül kullanıldığında Botrix'in chate sizin belirlediğiniz komutu (örn: `!sus`, `!sus 5` veya `!sus 20`) sohbet mesajı olarak yazmasını sağlayın. Bu sayede farklı kanal puanı bedelleri için farklı süreli ödüller tanımlayabilirsiniz.
4. **İpucu:** Sayacın başladığını yayın sırasında anında fark etmek için, aynı ödülün Botrix ayarlarına uyarıcı bir ses efekti de ekleyebilirsiniz.

---

## 💻 Geliştirici / Developer
Developed with ❤️ by **CrossWeq**

İletişim / Contact: [crosweq204@gmail.com](mailto:crosweq204@gmail.com)

---

## Kullanılan Teknolojiler
- HTML5 & CSS3
- Vanilla JavaScript
- Tailwind CSS (CDN)
- Pusher JS & Cloudflare Worker (Kick Resmi API Webhook Entegrasyonu)
- Google Fonts

## Lisans
Bu proje açık kaynaklı olup, istediğiniz gibi kullanıp geliştirebilirsiniz.
