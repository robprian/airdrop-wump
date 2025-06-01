# WUMP Auto Claim Bot - Node.js Version

Bot otomatis untuk claim reward WUMP dengan sistem proxy otomatis.

## ✨ Fitur Utama

- 🔄 **Auto Proxy Management**: Otomatis menggunakan proxy dari 2 sumber terpercaya
- 🔃 **Auto Proxy Rotation**: Proxy yang mati langsung dihapus dan diganti
- ⏰ **Auto Refresh**: List proxy di-refresh setiap 30 menit
- 🚀 **High Performance**: Menggunakan Node.js untuk performa yang lebih baik
- 🛡️ **Error Handling**: Sistem penanganan error yang robust
- 📊 **Real-time Logging**: Log aktivitas dengan timestamp WIB

## 🚀 Instalasi

### 1. Install Node.js
Pastikan Node.js versi 16 atau lebih baru sudah terinstall di sistem Anda.
Download dari: https://nodejs.org/

### 2. Clone/Download Script
```bash
# Download semua file ke folder project
# - wump-bot.js
# - package.json
# - tokens.txt (buat file ini)
```

### 3. Install Dependencies
```bash
npm install
# atau
npm install axios https-proxy-agent socks-proxy-agent
```

## 📝 Konfigurasi

### Format tokens.txt
Buat file `tokens.txt` di folder yang sama dengan script, format per baris:

```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

**⚠️ Format yang didukung:**
- Dengan prefix "Bearer ": `Bearer eyJ0eXAi...`
- Tanpa prefix: `eyJ0eXAi...`

### Cara Mendapatkan Token
1. Login ke https://wump.xyz
2. Buka Developer Tools (F12)
3. Pilih tab Network
4. Refresh halaman
5. Cari request ke `api.wump.xyz`
6. Lihat header `Authorization`, copy nilai setelah "Bearer "

## 🎯 Menjalankan Bot

### Mode Normal
```bash
npm start
# atau
node wump-bot.js
```

### Mode Development (dengan auto-restart)
```bash
npm run dev
```

## 🔧 Fitur Proxy

### Sumber Proxy Otomatis
Bot menggunakan 2 sumber proxy gratis:
1. `https://raw.githubusercontent.com/dpangestuw/Free-Proxy/refs/heads/main/All_proxies.txt`
2. `https://raw.githubusercontent.com/monosans/proxy-list/refs/heads/main/proxies/all.txt`

### Manajemen Proxy
- ✅ Auto download dan kombinasi dari kedua sumber
- ✅ Auto test proxy sebelum digunakan
- ✅ Proxy mati langsung dihapus dari list
- ✅ Auto refresh list setiap 30 menit
- ✅ Support HTTP, HTTPS, SOCKS4, SOCKS5
- ✅ Setiap account mendapat proxy berbeda

### Format Proxy yang Didukung
```
1.2.3.4:8080
http://1.2.3.4:8080
https://1.2.3.4:8080
socks4://1.2.3.4:1080
socks5://1.2.3.4:1080
user:pass@1.2.3.4:8080
```

## 📊 Fitur Utama Bot

### Auto Claim Tasks
- ✅ Otomatis claim semua task yang belum selesai
- ✅ Skip task yang sudah dikerjakan
- ✅ Real-time status update
- ✅ Reward tracking per task

### Account Management
- ✅ Multi-account support
- ✅ Token validation dan expiry check
- ✅ Balance monitoring
- ✅ Account masking untuk privacy

### Scheduling
- ✅ Berjalan 24/7 dengan interval 12 jam
- ✅ Countdown timer untuk next run
- ✅ Graceful shutdown dengan Ctrl+C

## 🛠️ Troubleshooting

### Error: "No tokens found in tokens.txt"
- Pastikan file `tokens.txt` ada di folder yang sama
- Pastikan file tidak kosong
- Check format token sudah benar

### Error: "Access Token Invalid"
- Token mungkin salah format
- Copy ulang token dari browser
- Pastikan token masih valid (belum expired)

### Error: "No working proxy available"
- Bot akan mencoba download proxy baru
- Tunggu 30 detik untuk refresh otomatis
- Check koneksi internet

### Error: "Failed to load proxies"
- Check koneksi internet
- Proxy sources mungkin down sementara
- Bot akan retry otomatis

## 📋 Log Output

Bot akan menampilkan informasi berikut:
```
[ 01/06/2025 14:30:15 WIB ] | Account's Total: 5
[ 01/06/2025 14:30:16 WIB ] | Proxies loaded: 1250
[ 01/06/2025 14:30:17 WIB ] | Account   : abc***def@gmail.com 
[ 01/06/2025 14:30:18 WIB ] | Proxy     : 1.2.3.4:8080 - 200 OK 
[ 01/06/2025 14:30:19 WIB ] | Balance   : 1500 WUMP 
[ 01/06/2025 14:30:20 WIB ] | Task Lists:
[ 01/06/2025 14:30:21 WIB ] |    > Daily Login Completed Successfully - Reward: 100 WUMP
```

## ⚡ Performance Tips

### Untuk Hasil Optimal
1. **Gunakan VPS/Server** dengan koneksi stabil
2. **Monitor logs** untuk memastikan proxy bekerja
3. **Check balance** secara berkala
4. **Backup tokens.txt** di tempat aman

### Resource Usage
- **RAM**: ~50-100MB per instance
- **CPU**: Minimal (mostly idle)
- **Network**: ~1-5MB per hour (tergantung jumlah account)

## 🔒 Keamanan

### Best Practices
- ✅ Jangan share file `tokens.txt`
- ✅ Gunakan account terpisah untuk farming
- ✅ Monitor aktivitas account secara berkala
- ✅ Backup token di tempat aman

### Privacy
- ✅ Email di-mask dalam log (abc***def@gmail.com)
- ✅ Token tidak ditampilkan di console
- ✅ Proxy connection secure

## 🆘 Support & Contact

Jika mengalami masalah:
1. Check troubleshooting guide di atas
2. Pastikan semua dependency terinstall
3. Coba restart bot
4. Check format tokens.txt

## 📜 Changelog

### v1.0.0 (Current)
- ✅ Migrasi dari Python ke Node.js
- ✅ Auto proxy management
- ✅ Auto refresh proxy setiap 30 menit
- ✅ Dead proxy detection dan removal
- ✅ Multi-source proxy loading
- ✅ Improved error handling
- ✅ Better logging system
- ✅ Watermark "robprian"

## 📄 License

MIT License - Free to use and modify

---

**Made with ❤️ by robprian**
