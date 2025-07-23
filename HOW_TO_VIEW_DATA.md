# 🔍 วิธีดูข้อมูลใน Database

## 🎯 **วิธีที่ 1: Prisma Studio (แนะนำ - GUI สวยงาม)**

```bash
cd ku-sheet-app/backend
npm run db:studio
```

- **URL**: http://localhost:5555
- **Features**: 
  - ✅ GUI สวยงาม เห็นภาพรวม
  - ✅ แก้ไขข้อมูลได้ (CRUD)
  - ✅ ดู Relations ระหว่างตาราง
  - ✅ Export ข้อมูลได้

---

## 🎯 **วิธีที่ 2: Script ดูข้อมูล (Command Line)**

### **ดูข้อมูลทั้งหมด:**
```bash
npm run db:view
```

### **ดูข้อมูลตารางเฉพาะ:**
```bash
npm run db:view users      # ดูข้อมูล Users
npm run db:view faculties  # ดูข้อมูล Faculties  
npm run db:view subjects   # ดูข้อมูล Subjects
npm run db:view sellers    # ดูข้อมูล Sellers
npm run db:view sheets     # ดูข้อมูล Sheets
npm run db:view orders     # ดูข้อมูล Orders
```

### **ตัวอย่างผลลัพธ์:**
```
🔍 Database Information

✅ Database connected successfully

📊 Table Counts:
👥 Users: 1
🏪 Sellers: 0  
🏛️  Faculties: 10
📚 Subjects: 25
📄 Sheets: 0
🛒 Orders: 0

👥 Users:
┌─────────┬────┬─────────────────────┬──────────────┬─────────┐
│ (index) │ id │ email               │ fullName     │ role    │
├─────────┼────┼─────────────────────┼──────────────┼─────────┤
│ 0       │ 1  │ 'admin@kusheet.com' │ 'Admin User' │ 'ADMIN' │
└─────────┴────┴─────────────────────┴──────────────┴─────────┘
```

---

## 🎯 **วิธีที่ 3: SQLite Command Line**

```bash
# เข้าใช้ SQLite CLI
sqlite3 dev.db

# คำสั่งใน SQLite:
.tables                    # ดูรายชื่อตาราง
.schema                    # ดู schema ทั้งหมด
.schema users              # ดู schema ตาราง users

# Query ข้อมูล:
SELECT * FROM users;       # ดูข้อมูล users ทั้งหมด
SELECT * FROM faculties;   # ดูข้อมูล faculties
SELECT COUNT(*) FROM subjects; # นับจำนวน subjects

# ออกจาก SQLite:
.quit
```

---

## 🎯 **วิธีที่ 4: API Testing**

```bash
# ทดสอบ API endpoints:
curl http://localhost:5000/health
curl http://localhost:5000/api/metadata/faculties
curl http://localhost:5000/api/metadata/subjects/1
curl http://localhost:5000/api/metadata/stats
```

---

## 🎯 **วิธีที่ 5: Database File Location**

```bash
# ตำแหน่งไฟล์ database:
ku-sheet-app/backend/dev.db

# ตรวจสอบขนาดไฟล์:
ls -la dev.db

# ตรวจสอบว่ามีข้อมูลหรือไม่:
sqlite3 dev.db "SELECT COUNT(*) FROM users;"
```

---

## 🛠️ **Commands สำหรับจัดการ Database**

### **Reset & Seed ใหม่:**
```bash
npm run db:reset    # ลบข้อมูลและสร้างใหม่
npm run seed        # เพิ่มข้อมูลเริ่มต้น
```

### **Migrate & Generate:**
```bash
npm run db:migrate  # สร้าง migration ใหม่
npm run db:generate # Generate Prisma client
npm run db:push     # Push schema ไป database
```

---

## 📊 **ข้อมูลปัจจุบันใน Database**

### ✅ **มีข้อมูลแล้ว:**
- **👥 Users**: 1 คน (Admin)
- **🏛️  Faculties**: 10 คณะ
- **📚 Subjects**: 25 วิชา

### ⏳ **ยังไม่มีข้อมูล:**
- **🏪 Sellers**: 0 คน
- **📄 Sheets**: 0 ชิ้น  
- **🛒 Orders**: 0 รายการ

---

## 🔑 **Admin Credentials**

```
📧 Email: admin@kusheet.com
🔒 Password: admin123
```

---

## 🎨 **สรุป - วิธีไหนดีที่สุด?**

### 🥇 **สำหรับ Developer**: 
```bash
npm run db:studio  # GUI สวยงาม, ใช้งานง่าย
```

### 🥈 **สำหรับ Quick Check**:
```bash
npm run db:view    # แสดงสรุปข้อมูลทั้งหมด
```

### 🥉 **สำหรับ SQL Lover**:
```bash
sqlite3 dev.db    # เขียน SQL เอง
```

**เลือกวิธีที่ถนัดได้เลย!** 🎉