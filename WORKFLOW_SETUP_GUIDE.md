# 🚀 Panduan Lengkap Setup GitHub Actions Workflows

Panduan ini menjelaskan cara setup tiga workflow GitHub Actions untuk profil README.md Anda:
1. **3D Contribution Graph (Animasi GIF)**
2. **Spotify "Now Playing" (Real-time SVG)**
3. **WakaTime Coding Stats (Auto-update README)**

---

## 📋 Daftar Repository Secrets yang Diperlukan

Sebelum menjalankan workflow, Anda perlu menambahkan secrets berikut di **Settings > Secrets and variables > Actions**:

### 1. Untuk 3D Contribution Graph:
- **`GH_TOKEN`** - Personal Access Token dengan izin `public_repo` dan `read:user`

### 2. Untuk Spotify Now Playing:
- **`SPOTIFY_CLIENT_ID`** - Client ID dari Spotify Developer Dashboard
- **`SPOTIFY_CLIENT_SECRET`** - Client Secret dari Spotify Developer Dashboard
- **`SPOTIFY_REFRESH_TOKEN`** - Refresh Token dari proses OAuth Spotify

### 3. Untuk WakaTime Stats:
- **`WAKATIME_API_KEY`** - API Key dari WakaTime
- **`GH_TOKEN`** - Personal Access Token dengan izin `public_repo` (atau `repo` untuk private repos)

---

## 🎨 1. 3D Contribution Graph (Animasi GIF)

### File Workflow: `.github/workflows/contrib-3d.yml`

✅ **Sudah dibuat!** Workflow ini akan:
- Berjalan setiap 12 jam secara otomatis
- Dapat dijalankan secara manual via `workflow_dispatch`
- Menggunakan action `yoshi389111/github-profile-3d-contrib@v1.3.1`
- Men-generate file `profile-3d-contrib.gif` di root repository
- Auto-commit dan push file GIF ke repository

### Snippet Markdown untuk README.md

Tambahkan snippet berikut di bagian yang ingin menampilkan 3D graph:

```markdown
## 🎨 **3D CONTRIBUTION GRAPH**

<div align="center">

<img src="https://raw.githubusercontent.com/DevZkafnd/profile-readme/main/profile-3d-contrib.gif" alt="3D Contribution Graph" />

</div>
```

**Catatan:** Ganti `DevZkafnd/profile-readme` dengan username dan nama repository Anda.

### Setup GH_TOKEN (Personal Access Token)

1. Buka [GitHub Settings > Developer settings > Personal access tokens > Tokens (classic)](https://github.com/settings/tokens)
2. Klik **"Generate new token (classic)"**
3. Beri nama token (contoh: "Profile README 3D Graph")
4. Pilih scope/permission:
   - ✅ **`public_repo`** - Untuk commit file ke repository
   - ✅ **`read:user`** - Untuk membaca informasi user GitHub
5. Klik **"Generate token"**
6. **SALIN TOKEN SEKARANG** (hanya muncul sekali!)
7. Di repository Anda: **Settings > Secrets and variables > Actions > New repository secret**
8. Nama: `GH_TOKEN`, Value: paste token yang sudah di-copy
9. Klik **"Add secret"**

---

## 🎵 2. Spotify "Now Playing" (Real-time SVG)

### File Workflow: `.github/workflows/spotify.yml`

✅ **Sudah di-update!** Workflow ini akan:
- Berjalan setiap 5 menit secara otomatis
- Dapat dijalankan secara manual via `workflow_dispatch`
- Menggunakan action `novatorem/github-readme-spotify@main`
- Men-generate file `spotify-now-playing.svg` di root repository
- Auto-commit dan push file SVG ke repository

### Snippet Markdown untuk README.md

Tambahkan snippet berikut di bagian yang ingin menampilkan Spotify status:

```markdown
## 🎵 **NOW PLAYING ON SPOTIFY**

<div align="center">

<img src="https://raw.githubusercontent.com/DevZkafnd/profile-readme/main/spotify-now-playing.svg" alt="Spotify Now Playing" />

</div>
```

**Catatan:** Ganti `DevZkafnd/profile-readme` dengan username dan nama repository Anda.

### Setup Spotify API Credentials

#### Langkah 1: Buat Spotify App

1. Kunjungi [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/applications)
2. Login dengan akun Spotify Anda
3. Klik **"Create an App"**
4. Isi form:
   - **App name**: Nama aplikasi (contoh: "GitHub Profile")
   - **App description**: Deskripsi singkat
   - **Website**: URL repository GitHub Anda (contoh: `https://github.com/DevZkafnd`)
   - **Redirect URI**: `http://localhost:3000/callback` (atau URL lain yang valid)
5. Centang **"I understand and agree to Spotify's Developer Terms of Service"**
6. Klik **"Save"**

#### Langkah 2: Dapatkan Client ID dan Client Secret

1. Setelah app dibuat, Anda akan melihat:
   - **Client ID** - Copy ini untuk secret `SPOTIFY_CLIENT_ID`
   - **Client Secret** - Klik "View client secret" dan copy untuk secret `SPOTIFY_CLIENT_SECRET`

#### Langkah 3: Dapatkan Refresh Token

Refresh token diperlukan untuk mendapatkan akses ke API Spotify. Ada beberapa cara:

**Cara 1: Menggunakan Tool Online (Paling Mudah)**
1. Kunjungi [Spotify Refresh Token Generator](https://github.com/novatorem/novatorem#-setup)
2. Atau gunakan tool online seperti: `https://github.com/novatorem/novatorem#-setup`
3. Masukkan `Client ID` dan `Client Secret` Anda
4. Authorize aplikasi
5. Copy `refresh_token` yang dihasilkan

**Cara 2: Manual OAuth Flow**
1. Buat URL authorization:
   ```
   https://accounts.spotify.com/authorize?client_id=YOUR_CLIENT_ID&response_type=code&redirect_uri=http://localhost:3000/callback&scope=user-read-currently-playing,user-read-recently-played
   ```
2. Ganti `YOUR_CLIENT_ID` dengan Client ID Anda
3. Buka URL tersebut di browser
4. Login dan authorize
5. Setelah redirect, ambil `code` dari URL callback
6. Exchange code untuk refresh token menggunakan API atau tool

**Cara 3: Menggunakan Script Python (Alternatif)**
```python
import requests
import base64

CLIENT_ID = "your_client_id"
CLIENT_SECRET = "your_client_secret"
REDIRECT_URI = "http://localhost:3000/callback"

# Step 1: Get authorization code from browser
# Step 2: Exchange code for tokens
auth_code = "your_authorization_code"
auth_string = base64.b64encode(f"{CLIENT_ID}:{CLIENT_SECRET}".encode()).decode()
response = requests.post(
    "https://accounts.spotify.com/api/token",
    headers={"Authorization": f"Basic {auth_string}"},
    data={
        "grant_type": "authorization_code",
        "code": auth_code,
        "redirect_uri": REDIRECT_URI
    }
)
tokens = response.json()
refresh_token = tokens["refresh_token"]
print(refresh_token)
```

#### Langkah 4: Tambahkan Secrets ke GitHub

1. Di repository: **Settings > Secrets and variables > Actions > New repository secret**
2. Tambahkan tiga secrets:
   - **Name**: `SPOTIFY_CLIENT_ID`, **Value**: Client ID Anda
   - **Name**: `SPOTIFY_CLIENT_SECRET`, **Value**: Client Secret Anda
   - **Name**: `SPOTIFY_REFRESH_TOKEN`, **Value**: Refresh Token Anda

---

## ⏱️ 3. WakaTime Coding Stats (Auto-update README)

### File Workflow: `.github/workflows/wakatime.yml`

✅ **Sudah di-update!** Workflow ini akan:
- Berjalan setiap 4 jam secara otomatis
- Dapat dijalankan secara manual via `workflow_dispatch`
- Menggunakan action `athul/waka-readme@master`
- Secara otomatis meng-edit `README.md` dan menyisipkan statistik WakaTime
- Tidak menghasilkan file terpisah, langsung update README.md

### Snippet Markdown untuk README.md (Placeholder)

Tambahkan placeholder berikut di `README.md` di lokasi yang ingin menampilkan statistik WakaTime:

```markdown
## ⏱️ **WAKATIME CODING STATS**

<div align="center">

<!--START_SECTION:waka-->
<!--END_SECTION:waka-->

</div>
```

**Catatan Penting:**
- Action `athul/waka-readme@master` menggunakan placeholder `<!--START_SECTION:waka-->` dan `<!--END_SECTION:waka-->`
- Action akan secara otomatis mengganti konten di antara kedua komentar tersebut dengan statistik WakaTime
- Jangan menghapus atau mengubah placeholder ini!

### Setup WakaTime API Key

1. **Install WakaTime Extension:**
   - Install extension WakaTime di editor/IDE Anda (VS Code, IntelliJ, dll)
   - Login dengan akun WakaTime saat diminta
   - Extension akan mulai tracking waktu coding Anda

2. **Dapatkan API Key:**
   - Kunjungi [WakaTime Dashboard](https://wakatime.com/)
   - Login ke akun Anda
   - Buka **Settings > Account** (atau langsung ke https://wakatime.com/settings/account)
   - Scroll ke bagian **"Secret API Key"**
   - Klik **"Show API Key"** atau **"Copy"**
   - Copy API key yang ditampilkan

3. **Tambahkan Secret ke GitHub:**
   - Di repository: **Settings > Secrets and variables > Actions > New repository secret**
   - **Name**: `WAKATIME_API_KEY`
   - **Value**: Paste API key yang sudah di-copy
   - Klik **"Add secret"**

### Setup GH_TOKEN untuk WakaTime

Untuk WakaTime workflow, Anda juga perlu `GH_TOKEN`:
- Jika repository **public**: Gunakan scope `public_repo` saja
- Jika repository **private**: Gunakan scope `repo` (full access)

Anda bisa menggunakan `GH_TOKEN` yang sama dengan yang digunakan untuk 3D Contribution Graph, atau membuat token terpisah.

---

## ✅ Checklist Final Setup

Setelah semua workflow dibuat dan secrets ditambahkan:

- [ ] `GH_TOKEN` sudah ditambahkan dengan izin `public_repo` dan `read:user`
- [ ] `SPOTIFY_CLIENT_ID` sudah ditambahkan
- [ ] `SPOTIFY_CLIENT_SECRET` sudah ditambahkan
- [ ] `SPOTIFY_REFRESH_TOKEN` sudah ditambahkan
- [ ] `WAKATIME_API_KEY` sudah ditambahkan
- [ ] Placeholder `<!--START_SECTION:waka-->` dan `<!--END_SECTION:waka-->` sudah ditambahkan di README.md
- [ ] Snippet Markdown untuk 3D graph dan Spotify sudah ditambahkan di README.md
- [ ] Semua workflow sudah di-test dengan menjalankan manual via `workflow_dispatch`

---

## 🧪 Testing Workflows

### Cara Test Manual:

1. Buka tab **Actions** di repository GitHub Anda
2. Pilih workflow yang ingin di-test (misalnya "3D Contribution Graph")
3. Klik **"Run workflow"** di sisi kanan
4. Pilih branch (biasanya `main` atau `master`)
5. Klik **"Run workflow"**
6. Tunggu workflow selesai berjalan
7. Cek apakah file sudah ter-generate atau README sudah ter-update

### Troubleshooting:

**3D Graph tidak muncul:**
- Pastikan `GH_TOKEN` sudah benar
- Cek workflow logs untuk error messages
- Pastikan workflow sudah berjalan setidaknya sekali

**Spotify tidak muncul:**
- Pastikan semua 3 secrets Spotify sudah benar
- Pastikan refresh token masih valid (tidak expired)
- Cek apakah Spotify app sudah di-setup dengan benar
- Pastikan Anda sudah pernah memutar musik di Spotify setelah setup

**WakaTime tidak muncul:**
- Pastikan WakaTime extension sudah terinstall dan aktif
- Pastikan Anda sudah melakukan coding activity (WakaTime perlu data untuk ditampilkan)
- Pastikan API key sudah benar
- Pastikan placeholder `<!--START_SECTION:waka-->` sudah ada di README.md
- Cek workflow logs untuk error messages

---

## 📚 Resources Tambahan

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [WakaTime Documentation](https://wakatime.com/help)
- [Spotify Web API Documentation](https://developer.spotify.com/documentation/web-api)
- [3D Contribution Graph Action](https://github.com/yoshi389111/github-profile-3d-contrib)
- [Spotify Now Playing Action](https://github.com/novatorem/github-readme-spotify)
- [WakaTime README Action](https://github.com/athul/waka-readme)

---

**Selamat! Profil GitHub Anda sekarang sudah "hidup" dengan fitur-fitur yang ter-update secara real-time! 🚀**

