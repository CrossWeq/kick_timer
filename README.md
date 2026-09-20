# Kick Timer Overlay

OBS için özel olarak tasarlanmış, **Kick** yayıncılarına yönelik sohbet komutları (örn: !sus) ile tetiklenen süre eklemeli zamanlayıcı (Timer) overlay projesi.

## Özellikler
- **Tamamen Statik & Sunucusuz:** Sadece HTML, CSS (Tailwind) ve JavaScript ile çalışır. Sunucu (backend) maliyeti veya kurulumu gerektirmez. (GitHub Pages üzerinden tek tıkla barındırılabilir.)
- **Kolay Kurulum Paneli (index.html):** Modern arayüzlü yapılandırma sayfası ile Kick kanal adınızı doğrulayabilir, renkleri, yazılı fontlarını, saydamlık ve çerçeve özelliklerini canlı önizleme (Live Preview) ile ayarlayabilirsiniz.
- **Sohbet Komutu ile Kontrol (Pusher JS):** Kick'in kendi WebSockets altyapısı (Pusher) kullanılarak sohbet mesajları dinlenir. Sadece belirlediğiniz kullanıcıların (Örn: botunuz veya yetkilileriniz) yazdığı tetikleyici komut (!sus vb.) dikkate alınarak sayaç otomatik başlar.
- **Otomatik Süre Ekleme ve Parlama Efekti:** İzin verilen bir kişi komutu yazdığında mevcut süreye ekleme yapılır ve sayaç belirlediğiniz renkte parlar.
- **Sesli Uyarı Sistemi:** Sayaç süresi tamamen bittiğinde otomatik olarak uyarıcı bir zil/bip sesi çalar.

## Nasıl Kullanılır?
1. index.html sayfasını tarayıcınızda açın.
2. Yayıncı kanal adınızı girin ve "Kontrol Et" ile doğrulayın.
3. Tetiklemek istediğiniz komutu (Örn: !sus), bu komutu kullanabilecek kişilerin kullanıcı adlarını (Örn: botrix, yayinci_adi) ve eklenecek süreyi belirleyin.
4. Tasarım bölümünden zevkinize göre renk, font, transparanlık ve metin ayarlarınızı yapıp **Bağlantı Oluştur** butonuna tıklayın.
5. Oluşturulan linki kopyalayın.
6. **OBS Studio** (veya benzeri bir yayın yazılımı) programında yeni bir **Tarayıcı Kaynağı (Browser Source)** ekleyin.
7. Kopyaladığınız linki URL kısmına yapıştırın (Önerilen boyut: 800x300 veya 1000x400).
8. Kaynak özelliklerindeki **"Sesi OBS üzerinden kontrol et" (Control audio via OBS)** seçeneğini işaretlemeyi unutmayın!

## Kullanılan Teknolojiler
- HTML5 & CSS3
- Vanilla JavaScript
- Tailwind CSS (CDN)
- Pusher JS (Kick WebSocket altyapısı için)
- Google Fonts

## Lisans
Bu proje açık kaynaklı olup, istediğiniz gibi kullanıp geliştirebilirsiniz.
