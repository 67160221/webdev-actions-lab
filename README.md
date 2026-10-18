# webdev-actions-lab

เว็บไซต์ Static (HTML / CSS / JavaScript) ที่ Deploy ขึ้น **GitHub Pages** อัตโนมัติด้วย **GitHub Actions** ทุกครั้งที่ push ไปยัง branch `main`

**ผู้จัดทำ:** นายนิรวิทธ์ ใจป้อ | รหัสนิสิต 67160221

🌐 **เว็บไซต์:** https://67160221.github.io/webdev-actions-lab/

---

## โครงสร้างโปรเจกต์

```
webdev-actions-lab/
├── index.html                  หน้าเว็บหลัก (About Me / Skills / Contact)
├── style.css                   สไตล์ของหน้าเว็บ รองรับ Light / Dark mode
├── script.js                   ปุ่ม Say Hello และปุ่ม Toggle Theme
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml          Workflow สำหรับ Deploy ขึ้น GitHub Pages
```

## ฟีเจอร์

- แสดงข้อมูลส่วนตัว 3 ส่วน: **About Me**, **Skills**, **Contact**
- ปุ่ม **Say Hello** กดแล้วข้อความจะสลับไปมา
- ปุ่ม **Dark mode / Light mode** สลับธีมของหน้าเว็บ
- Deploy อัตโนมัติทุกครั้งที่ push ขึ้น `main`

## การทำงานของ Workflow

```
แก้โค้ด → git commit → git push (main) → GitHub Actions → Upload Artifact → Deploy → GitHub Pages
```

Workflow `Deploy Static Website` จะเริ่มทำงานเมื่อ

- มีการ push ไปยัง branch `main`
- กดสั่งรันเองในแท็บ Actions (`workflow_dispatch`)

ขั้นตอนใน Job `deploy` ซึ่งรันบนเครื่อง `ubuntu-latest`

1. **Checkout source code** ดึงโค้ดล่าสุดจาก Repository
2. **Check index.html exists** ตรวจว่ามีไฟล์ `index.html` ก่อน Deploy (`test -f index.html`)
3. **Setup Pages** ตั้งค่า GitHub Pages
4. **Upload static website** แพ็กไฟล์เว็บเป็น Artifact
5. **Deploy to GitHub Pages** นำ Artifact ขึ้นเว็บและได้ URL ของเว็บไซต์

## วิธีรันบนเครื่อง

ไม่ต้องติดตั้งอะไรเพิ่ม เปิดไฟล์ `index.html` ด้วยเบราว์เซอร์ได้เลย

## วิธีอัปเดตเว็บไซต์

```bash
git add .
git commit -m "อธิบายสิ่งที่แก้ไข"
git push origin main
```

จากนั้นรอให้แท็บ **Actions** ขึ้นเครื่องหมายสีเขียว แล้ว Refresh หน้าเว็บ (Ctrl + Shift + R)

## เครื่องมือที่ใช้

HTML · CSS · JavaScript · Git · GitHub · GitHub Actions · GitHub Pages
