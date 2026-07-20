# RM Task Manager Pro - Shared Team Mode v2

เวอร์ชันนี้ปรับตามคำขอล่าสุด:

1. KPI "กำลังดำเนินการ" นับเฉพาะสถานะ `In Progress` เท่านั้น ไม่รวม `Open`
2. Dashboard Eisenhower Matrix แสดงแบบย่อ 1 งานต่อ 1 บรรทัด โดยแสดง:
   - วันที่รับงาน
   - ชื่องาน
   - ชื่อลูกค้า
   - วัน Due
3. ยังเป็น Shared Team Mode เหมือนเดิม ใช้ Firestore path:
   `teams/bbl-team/tasks/{taskId}`

## วิธีใช้งาน

1. แตก ZIP
2. Upload ไฟล์ทั้งหมดขึ้น GitHub ทับไฟล์เดิม
3. Commit Changes
4. หากเคยตั้ง Firestore Rules แบบ Shared Team แล้ว ไม่ต้องเปลี่ยน Rules ใหม่
5. เปิด GitHub Pages แล้วกด Ctrl + F5 เพื่อ Refresh Cache

## Firestore Rules

ใช้ไฟล์ `firestore-rules-shared-team.txt` หากต้องตั้ง Rules ใหม่
