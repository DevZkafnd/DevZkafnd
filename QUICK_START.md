# ⚡ Quick Start Guide - GitHub Profile README Workflows

Panduan cepat untuk setup tiga workflow GitHub Actions.

---

## 📁 File yang Sudah Dibuat

✅ **Workflow Files:**
- `.github/workflows/contrib-3d.yml` - 3D Contribution Graph (setiap 12 jam)
- `.github/workflows/spotify.yml` - Spotify Now Playing (setiap 5 menit)
- `.github/workflows/wakatime.yml` - WakaTime Stats (setiap 4 jam)

✅ **Documentation:**
- `WORKFLOW_SETUP_GUIDE.md` - Panduan lengkap setup

---

## 🔑 Secrets yang Perlu Ditambahkan

Buka **Settings > Secrets and variables > Actions** di repository GitHub Anda, lalu tambahkan:

### 1. GH_TOKEN
- **Nama:** `GH_TOKEN`
- **Value:** Personal Access Token dengan izin `public_repo` dan `read:user`
- **Cara membuat:** [GitHub Settings > Developer settings > Personal access tokens](https://github.com/settings/tokens)

### 2. Spotify Secrets (3 secrets)
- **SPOTIFY_CLIENT_ID** - Dari [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
- **SPOTIFY_CLIENT_SECRET** - Dari Spotify Developer Dashboard
- **SPOTIFY_REFRESH_TOKEN** - Dari proses OAuth Spotify

### 3. WakaTime Secret
- **WAKATIME_API_KEY** - Dari [WakaTime Settings](https://wakatime.com/settings/account)

> 📖 **Detail lengkap:** Lihat `WORKFLOW_SETUP_GUIDE.md`

---

## 📝 Update README.md

### 1. 3D Contribution Graph

Path sudah di-set di README.md:
```markdown
<img src="https://raw.githubusercontent.com/DevZkafnd/DevZkafnd/main/profile-3d-contrib.gif" alt="3D Contribution Graph" />
```

### 2. Spotify Now Playing

Path sudah di-set di README.md:
```markdown
<img src="https://raw.githubusercontent.com/DevZkafnd/DevZkafnd/main/spotify-now-playing.svg" alt="Spotify Now Playing" />
```

### 3. WakaTime Stats

Placeholder sudah ada di README.md:
```markdown
<!--START_SECTION:waka-->
<!--END_SECTION:waka-->
```

> ✅ **README.md sudah di root repository, semua path sudah benar!**

---

## 🚀 Testing

1. Buka tab **Actions** di GitHub
2. Pilih workflow yang ingin di-test
3. Klik **"Run workflow"**
4. Tunggu hingga selesai
5. Cek apakah file ter-generate atau README ter-update

---

## 📚 Resources

- **Panduan Lengkap:** `WORKFLOW_SETUP_GUIDE.md`
- **GitHub Actions Docs:** https://docs.github.com/en/actions
- **WakaTime:** https://wakatime.com
- **Spotify API:** https://developer.spotify.com

---

**Selamat! Setup workflow Anda sudah siap! 🎉**

