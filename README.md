### MINIPROJECT UPTIME MONITOR
### ✨**ฟีเจอร์หลัก**
แยกสถานะเป็น 3 แบบ: ปกติ ช้า และล่ม โดยวัดความเร็วเป็นมิลลิวินาที
เวลาล่ม จะบอกสาเหตุด้วย เช่น Timeout, หาเว็บไม่เจอ หรือเว็บตอบ error 500
พอกลับมาปกติ จะบอกว่าล่มไปนานเท่าไหร่
ส่งรายงานสรุป Uptime เป็นเปอร์เซ็นต์พร้อมกราฟทุกชั่วโมง
และถ้าตัว Monitor หยุดทำงานเอง บอทก็จะแจ้งเตือนว่า Monitor หยุด
### **Demo**
<img width="667" height="491" alt="image" src="https://github.com/user-attachments/assets/b869042a-6031-4fb6-bd0e-4e0398a3d14e" />

### **เครื่องมือที่ใช้ + การทำงานเป็นทีม**
ใช้ภาษา Python กับไลบรารี requests, SQLite, matplotlib สำหรับกราฟ, discord.py สำหรับบอท และ CustomTkinter สำหรับหน้าโปรแกรม

โค้ดทั้งหมดจัดการด้วย Git และ GitHub ทำงานร่วมกับเพื่อนผ่าน repository เดียวกันครับ
### **ข้อจำกัดและการต่อยอด**
"ข้อจำกัดตอนนี้คือโปรแกรมต้องรันบนคอมที่เปิดอยู่ ถ้าปิดคอมการเฝ้าดูก็หยุด

ต่อยอดได้โดยย้ายไปรันบนเซิร์ฟเวอร์ 24 ชั่วโมง, ทำหน้าเว็บ Status Page ให้คนทั่วไปดูได้ หรือเพิ่มการเช็กวันหมดอายุของใบรับรอง SSL ครับ"
## 📁 โครงสร้างโปรเจกต์ (Project Structure)

```
uptime-monitor/
├── data/
│   ├── monitor.db          # ฐานข้อมูล SQLite เก็บผลการเช็กทั้งหมด
│   ├── targets.json        # รายชื่อเว็บ/โฮสต์ที่ต้องการเช็ก
│   ├── chart.png           # กราฟ Response Time สำหรับรายงานรายชั่วโมง
│   ├── error.log           # Log ข้อผิดพลาดของ monitor
│   └── bot_error.log       # Log ข้อผิดพลาดของ bot
├── monitor.py              # สคริปต์หลัก เช็ก HTTP/Ping แล้วบันทึกผลลง DB
├── discord_notify.py       # ส่งแจ้งเตือนและรายงานผ่าน Discord Webhook
├── report.py               # สรุปรายงานรายชั่วโมง และสร้างกราฟ
├── bot.py                  # Discord Bot สำหรับสั่งงาน/จัดการ targets
├── targets_store.py        # อ่าน/เขียนรายการ targets ใน targets.json
├── show_log.py             # ดู Log ย้อนหลังผ่าน Terminal
├── clean_log.py            # ล้าง Log เก่าออกจากฐานข้อมูล
├── config.example.py       # ตัวอย่างไฟล์ Config (คัดลอกไปเป็น config.py)
├── config.py               # ค่า Config จริง + Webhook URL (ต้องสร้างเพิ่ม)
├── requirements.txt        # รายการ Library ที่ต้องติดตั้ง
├── run_monitor.bat         # ไฟล์รันบน Windows
├── .gitignore              # รายการไฟล์ที่ไม่ขึ้น Git
└── README.md               # เอกสารอธิบายโปรเจกต์
```

# Start-Github
- Phootawan Sangmuang
- Student ID: 116810462023-6
