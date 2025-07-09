# Otomatik Hata Takip ve Bildirim Sistemi
Bu proje, belirli aralıklarla bir web sitesini kontrol eden ve hata olup olmadığını denetleyen bir sistemdir. Eğer hata varsa Telegram üzerinden bildirim gönderir, eğer hata yoksa “Her şey yolunda” şeklinde mesaj atar. Ayrıca her kontrol sonucunu Google Sheets’e tarih ve saat bilgisiyle birlikte kaydeder.

Özellikler:
Her 10 dakikada bir otomatik çalışır.
Belirtilen bir URL'e istek gönderir.
Eğer hata varsa:
Telegram bot ile kullanıcıya mesaj atar.
Aynı mesajı Google Sheets tablosuna yazar.
Eğer hata yoksa:
“Her şey yolunda” mesajı gönderir.
Onu da Sheets’e kaydeder.
Google Sheet'te her satırda şu formatla kayıt tutulur:

yaml
Kopyala
Düzenle
📅 2025-07-09 🕒 15:30:22
✉️ Hata mesajı veya iyi günler mesajı
Kullanılan Teknolojiler:
n8n (kod yazmadan otomasyon aracı)

Telegram Bot API
Google Sheets
HTTP Request işlemi
Node.js ile Code node’ları (tarih, saat, mesaj formatlama vs.)

Nasıl çalışır?
Schedule Trigger ile her 10 dakikada bir tetiklenir.
HTTP Request ile belirlenen web sitesine istek atılır.
Gelen cevaba göre:
Hata varsa: Telegram’a hata mesajı atılır.
Hata yoksa: İyi günler mesajı atılır.
Atılan mesajlar aynı zamanda Google Sheet’e şu şekilde eklenir:
Tarih + SaatMesaj (tek hücrede, alt alta)

Örnek Kayıtlar:

📅 2025-07-09 🕒 15:30:22
✉️ API bağlantı hatası: Timeout

📅 2025-07-09 🕒 15:40:22
✉️ Her şey yolunda! İyi günler 🌞


