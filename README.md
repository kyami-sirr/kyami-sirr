<!-- Profil GitHub kyami-sirr. Edit bagian yang perlu saja -->

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=260&section=header&text=Muhammad%20Yasir%20Assafa&fontSize=46&fontColor=ffffff&fontAlignY=40&desc=Robotics%20%7C%20ROS2%20%7C%20SLAM&descAlignY=62&descSize=20&animation=twinkling" alt="header" />

<a href="https://github.com/kyami-sirr">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=1000&color=5FB3D9&center=true&vCenter=true&width=700&lines=Membangun+robot+dengan+ROS2;Simulasi+di+Gazebo%2C+visualisasi+di+RViz2;Memetakan+dunia+dengan+algoritma+SLAM;Terbuka+untuk+diskusi+dan+kolaborasi" alt="typing" />
</a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=kyami-sirr&label=Pengunjung&color=2c5364&style=for-the-badge" alt="views" />
<img src="https://img.shields.io/github/followers/kyami-sirr?label=Followers&style=for-the-badge&color=2c5364&logo=github" alt="followers" />
<img src="https://img.shields.io/github/stars/kyami-sirr?label=Total%20Stars&style=for-the-badge&color=2c5364&logo=github" alt="stars" />

<br/><br/>

<!-- Menu navigasi, klik untuk lompat ke bagian -->
<a href="#tentang-saya"><img src="https://img.shields.io/badge/Tentang_Saya-203a43?style=for-the-badge" alt="Tentang Saya" /></a>
<a href="#proyek-robot-slam"><img src="https://img.shields.io/badge/Proyek_Robot-203a43?style=for-the-badge" alt="Proyek Robot" /></a>
<a href="#tanya-jawab-singkat"><img src="https://img.shields.io/badge/Tanya_Jawab-203a43?style=for-the-badge" alt="Tanya Jawab" /></a>
<a href="#tech-stack"><img src="https://img.shields.io/badge/Tech_Stack-203a43?style=for-the-badge" alt="Tech Stack" /></a>
<a href="#statistik-github"><img src="https://img.shields.io/badge/Statistik-203a43?style=for-the-badge" alt="Statistik" /></a>
<a href="#kontak"><img src="https://img.shields.io/badge/Kontak-203a43?style=for-the-badge" alt="Kontak" /></a>

</div>

<br/>

## Tentang Saya

Saya Muhammad Yasir Assafa. Saat ini saya membangun robot berbasis ROS2 dengan algoritma SLAM, memakai Gazebo untuk simulasi dan RViz2 untuk visualisasi.

| | |
|:--|:--|
| Sedang dikerjakan | Robot SLAM dengan ROS2, Gazebo, dan RViz2 |
| Sedang dipelajari | Navigasi otonom dan pemetaan lingkungan |
| Terbuka untuk | Diskusi dan kolaborasi di bidang robotika |

## Proyek Robot SLAM

Robot yang memetakan lingkungan sambil menentukan posisinya sendiri. Semua dikembangkan dan diuji di simulasi dulu sebelum dicoba pada robot nyata.

### Alur data robot

```mermaid
flowchart LR
  A["Gazebo<br/>simulasi robot dan dunia"] -->|"/scan, /odom"| B["Algoritma SLAM<br/>pemetaan dan lokalisasi"]
  B -->|"/map, TF"| C["RViz2<br/>visualisasi"]
  B --> D["Navigasi otonom<br/>(rencana)"]
```

### Cara kerja satu siklus SLAM

```mermaid
sequenceDiagram
  participant S as Sensor
  participant O as Odometri
  participant L as SLAM
  participant M as Peta
  S->>L: data scan
  O->>L: estimasi gerak
  L->>L: cocokkan scan, perbarui posisi
  L->>M: perbarui peta
  M-->>L: peta terkini
  Note over L,M: diulang terus selama robot bergerak
```

### Peta jalan

```mermaid
flowchart LR
  A["Simulasi<br/>Gazebo"]:::done --> B["Visualisasi<br/>RViz2"]:::done --> C["Pemetaan<br/>SLAM"]:::now --> D["Navigasi<br/>otonom"]:::next --> E["Robot<br/>nyata"]:::next
  classDef done fill:#1f6feb,color:#ffffff,stroke:none
  classDef now fill:#e3b341,color:#000000,stroke:none
  classDef next fill:#30363d,color:#c9d1d9,stroke:none
```

Biru: selesai. Kuning: sedang dikerjakan. Abu-abu: rencana.

<details>
<summary><b>Cara menjalankan (klik untuk buka)</b></summary>
<br/>

```bash
# Bangun workspace
cd ~/ros2_ws
colcon build --symlink-install
source install/setup.bash

# Jalankan simulasi (ganti nama paket dan launch file)
ros2 launch <nama_paket> <simulasi>.launch.py

# Buka RViz2
rviz2
```

</details>

<details>
<summary><b>Rencana pengembangan (klik untuk buka)</b></summary>
<br/>

- [x] Model robot dan dunia simulasi di Gazebo
- [x] Visualisasi data sensor di RViz2
- [ ] Pemetaan dengan algoritma SLAM
- [ ] Navigasi otonom pada peta yang dibuat
- [ ] Uji coba pada robot nyata

</details>

## Tanya Jawab Singkat

<details>
<summary><b>Apa itu SLAM?</b></summary>
<br/>

SLAM (Simultaneous Localization and Mapping) adalah cara robot membuat peta lingkungan sambil menentukan posisinya sendiri di peta itu, pada saat yang sama.

</details>

<details>
<summary><b>Apa itu ROS2?</b></summary>
<br/>

ROS2 (Robot Operating System 2) adalah kumpulan alat dan pustaka untuk membangun perangkat lunak robot. Bagian-bagian robot saling bertukar data lewat node dan topic.

</details>

<details>
<summary><b>Kenapa mulai dari Gazebo?</b></summary>
<br/>

Simulasi membuat saya bisa mencoba algoritma berulang kali tanpa risiko merusak robot, dan tanpa harus menyiapkan lingkungan fisik setiap kali.

</details>

<details>
<summary><b>Apa fungsi RViz2?</b></summary>
<br/>

RViz2 menampilkan apa yang "dilihat" robot: data sensor, peta yang sedang dibuat, posisi robot, dan hasil navigasi. Ini sangat membantu untuk debugging.

</details>

## Tech Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=ros,py,cpp,linux,ubuntu,git,github,vscode,bash&theme=dark" alt="tech stack" />

</div>

## Statistik GitHub

<div align="center">

<img height="180" src="https://github-readme-stats.vercel.app/api?username=kyami-sirr&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&rank_icon=github" alt="stats" />
<img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=kyami-sirr&layout=donut-vertical&theme=tokyonight&hide_border=true&langs_count=6" alt="top languages" />

<img src="https://streak-stats.demolab.com?user=kyami-sirr&theme=tokyonight&hide_border=true" alt="streak" />

<img src="https://github-readme-activity-graph.vercel.app/graph?username=kyami-sirr&theme=tokyo-night&hide_border=true&area=true&custom_title=Grafik%20Aktivitas%20GitHub" alt="activity graph" />

<img src="https://github-profile-trophy.vercel.app/?username=kyami-sirr&theme=darkhub&no-frame=true&no-bg=true&margin-w=10&column=7" alt="trophies" />

</div>

## Kontak

<div align="center">

<a href="https://linkedin.com/in/kyami-sirr"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="mailto:emailkamu@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
<a href="https://instagram.com/kyami-sirr"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram" /></a>

<br/><br/>

Kalau proyek saya bermanfaat, kasih bintang ya.

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=110&section=footer" width="100%" alt="footer" />
