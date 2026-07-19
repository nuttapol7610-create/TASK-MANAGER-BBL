# RM Task Manager Pro - Shared Team Mode

เวอร์ชันนี้เปลี่ยน Firestore จาก Single User Mode เป็น Shared Team Mode แล้ว

## โครงสร้าง Firestore ใหม่

เดิม:
`users/{userId}/tasks/{taskId}`

ใหม่:
`teams/bbl-team/tasks/{taskId}`

ผลลัพธ์คือ ผู้ใช้ 2 คนหรือมากกว่าที่ Login Google และเปิดลิงก์เดียวกัน จะเห็นงานชุดเดียวกัน และเมื่อคนหนึ่งแก้ไข อีกคนจะเห็น Update แบบ Real-time

## ไฟล์ในชุดนี้

- `index.html`
- `firebase-config.js`
- `manifest.webmanifest`
- `service-worker.js`
- `firestore-rules-shared-team.txt`
- `README.md`

## วิธีนำไปใช้

1. แตก ZIP
2. Upload ไฟล์ทั้งหมดขึ้น GitHub ทับไฟล์เดิม
3. Commit Changes
4. ไป Firebase > Firestore Database > Rules
5. วาง Rules จากไฟล์ `firestore-rules-shared-team.txt`
6. กด Publish
7. เปิดหน้าเว็บ แล้วให้ผู้ใช้แต่ละคน Login Google ด้วย Email ของตัวเอง

## หมายเหตุด้านความปลอดภัย

Rules ชุดนี้อนุญาตให้ผู้ใช้ที่ Login Google แล้วทุกคนที่เข้าถึงเว็บได้ อ่าน/เขียนงานทีมเดียวกันได้ เหมาะสำหรับทีมเล็กที่แชร์ลิงก์เฉพาะภายใน

ถ้าต้องการจำกัดเฉพาะ Email 2 คน ให้แจ้ง Email ที่ต้องการ ผมสามารถทำ Rules แบบ Whitelist ให้ได้
