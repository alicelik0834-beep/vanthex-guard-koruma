# Discord Giveaway Bot

Bu gelişmiş Discord çekiliş botu, anlık katılımcı sayısı ve şans gösterimi ile çekilişleri yönetir.

## Özellikler
- Çekiliş başlatma komutu: `!çekiliş <ödül> <süre> [kaçkişi]`
- Gizli Çekiliş Form Komutu: `!çekiliş1` (Modal form açar, **sadece bot sahibi kullanabilir**)
- Katıl/Ayrıl butonları
- Anlık katılımcı sayısı ve şans güncellemesi
- Otomatik kazanan seçimi
- Mesaj silme komutu: `!sil <sayı>` (1-100 arası mesaj siler)
- Kanal nuke komutu: `!nuke` (kanalı yeniden oluşturarak tüm mesajları siler)
- Otomatik cevap sistemi: Tetikleyici mesajlara otomatik yanıt
- Otomatik cevap listesi: `!otocevaplist` (ekle/sil butonları ile)
- Spam koruması: 5 saniye içinde 5+ mesaj gönderenleri engeller
- Otomatik rol: `!otorol` (yeni üyelere otomatik rol verme, yönetici gerekli)
- Ceza bildirimi: Mute veya ban yendiğinde DM ile itiraz bilgisi gönderir
- Spam ayarları: `!spam` (menü ile aç/kapat, susturma ayarı)
- Ping komutu: `!ping` (botun pingini gösterir)- Yardım komutu: `!yardım` (komut listesi ve kullanım)
- Koruma ayarları: `!koruma` (anti-raid korumaları, yönetici gerekli)- Unmute komutu: `!unmute @kullanıcı`

## Kurulum
1. `.env` dosyasına bot tokenınızı ve Groq anahtarınızı ekleyin:
   - `DISCORD_TOKEN=your_token_here`
   - `GROQ_API_KEY=your_groq_key_here`
   - `hsan_AI_ENABLED=true`
   - İsteğe bağlı model: `ELECTUS_GROQ_MODEL=llama-3.3-70b-versatile`
2. Bağımlılıkları yükleyin: `npm install`
3. Botu başlatın: `npm start`

### Müzik için ek notlar
- `!play <URL>` komutu sadece doğrudan URL alır ve oynatır.
- Proje `ffmpeg-static` kullanır; ancak sisteminizde `yt-dlp` yüklü ve PATH'e eklenmiş olmalı. Windows için `yt-dlp` kurup PATH'e ekleyin veya uygun yolu sağlayın.
- Eğer `yt-dlp` yüklü değilse, `!play` çalıştırıldığında hata mesajı alırsınız.

## Kullanım
- Sunucu mesajı ve slash komutlarını yalnızca `index.js` içindeki `OWNER_IDS` listesinde bulunan kişiler kullanabilir.
- Çekiliş başlatmak için: `!çekiliş Discord Nitro 1h 1kişi`
- Gizli form ile çekiliş kurmak için (BOT SAHİBİ SADECE): `!çekiliş1` (Modal açılır, ödül, süre, kazanan sayısı ve kazanacak kişiler yazıp gönderebilirsiniz)
- Mesaj silmek için: `!sil 10` (son 10 mesajı siler)
- Kanalı nuke etmek için: `!nuke` (kanalı yeniden oluşturur)
- Otomatik cevapları listelemek için: `!otocevaplist`
- Spam ayarlarını yönetmek için: `!spam`
- Ping için: `!ping`
- Yardım için: `!yardım`
- Koruma ayarları için: `!koruma`
- Mute için: `!mute @user spam 5d`
- Davet istatistikleri için: `!davet @user`
- Otomatik rol için: `!otorol`
- Unmute için: `!unmute @user`
- Minecraft AFK panelini açmak için: `!mcafkpanel` (yalnızca `OWNER_IDS` listesindeki bot sahipleri kullanabilir)

### Özel ses kanalları
- Sunucu yöneticisi `!özelseskur` komutuyla sistemi kurar.
- Üyeler **🔊 özel ses oluştur** kanalına girince kişisel ses kanalları oluşturulur. Kanalları herkes görebilir, ancak yalnızca sahibi ve izin verdiği kişiler girebilir.
- Kanal sahibinin özel kontrol mesajındaki **Kişiye Giriş İzni Ver** düğmesiyle sunucudan bir üyeye erişim verilebilir; **Giriş İznini Kaldır** düğmesiyle erişim geri alınabilir.

### Minecraft AFK paneli
- Botun **Message Content Intent** izni Discord Developer Portal'da açık olmalıdır.
- İstersen panel kanalını `MCAFK_PANEL_CHANNEL_ID` ortam değişkeniyle veya `config.json` içindeki `panelChannelId` ile sınırlandırabilirsin. Ayarlanmazsa komut herhangi bir kanalda çalışır.
- `!mcafkpanel` komutu da yalnızca bot sahiplerine açıktır.
- Paneldeki **Oyun Sohbeti** düğmesi son 12 oyun mesajını gösterir. **Sohbet Kanalı** düğmesiyle oyun içi mesajların aktarılacağı metin kanalını ayarlayabilir veya aktarımı kapatabilirsin; ayar `config.json` dosyasına kaydedilir. Botun seçilen kanalda kanalı görme ve mesaj gönderme izinleri olmalıdır.