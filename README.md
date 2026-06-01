# RB Student Council Website

เว็บไซต์สภานักเรียน โรงเรียนราชโบริกานุเคราะห์ (Ratchaborikanukroh School)

เว็บแบบ static (HTML/CSS/JS ล้วน) ไม่ต้อง build โฮสต์บน GitHub Pages ได้เลย

## หน้าเว็บ

- `index.html` — หน้าแรก / ศูนย์รวม
- `council.html` — ข้อมูลสภานักเรียน
- `hall-of-fame.html` — Hall of Fame (ดึงข้อมูลจาก Google Sheets — ดู `HALL_OF_FAME_SETUP.md`)
- `find-your-future.html` — ข้อมูลเรียนต่อ / TCAS
- `calendar.html` — ปฏิทินวันสำคัญ (ดึงข้อมูลจาก Google Sheets — ดู `CALENDAR_SETUP.md`)
- `schedule.html` — ตารางเรียน (ลิงก์ไประบบตารางสอนของโรงเรียน)

## เปิดดูในเครื่อง (local)

หน้า Hall of Fame ต้องเปิดผ่าน server (ไม่ใช่ดับเบิลคลิก) เพราะอ่านข้อมูลจากไฟล์/ลิงก์ภายนอก

```bash
python3 -m http.server 8000
```
แล้วเปิด http://localhost:8000

## แก้รายชื่อ Hall of Fame

ดูวิธีเชื่อม Google Sheets ในไฟล์ `HALL_OF_FAME_SETUP.md`
ถ้ายังไม่เชื่อม Sheet เว็บจะใช้ข้อมูลตัวอย่างจาก `data/hall.json`

## โครงสร้าง

```
.
├── index.html, council.html, ...   หน้าเว็บแต่ละหน้า
├── css/style.css                   ดีไซน์รวม
├── js/main.js                      เมนู + เอฟเฟกต์
├── data/hall.json                  ข้อมูลสำรอง Hall of Fame
└── HALL_OF_FAME_SETUP.md           คู่มือเชื่อม Google Sheets
```
