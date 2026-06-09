# เว็บไซต์สภานักเรียน — โรงเรียนราชโบริกานุเคราะห์

> **Live site:** [https://ratbsc.com](https://ratbsc.com)
> Repository ของเว็บไซต์อย่างเป็นทางการของสภานักเรียน โรงเรียนราชโบริกานุเคราะห์ จังหวัดราชบุรี

[![Instagram](https://img.shields.io/badge/Instagram-@studentcouncil__rb-E4405F?logo=instagram&logoColor=white)](https://www.instagram.com/studentcouncil_rb/)
[![Facebook](https://img.shields.io/badge/Facebook-สภานักเรียน_RB-1877F2?logo=facebook&logoColor=white)](https://www.facebook.com/RBStudentCouncil2561)

---

## 📑 สารบัญ

- [ภาพรวม](#-ภาพรวม)
- [หน้าเว็บทั้งหมด](#-หน้าเว็บทั้งหมด)
- [โครงสร้างโปรเจกต์](#-โครงสร้างโปรเจกต์)
- [วิธีอัปเดตเนื้อหา](#-วิธีอัปเดตเนื้อหา-สำคัญสุด)
- [การพัฒนาเว็บ (สำหรับ Developer)](#-การพัฒนาเว็บ-สำหรับ-developer)
- [การ Deploy](#-การ-deploy)
- [เทคโนโลยีที่ใช้](#-เทคโนโลยีที่ใช้)
- [การส่งต่อให้รุ่นน้อง](#-การส่งต่อให้รุ่นน้อง)

---

## 🌟 ภาพรวม

เว็บไซต์นี้เป็น **static website** (HTML/CSS/JS ล้วน) ที่ออกแบบมาให้:

- ✅ **สภาแก้เนื้อหาได้เองผ่าน Google Sheets** — ไม่ต้องเขียนโค้ด ไม่ต้อง push git
- ✅ **โหลดเร็ว** — ใช้ CDN ของ GitHub Pages + Cloudflare
- ✅ **มือถือใช้ได้** — responsive ทุกหน้า
- ✅ **ส่งต่อรุ่นน้องง่าย** — โครงสร้างเรียบง่าย ไม่มี framework ซับซ้อน

---

## 📄 หน้าเว็บทั้งหมด

| URL | หน้า | คำอธิบาย |
|-----|------|----------|
| [`/`](https://ratbsc.com/) | หน้าแรก | รวมข้อมูลล่าสุดจากทุกหน้า — กิจกรรม โอกาส ผลงาน |
| [`/council`](https://ratbsc.com/council) | สภานักเรียน | รายชื่อคณะกรรมการสภาแยกตามปีการศึกษา |
| [`/hall-of-fame`](https://ratbsc.com/hall-of-fame) | Hall of Fame | รวมรางวัล/ผลงานของนักเรียน RB |
| [`/find-your-future`](https://ratbsc.com/find-your-future) | Find Your Future | ค่าย ทุน กิจกรรมเพื่อพอร์ตและศึกษาต่อ |
| [`/calendar`](https://ratbsc.com/calendar) | ปฏิทิน | กำหนดการ TCAS และกิจกรรมโรงเรียน |
| [`/schedule`](https://ratbsc.com/schedule) | ตารางเรียน | ลิงก์ไประบบตารางสอนของโรงเรียน |

---

## 📁 โครงสร้างโปรเจกต์

```
rb-council/
├── 📄 index.html              หน้าแรก
├── 📄 council.html            สภานักเรียน
├── 📄 hall-of-fame.html       Hall of Fame
├── 📄 find-your-future.html   Find Your Future
├── 📄 calendar.html           ปฏิทิน
├── 📄 schedule.html           ตารางเรียน
│
├── 📁 css/
│   └── style.css              ดีไซน์รวมทั้งเว็บ
│
├── 📁 js/
│   └── main.js                เมนู + scroll reveal
│
├── 📁 images/
│   ├── logo.png               โลโก้สภานักเรียน (favicon ด้วย)
│   ├── council/               รูปกรรมการสภา
│   │   └── 2569/              แยกตามปีการศึกษา
│   └── hall/                  รูป Hall of Fame
│
├── 📁 data/
│   └── hall.json              ข้อมูลสำรองของ Hall of Fame
│
├── 📄 CNAME                   โดเมน custom (ratbsc.com)
├── 📄 sitemap.xml             สำหรับ Google Search
├── 📄 robots.txt              สำหรับ Google bot
│
├── 📘 README.md               ไฟล์นี้
├── 📘 HALL_OF_FAME_SETUP.md   คู่มือตั้ง Google Sheet ของ HoF
├── 📘 CALENDAR_SETUP.md       คู่มือตั้ง Sheet ของปฏิทิน
└── 📘 FIND_YOUR_FUTURE_SETUP.md คู่มือตั้ง Sheet ของ FYF
```

---

## ✏️ วิธีอัปเดตเนื้อหา (สำคัญสุด!)

เนื้อหาส่วนใหญ่ของเว็บแก้ผ่าน **Google Sheets** — ไม่ต้องเขียนโค้ดเลย

### 🏆 Hall of Fame
แก้รายชื่อนักเรียน/ผลงานที่เก่ง
👉 ดูคู่มือ: [`HALL_OF_FAME_SETUP.md`](HALL_OF_FAME_SETUP.md)

### 📅 ปฏิทิน (TCAS + กิจกรรมโรงเรียน)
เพิ่ม/ลบ/แก้กิจกรรม — ระบบจะคำนวณ "อีก X วัน" อัตโนมัติ
👉 ดูคู่มือ: [`CALENDAR_SETUP.md`](CALENDAR_SETUP.md)

### 🌟 Find Your Future (ค่าย/ทุน/โอกาส)
แก้รายการค่ายและกิจกรรมที่นักเรียนสนใจสมัคร
👉 ดูคู่มือ: [`FIND_YOUR_FUTURE_SETUP.md`](FIND_YOUR_FUTURE_SETUP.md)

### 👥 รายชื่อกรรมการสภา (`/council`)
แก้ในไฟล์ `council.html` โดยตรง — หา `const COMMITTEES = {` ใน `<script>` ด้านล่าง
```js
const COMMITTEES = {
  '2569': [
    { role: 'ประธานสภานักเรียน', name: 'ชื่อ-สกุล', photo: 'images/council/2569/chair.jpg' },
    // ...
  ],
  '2570': [ /* เพิ่มปีใหม่ */ ]
};
```

> **เพิ่มรูปกรรมการ:** วางไฟล์ใน `images/council/<ปี>/` แล้วอ้างใน `photo`

### 📚 ตารางเรียน (`/schedule`)
ลิงก์ไประบบตารางสอนของโรงเรียน — แก้ที่ `schedule.html` ตรง URL ของแต่ละชั้น

---

## 💻 การพัฒนาเว็บ (สำหรับ Developer)

### ความต้องการ
- ไม่ต้องการ Node.js หรือ build process — เป็น **static HTML/CSS/JS** ล้วน
- มี Python หรือ Live Server ก็พอสำหรับการทดสอบ local

### เปิดทดสอบ local
```bash
# ใช้ Python (มากับ Mac/Linux อยู่แล้ว)
cd /path/to/rb-council
python3 -m http.server 8000
# แล้วเปิด http://localhost:8000
```

หรือใช้ **VS Code + Live Server extension** — คลิก "Go Live" ที่มุมล่างขวา

> ⚠️ **หน้า Hall of Fame, Calendar, FYF ต้องเปิดผ่าน server เท่านั้น** ดับเบิ้ลคลิกไฟล์ HTML ตรงๆ จะใช้ไม่ได้ เพราะ browser block `fetch()` จาก `file://`

### Workflow การแก้
```bash
git pull origin main           # ดึงโค้ดล่าสุดก่อน
# ...แก้ไฟล์ HTML/CSS/JS...
git add .
git commit -m "อธิบายสิ่งที่แก้"
git push origin main           # push ขึ้น GitHub
```

GitHub Pages จะ deploy อัตโนมัติภายใน 1-2 นาทีหลัง push

---

## 🚀 การ Deploy

เว็บ host บน **GitHub Pages** เปลี่ยน URL ไปที่ custom domain `ratbsc.com`

| Component | Service | Cost |
|-----------|---------|------|
| Hosting | GitHub Pages | ฟรี |
| Domain | Cloudflare Registrar | ~$10/ปี |
| DNS | Cloudflare | ฟรี |
| SSL | GitHub Pages (Let's Encrypt) | ฟรี |
| CDN | GitHub + Cloudflare | ฟรี |

### Auto-deploy
ทุก `git push` ไป branch `main` จะ trigger GitHub Pages ให้ build เว็บใหม่อัตโนมัติ — ภายใน 1-2 นาทีเว็บอัปเดต

---

## 🛠️ เทคโนโลยีที่ใช้

- **HTML/CSS/JS ล้วน** — ไม่ใช้ framework
- **Google Sheets** — เป็น CMS สำหรับเนื้อหาแบบ dynamic
- **GitHub Pages** — hosting
- **Cloudflare** — DNS + CDN + Domain Registrar
- **Google Fonts** — `IBM Plex Sans Thai`, `Sora`, `Chonburi`

### Design System
- **สีหลัก:** ชมพู-ม่วง (`#B62477` → `#6248A9`)
- **สีรอง:** ทอง (`#FFB048`) สำหรับ Hall of Fame
- **Layout max-width:** 1180px
- **Responsive breakpoints:** 880px (tablet), 560px (mobile)

ดูรายละเอียดใน [`css/style.css`](css/style.css)

---

## 🎓 การส่งต่อให้รุ่นน้อง

โปรเจกต์นี้ออกแบบมาให้ส่งต่อรุ่นต่อรุ่นได้ — สิ่งที่ต้องส่งต่อ:

### 1. GitHub Organization
ตอนนี้อยู่ที่ [`rb-studentcouncil`](https://github.com/rb-studentcouncil) — เชิญรุ่นน้องเป็น Owner เพิ่มก่อนจบ

### 2. Google Account กลาง
สำหรับเข้าถึง Google Sheets ของ Hall of Fame, Calendar, FYF
> **คำแนะนำ:** ใช้ email กลาง เช่น `studentcouncil.rb@gmail.com` แทน account ส่วนตัว

### 3. Domain `ratbsc.com`
- ซื้อจาก Cloudflare ด้วย account ของสภา
- ต่ออายุประมาณปีละครั้ง (~$10)
- ต้องมีคนรับผิดชอบเปลี่ยน owner เมื่อจบ

### 4. Social Media
- Instagram: `@studentcouncil_rb`
- Facebook: `สภานักเรียน RB`
- รหัสส่งต่อกันเป็นทอดๆ ผ่านฝ่ายประชาสัมพันธ์

### 5. Documentation นี้
README + คู่มือ Setup ทุกไฟล์ — อ่านก่อนเริ่มงาน อย่าลบทิ้ง

---

## 📞 ติดต่อ

- 📷 Instagram: [@studentcouncil_rb](https://www.instagram.com/studentcouncil_rb/)
- 📘 Facebook: [สภานักเรียน RB](https://www.facebook.com/RBStudentCouncil2561)

---

## 📝 License & Credits

เว็บไซต์นี้สร้างขึ้นโดยสภานักเรียนโรงเรียนราชโบริกานุเคราะห์ ปีการศึกษา 2569
สงวนลิขสิทธิ์ — © 2569

> 💡 **รุ่นน้องที่มาดูแลต่อ:** ยินดีต้อนรับ! ถ้าไม่เข้าใจอะไรในนี้ ส่งข้อความหาทาง IG ของสภาได้เลย รุ่นพี่ที่เคยทำพร้อมช่วย 😊
