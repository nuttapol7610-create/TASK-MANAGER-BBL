# RM Task Manager Pro - Shared Team Mode v3

เวอร์ชันนี้ปรับให้ Dashboard KPI ด้านบนสามารถคลิกเพื่อ Filter ข้อมูลได้แล้ว

## สิ่งที่เพิ่ม/แก้ไข

1. คลิก KPI ด้านบนเพื่อ Filter รายการได้ทั้งตารางและ Eisenhower Matrix
   - งานทั้งหมด
   - กำลังดำเนินการ
   - เสร็จแล้ว
   - เลยกำหนด
   - Due วันนี้
   - Due ภายใน 7 วัน
2. KPI "กำลังดำเนินการ" นับเฉพาะสถานะ `In Progress` เท่านั้น ไม่รวม `Open`
3. Dashboard Eisenhower Matrix ยังแสดงแบบย่อ 1 งานต่อ 1 บรรทัด:
   `รับ: วันที่รับงาน | ชื่องาน | ชื่อลูกค้า | Due: วันที่ส่งงาน`
4. ยังใช้ Shared Team Mode เดิม: `teams/bbl-team/tasks/{taskId}`

## วิธีใช้งาน

1. แตก ZIP
2. Upload ไฟล์ทั้งหมดขึ้น GitHub ทับไฟล์เดิม
3. Commit Changes
4. หากตั้ง Firestore Rules แบบ Shared Team แล้ว ไม่ต้องเปลี่ยน Rules ใหม่
5. เปิด GitHub Pages แล้วกด Ctrl + F5 เพื่อ Refresh Cache
