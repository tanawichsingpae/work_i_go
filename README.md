# 🚀 Work-i-Go Platform

ระบบแพลตฟอร์มตัวกลางระหว่าง **นายจ้าง** และ **ผู้หางาน Part-time**
ออกแบบมาเพื่อช่วยให้การหางานและการจ้างงานเป็นเรื่องง่าย รวดเร็ว และมีประสิทธิภาพ

---

## 📌 ภาพรวมระบบ (System Overview)

Work-i-Go ประกอบด้วย 3 ส่วนหลัก (แยกเป็น 3 Repository):

| ส่วน                     | รายละเอียด                        |
| ------------------------ | --------------------------------- |
| 🌐 Main Web (Frontend)   | เว็บไซต์หลักสำหรับผู้ใช้งานทั่วไป |
| 🧑‍💼 Employer Dashboard | ระบบจัดการงานสำหรับนายจ้าง        |
| 🛠️ Admin Dashboard      | ระบบดูภาพรวมและจัดการระบบ         |

> ⚠️ ทั้ง 3 ส่วนทำงานร่วมกัน แต่ถูกพัฒนาและ deploy แยกกันอย่างอิสระ

---

# 🌐 1. Main Web (Frontend)

> Repository: `work_i_go`

## 📖 รายละเอียด

เว็บไซต์หลักที่ผู้ใช้งานทั่วไป (ผู้หางาน) ใช้สำหรับ:

* ดูงาน Part-time
* สมัครงาน
* ดูรายละเอียดงาน

## 🛠️ เทคโนโลยี

* HTML
* CSS
* JavaScript

## ⚙️ การใช้งาน

```bash
# เปิดใช้งานแบบง่าย
เปิดไฟล์ index.html ผ่าน browser
```

## 🔗 การเชื่อมต่อ

* ส่งข้อมูลไปยัง Employer Dashboard (backend)
* ดึงข้อมูลงานจากระบบ

---

# 🧑‍💼 2. Employer Dashboard

> Repository: `work_i_go_employer`

## 📖 รายละเอียด

ระบบสำหรับ **นายจ้าง** ใช้ในการจัดการงานและผู้สมัคร

## ✨ ฟีเจอร์หลัก

* สร้าง / แก้ไข / ลบ ประกาศงาน
* ดูรายชื่อผู้สมัคร
* จัดการข้อมูลบริษัท/โปรไฟล์

## 🛠️ เทคโนโลยี

* Node.js
* Express.js
* (อาจมี Database เช่น MongoDB / MySQL)

## ⚙️ การติดตั้ง

```bash
npm install
```

## ▶️ การรันระบบ

```bash
npm start
```

## 🔗 การเชื่อมต่อ

* รับข้อมูลจาก Main Web
* ส่งข้อมูลให้ Admin Dashboard สำหรับวิเคราะห์

---

# 🛠️ 3. Admin Dashboard

> Repository: `work_i_go_admin`

## 📖 รายละเอียด

ระบบสำหรับ **ผู้ดูแล (Admin)** ใช้ดูภาพรวมของแพลตฟอร์ม

## ✨ ฟีเจอร์หลัก

* ดูจำนวนผู้ใช้งาน
* ดูจำนวนงานทั้งหมด
* ตรวจสอบกิจกรรมในระบบ
* จัดการข้อมูล (User / Job)

## 🛠️ เทคโนโลยี

* Node.js
* Express.js
* Dashboard UI (เช่น Chart / Table)

## ⚙️ การติดตั้ง

```bash
npm install
```

## ▶️ การรันระบบ

```bash
npm start
```

## 🔗 การเชื่อมต่อ

* ดึงข้อมูลจาก Employer Dashboard
* ใช้สำหรับ Monitoring ระบบทั้งหมด

---

# 🔗 Architecture Overview

```text
[ User ]
   ↓
🌐 Main Web (HTML)
   ↓
🧑‍💼 Employer Dashboard (Node.js)
   ↓
🛠️ Admin Dashboard (Node.js)
```

---

# 📦 โครงสร้างโปรเจคโดยรวม

```bash
workigo/
│
├── workigo_pan/           # Frontend (Main Web)
├── work_i_go_employer/    # Employer Dashboard
└── work_i_go_admin/       # Admin Dashboard
```

---

# 🎯 จุดเด่นของระบบ

* แยก Microservice ชัดเจน (Frontend / Employer / Admin)
* Scale ระบบได้ง่าย
* แยกหน้าที่การทำงานชัดเจน
* รองรับการพัฒนาเพิ่มเติมในอนาคต

---

# 📌 หมายเหตุ

* แต่ละระบบต้องตั้งค่า environment (.env) แยกกัน
* ต้องเชื่อม API ระหว่างแต่ละ service ให้ถูกต้อง

---

# 👨‍💻 ผู้พัฒนา

โปรเจคนี้พัฒนาขึ้นเพื่อการศึกษาและการใช้งานจริงในด้านระบบจัดการงาน Part-time

---
