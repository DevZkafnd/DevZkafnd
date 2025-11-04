# 🚀 Setup Guide - Fitur "Waw" untuk GitHub Profile

Panduan lengkap untuk mengaktifkan semua fitur dinamis yang telah ditambahkan ke profil GitHub Anda.

## 📋 Daftar Fitur yang Ditambahkan

1. ✅ **3D Contribution Graph** - Visualisasi kontribusi 3D (Sudah Aktif!)
2. ⏱️ **WakaTime Coding Stats** - Statistik coding waktu nyata dari editor
3. 🎵 **Spotify Now Playing** - Menampilkan lagu yang sedang diputar
4. 📝 **Blog Posts Auto-Update** - Daftar postingan blog terbaru otomatis

---

## ⏱️ Setup WakaTime Stats

### Langkah 1: Install WakaTime Extension
1. Install WakaTime extension di editor favorit Anda:
   - **VS Code**: [WakaTime Extension](https://marketplace.visualstudio.com/items?itemName=WakaTime.vscode-wakatime)
   - **IntelliJ IDEA**: [WakaTime Plugin](https://plugins.jetbrains.com/plugin/7426-wakatime)
   - **Sublime Text**: [WakaTime Package](https://packagecontrol.io/packages/WakaTime)

### Langkah 2: Dapatkan API Key
1. Buka [WakaTime Dashboard](https://wakatime.com/)
2. Login atau buat akun baru
3. Pergi ke **Settings** → **API Keys**
4. Copy API Key Anda

### Langkah 3: Tambahkan ke GitHub Secrets
1. Buka repository GitHub Anda
2. Pergi ke **Settings** → **Secrets and variables** → **Actions**
3. Klik **New repository secret**
4. Tambahkan secret dengan nama: `WAKATIME_API_KEY`
5. Paste API Key WakaTime Anda
6. Klik **Add secret**

### Langkah 4: Aktifkan Workflow
1. Pergi ke tab **Actions** di repository Anda
2. Pilih workflow **WakaTime Stats**
3. Klik **Run workflow** untuk test pertama kali
4. Workflow akan otomatis berjalan setiap jam

---

## 🎵 Setup Spotify Now Playing

### Langkah 1: Buat Spotify App
1. Buka [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
2. Login dengan akun Spotify Anda
3. Klik **Create App**
4. Isi form:
   - **App name**: `GitHub Profile Status` (atau nama lain)
   - **App description**: `Display now playing on GitHub profile`
   - **Redirect URI**: `https://github.com/DevZkafnd` (atau URL profil GitHub Anda)
5. Terima terms dan klik **Create**
6. Klik **Settings** dan tambahkan Redirect URI: `https://github.com/DevZkafnd`

### Langkah 2: Dapatkan Client ID & Secret
1. Di dashboard app Anda, copy **Client ID**
2. Klik **View client secret** dan copy **Client Secret**

### Langkah 3: Dapatkan Refresh Token
Gunakan tool ini untuk mendapatkan refresh token:
- [Spotify Token Generator](https://github.com/novatorem/novatorem#setup)

Atau gunakan script Python sederhana:

```python
import base64
import requests

CLIENT_ID = 'YOUR_CLIENT_ID'
CLIENT_SECRET = 'YOUR_CLIENT_SECRET'

# Encode credentials
credentials = f"{CLIENT_ID}:{CLIENT_SECRET}"
encoded_credentials = base64.b64encode(credentials.encode()).decode()

# Get refresh token
token_url = 'https://accounts.spotify.com/api/token'
headers = {
    'Authorization': f'Basic {encoded_credentials}',
    'Content-Type': 'application/x-www-form-urlencoded'
}
data = {
    'grant_type': 'client_credentials'
}

response = requests.post(token_url, headers=headers, data=data)
print(response.json())
```

### Langkah 4: Tambahkan ke GitHub Secrets
Tambahkan 3 secrets berikut:
- `SPOTIFY_CLIENT_ID` - Client ID dari Spotify Dashboard
- `SPOTIFY_CLIENT_SECRET` - Client Secret dari Spotify Dashboard  
- `SPOTIFY_REFRESH_TOKEN` - Refresh Token yang didapat dari langkah 3

### Langkah 5: Aktifkan Workflow
1. Pergi ke tab **Actions**
2. Pilih workflow **Update Spotify Status**
3. Klik **Run workflow** untuk test
4. Workflow akan otomatis berjalan setiap 30 menit

---

## 📝 Setup Blog Posts Auto-Update

### Langkah 1: Identifikasi RSS Feed Anda
Format RSS feed umum:
- **Medium**: `https://medium.com/feed/@username`
- **Dev.to**: `https://dev.to/feed/username`
- **Hashnode**: `https://hashnode.com/rss/@username`
- **WordPress**: `https://yoursite.com/feed/`

### Langkah 2: Update Workflow
Edit file `.github/workflows/blog-post-workflow.yml`:

```yaml
feed_list: "https://medium.com/feed/@devzkafnd,https://dev.to/feed/devzkafnd"
```

Ganti dengan RSS feed URL Anda (pisahkan dengan koma jika multiple).

### Langkah 3: Customize Template (Opsional)
Anda bisa mengubah tampilan daftar blog dengan mengedit bagian `template` dan `item_template` di workflow file.

### Langkah 4: Aktifkan Workflow
1. Commit perubahan workflow file
2. Pergi ke tab **Actions**
3. Workflow akan otomatis berjalan setiap 6 jam

---

## 🎨 3D Contribution Graph

**Sudah Aktif!** Tidak perlu setup tambahan. Graph akan otomatis ter-generate.

Anda bisa customize dengan mengubah parameter di URL:
- `theme`: `dracula`, `gitdark`, `github`, `github_dark`, `github_dark_dimmed`, dll
- `dimensions`: Ukuran dimensi (default: 8)
- `column`: Jumlah kolom (default: 7)

Contoh customization:
```markdown
<img src="https://github-profile-3d-contrib.vercel.app/profile/?username=DevZkafnd&theme=github_dark&dimensions=10&column=7" alt="3D Contribution Graph" />
```

---

## ✅ Checklist Final

Setelah setup semua fitur:

- [ ] WakaTime API key ditambahkan ke GitHub Secrets
- [ ] Spotify credentials (Client ID, Secret, Refresh Token) ditambahkan
- [ ] Blog RSS feed URL sudah di-update di workflow
- [ ] Semua workflow sudah di-run manual sekali untuk test
- [ ] Profil GitHub sudah di-refresh dan cek apakah semua fitur muncul

---

## 🐛 Troubleshooting

### WakaTime tidak muncul
- Pastikan WakaTime extension sudah terinstall dan aktif di editor
- Pastikan API key sudah benar di GitHub Secrets
- Cek workflow logs di tab Actions untuk error messages

### Spotify tidak muncul
- Pastikan semua 3 secrets sudah ditambahkan
- Pastikan refresh token masih valid
- Cek apakah Spotify app sudah di-setup dengan benar di dashboard

### Blog posts tidak muncul
- Pastikan RSS feed URL valid (bisa test dengan membuka URL di browser)
- Pastikan format RSS feed sesuai standar
- Cek workflow logs untuk error messages

---

## 📚 Resources Tambahan

- [WakaTime Documentation](https://wakatime.com/help)
- [Spotify Web API](https://developer.spotify.com/documentation/web-api)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [3D Contribution Graph](https://github.com/yoshi389111/github-profile-3d-contrib)

---

**Selamat! Profil GitHub Anda sekarang sudah "hidup" dan ter-update secara real-time! 🚀**

