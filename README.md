# Kick Timer Overlay

OBS için özel olarak tasarlanmış, **Kick** yayıncılarına yönelik sadakat puanı ve sohbet mesajı ile tetiklenen süre eklemeli zamanlayıcı (Timer) overlay projesi.

## Özellikler
- **Tamamen Statik & Sunucusuz:** Sadece HTML, CSS (Tailwind) ve JavaScript ile çalışır. Sunucu (backend) maliyeti veya kurulumu gerektirmez. (GitHub Pages üzerinden tek tıkla barındırılabilir.)
- **Kolay Kurulum Paneli (Wizard):** Modern arayüzlü yapılandırma sayfası ile Kick kanal adını doğrulayabilir, renkleri, yazı tiplerini ve çerçeve özelliklerini canlı önizleme (Live Preview) ile ayarlayabilirsiniz.
- **Sohbet Dinleme (Pusher JS):** Kick'in kendi WebSockets altyapısı (Pusher) kullanılarak tüm "Global" etkinlikler ve sohbet akışı dinlenir.
- **Otomatik Süre Ekleme:** Belirttiğiniz sadakat ödülü (veya kelime) kullanıldığında sayaç otomatik olarak başlar veya mevcut süreye ekleme yapar. Ekleme anında görsel bir parlama efekti oluşur.
- **Dahili Ses Sistemi:** Gömülü base64 ses dosyaları sayesinde sayacın başlaması, süre eklenmesi ve sayacın bitişi anında sesli bildirim verir. Dış linklere bağımlı değildir.

## Nasıl Kullanılır?
1. `panel.html` dosyasını tarayıcınızda açın.
2. Yayıncı kanal adınızı, süreyi ve tetiklemek istediğiniz ödül/kelime adını girin.
3. Renk, font ve metin ayarlarınızı yapıp **Bağlantı Oluştur** butonuna tıklayın.
4. Oluşturulan linki kopyalayın.
5. **OBS Studio** (veya benzeri bir yayın yazılımı) programında yeni bir **Tarayıcı Kaynağı (Browser Source)** ekleyin.
6. Kopyaladığınız linki URL kısmına yapıştırın (Önerilen boyut: 800x300).
7. Kaynak özelliklerindeki **"Sesi OBS üzerinden kontrol et" (Control audio via OBS)** seçeneğini işaretlemeyi unutmayın!

## Kullanılan Teknolojiler
- HTML5 & CSS3
- Vanilla JavaScript
- Tailwind CSS (CDN)
- Pusher JS (Kick WebSocket altyapısı için)

## Lisans
Bu proje açık kaynaklı olup, istediğiniz gibi kullanıp geliştirebilirsiniz.
