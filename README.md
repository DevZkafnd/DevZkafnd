<!-- HEADER WAVE TOP -->
<div align="center">
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=250&text=DevZkafnd&desc=Full%20Stack%20Developer%20%7C%20Game%20Dev%20%7C%20Tech%20Innovator&fontAlign=50&fontAlignY=38&color=0:0a0a0a,50:0d1117,100:161b22&textBg=false&animation=twinkling&fontColor=58a6ff&descColor=3fb950&descAlignY=60&descSize=16&fontSize=50&fontAlignY=40&stroke=58a6ff&strokeWidth=1" />
</div>

<!-- TYPING ANIMATION -->
<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&duration=3000&pause=800&color=58A6FF&center=true&vCenter=true&width=700&height=80&lines=Hello+I+am+Zaki+Affandi;Full+Stack+Developer;Game+Developer;Tech+Enthusiast;Always+Learning" alt="Typing Animation" />

</div>

---

<!-- STATUS BADGES — pakai shields.io static, paling reliable -->
<div align="center">

![Status](https://img.shields.io/badge/Status-Open%20to%20Collaborate-3fb950?style=for-the-badge&logo=statuspage&logoColor=white&labelColor=0d1117)
![Mode](https://img.shields.io/badge/Mode-Developer%20Mode-58a6ff?style=for-the-badge&logo=visualstudiocode&logoColor=white&labelColor=0d1117)
![Coffee](https://img.shields.io/badge/Fuel-Coffee%20Powered-c0682e?style=for-the-badge&logo=buymeacoffee&logoColor=white&labelColor=0d1117)
![Location](https://img.shields.io/badge/Based%20in-Indonesia%20%F0%9F%87%AE%F0%9F%87%A9-f78166?style=for-the-badge&logo=googlemaps&logoColor=white&labelColor=0d1117)

</div>

---

<div align="center">

## 👤 TENTANG SAYA

```js
const devzkafnd = {
  nama       : "Zaki Affandi",
  username   : "DevZkafnd",
  role       : ["Full Stack Developer", "Game Developer"],
  lokasi     : "Indonesia 🇮🇩",
  skills     : ["JavaScript", "TypeScript", "React", "Node.js", "Python", "Game Dev"],
  status     : "🟢 Open to collaboration",
  motto      : "Keep Coding, Keep Gaming, Keep Growing!",
};
```

</div>

---

## 🛠️ TECH STACK

<div align="center">

<img src="https://skillicons.dev/icons?i=js,ts,react,nextjs,vue,html,css,tailwind,nodejs,express,python,php,java,laravel,mysql,postgres,mongodb,firebase,aws,docker,linux,vscode,git,github&theme=dark&perline=12" />

</div>

---

## 📊 GITHUB STATISTICS

<div align="center">

<!-- Stats + Top Langs side by side -->
<img height="195px" src="https://github-readme-stats.vercel.app/api?username=DevZkafnd&show_icons=true&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&icon_color=3fb950&count_private=true&include_all_commits=true&custom_title=GitHub+Stats" />
<img height="195px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=DevZkafnd&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&langs_count=8&custom_title=Top+Languages" />

</div>

<div align="center">

<!-- GitHub Streak -->
<img width="70%" src="https://streak-stats.demolab.com?user=DevZkafnd&theme=github-dark-blue&hide_border=true&background=0d1117&ring=58a6ff&fire=ff7b72&currStreakLabel=3fb950&sideLabels=c9d1d9&dates=8b949e&stroke=58a6ff&currStreakNum=58a6ff&sideNums=c9d1d9" />

</div>

---

## 🏆 GITHUB TROPHIES

<div align="center">

<img src="https://github-profile-trophy.vercel.app/?username=DevZkafnd&theme=algolia&no-frame=true&no-bg=false&margin-w=10&column=7" alt="GitHub Trophies" />

</div>

---

## 🐍 CONTRIBUTION SNAKE

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/DevZkafnd/DevZkafnd/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/DevZkafnd/DevZkafnd/output/github-snake.svg" />
  <img alt="Snake animation" src="https://raw.githubusercontent.com/DevZkafnd/DevZkafnd/output/github-snake-dark.svg" />
</picture>

</div>

---

## 📈 CONTRIBUTION ACTIVITY GRAPH

<div align="center">

<img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=DevZkafnd&bg_color=0d1117&color=58a6ff&line=3fb950&point=ff7b72&area=true&area_color=58a6ff&hide_border=true&custom_title=Contribution+Activity+Graph&radius=8" />

</div>

---

## 🌐 3D CONTRIBUTION GRAPH

<div align="center">

> ⚡ **Setup sekali, jalan selamanya** — jalankan workflow di bawah agar grafik 3D ini tampil otomatis

<!-- Tampil setelah workflow dijalankan -->
<img src="https://raw.githubusercontent.com/DevZkafnd/DevZkafnd/main/profile-3d-contrib/profile-night-rainbow.svg" alt="3D Contribution Graph" width="100%" />

<details>
<summary><b>🔧 Cara Setup 3D Graph (klik untuk buka)</b></summary>
<br/>

Buat file ini di repo profil kamu: `.github/workflows/profile-3d.yml`

```yaml
name: GitHub-Profile-3D-Contrib

on:
  schedule:
    - cron: "0 18 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v3
      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: DevZkafnd
        with:
          MAX_REPOS: 10
      - name: Commit & Push
        run: |
          git config user.email "action@github.com"
          git config user.name "GitHub Action"
          git add -A .
          git commit -m "generate 3d contribution" || exit 0
          git push
```

Lalu klik **Actions → GitHub-Profile-3D-Contrib → Run workflow**

</details>

</div>

---

## 📊 PROFILE SUMMARY

<div align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=DevZkafnd&theme=github_dark" width="100%" />

<img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=DevZkafnd&theme=github_dark" height="180" />
<img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=DevZkafnd&theme=github_dark" height="180" />
<img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=DevZkafnd&theme=github_dark" height="180" />
<img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=DevZkafnd&theme=github_dark&utcOffset=7" height="180" />

</div>

---

## 🤝 HUBUNGI SAYA

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/DevZkafnd)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/zaki-affandi)
[![Twitter](https://img.shields.io/badge/Twitter-1D9BF0?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/DevZkafnd)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/zaki.affandi)
[![Email](https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:zaki.affandi@example.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)](https://devzkafnd.github.io)

</div>

---

## ✨ QUOTE OF THE DAY

<div align="center">

<img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=dark" alt="Dev Quote" width="80%" />

</div>

---

<!-- FOOTER -->
<div align="center">

**"Keep Coding, Keep Gaming, Keep Growing!"**

```js
while (alive) { code(); game(); coffee(); learn(); }
```

<br/>

<!-- DYNAMIC COUNTERS — semuanya realtime dari API -->
<img src="https://komarev.com/ghpvc/?username=DevZkafnd&style=for-the-badge&color=blueviolet&label=PROFILE+VIEWS" alt="Profile Views Counter" />
<br/>
<img src="https://img.shields.io/github/followers/DevZkafnd?style=for-the-badge&logo=github&label=Followers&color=blue" alt="GitHub Followers - Dynamic" />
<img src="https://img.shields.io/github/stars/DevZkafnd?style=for-the-badge&logo=github&label=Total+Stars&color=yellow" alt="GitHub Stars - Dynamic" />

<br/><br/>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=120&color=0:161b22,100:0a0a0a&section=footer&reversal=false" />

</div>
