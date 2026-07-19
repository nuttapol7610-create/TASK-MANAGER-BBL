# RM Task Manager Pro

เวอร์ชันแนะนำสำหรับใช้งานจริงมากขึ้น โดยเพิ่ม:

- Login ด้วย Google ผ่าน Firebase Authentication
- Sync ข้อมูลข้าม PC / iPad / iPhone ผ่าน Firestore
- ใช้ Local Storage ได้ก่อน หากยังไม่ใส่ Firebase Config
- Export Excel เป็นไฟล์ `.xls`
- รองรับ PWA / Add to Home Screen
- Responsive สำหรับ PC / iPad เป็นหลัก และ iPhone สำหรับ Key-in งาน
- ไม่มีหัวข้อ "ประเภทงาน" แล้ว

## ไฟล์ในชุดนี้

- `index.html` หน้าเว็บหลัก
- `firebase-config.js` ไฟล์สำหรับใส่ Firebase Config
- `manifest.webmanifest` ไฟล์ PWA
- `service-worker.js` ไฟล์ Offline/PWA พื้นฐาน
- `README.md` คู่มือ

## วิธีทดลองใช้ก่อน โดยยังไม่ต่อ Firebase

1. แตกไฟล์ ZIP
2. เปิด `index.html` ด้วย Browser
3. ใช้งานได้ทันทีแบบ Local Storage

## วิธีนำขึ้น GitHub Pages

1. สร้าง GitHub Repository เช่น `rm-task-manager-pro`
2. Upload ไฟล์ทั้งหมดใน ZIP นี้เข้า Repository
3. ไปที่ `Settings` > `Pages`
4. เลือก `Deploy from a branch`
5. Branch = `main`, Folder = `/root`
6. กด Save

## วิธีต่อ Firebase เพื่อ Sync หลายอุปกรณ์

### 1) สร้าง Firebase Project

1. เข้า Firebase Console
2. Create project
3. ตั้งชื่อ Project เช่น `rm-task-manager-pro`

### 2) เปิด Authentication

1. ไปที่ `Authentication`
2. เลือก `Sign-in method`
3. เปิด `Google`
4. Save

### 3) เปิด Firestore Database

1. ไปที่ `Firestore Database`
2. Create database
3. เลือก Production mode หรือ Test mode เพื่อเริ่มต้น
4. เลือก Location ตามที่ต้องการ

### 4) เพิ่ม Web App

1. ไปที่ Project settings
2. เลือก Add app > Web
3. ตั้งชื่อ App
4. Copy Firebase config
5. นำค่าที่ได้ไปวางแทนค่า `PASTE_...` ในไฟล์ `firebase-config.js`

### 5) ตั้งค่า Authorized domains

ใน Authentication > Settings > Authorized domains ให้เพิ่มโดเมน GitHub Pages ของคุณ เช่น:

`yourname.github.io`

### 6) Firestore Rules ตัวอย่างเริ่มต้น

ใช้ Rules นี้เพื่อให้ User เห็นเฉพาะงานของตัวเอง:

```txt
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId}/tasks/{taskId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

## การ Update ไฟล์ภายหลัง

ถ้าแก้ไฟล์แล้ว ให้ Upload ทับใน GitHub แล้ว Commit Changes จากนั้น GitHub Pages จะใช้ไฟล์ล่าสุด
