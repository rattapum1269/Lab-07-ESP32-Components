# Lab 7-3: Custom ESP32 Components (Sensor + Display)

## คำอธิบาย
การทดลองนี้แสดงการสร้าง component ใหม่ด้วยคำสั่ง `idf.py create-component`
สร้าง 2 components:
1. **Sensor Component** - อ่านค่า temperature, humidity และคำนวณ heat index
2. **Display Component** - แสดงผลข้อมูลในรูปแบบตาราง

## โครงสร้างโฟลเดอร์หลังใช้ create-component
```c
lab7-3_esp32_Component/
├── CMakeLists.txt
├── components/
│   ├── sensor/
│   │   ├── CMakeLists.txt
│   │   ├── include/
│   │   │   └── sensor.h
│   │   └── sensor.c
│   └── display/
│       ├── CMakeLists.txt
│       ├── include/
│       │   └── display.h
│       └── display.c
├── main/
│   ├── CMakeLists.txt
│   └── lab7-3.c
├── build/
└── README.md
```

## ผลลัพธ์ที่คาดหวัง
- แสดงข้อความการเริ่มต้น sensor และ display components
- แสดงข้อมูล temperature และ humidity
- คำนวณและแสดง heat index
- แสดงข้อมูลในรูปแบบตารางผ่าน display component
- แสดงสถานะความปลอดภัยตามค่า heat index

## ความแตกต่างจาก Lab อื่นๆ
- **Lab 7-1**: ใช้ local component (โฟลเดอร์ components ของ project)
- **Lab 7-2**: ใช้ managed component จาก GitHub URL
- **Lab 7-3**: สร้าง component ใหม่ด้วย `idf.py create-component` (2 components ในโฟลเดอร์ components/)

## ข้อดีของการใช้โฟลเดอร์ components/
1. **การจัดระเบียบ** - แยก components ออกจาก main application
2. **การทำงานเป็นทีม** - แต่ละคนสามารถรับผิดชอบ component ต่างกันได้
3. **GitHub Collaboration** - ง่ายต่อการ review code และ merge
4. **Modularity** - component สามารถนำไปใช้ใน project อื่นได้
5. **ESP-IDF Standard** - เป็นมาตรฐานของ ESP-IDF project



## การใช้งาน
1. สร้าง components ด้วยคำสั่ง `idf.py create-component`
2. แก้ไขไฟล์ CMakeLists.txt, .h และ .c ของแต่ละ component
3. เขียน main application ที่เรียกใช้ทั้ง 2 components
4. Build และทดสอบด้วย QEMU

```c
I (18446) LAB7-3: 📋 Reading #2
I (18446) DISPLAY: 🧹 Display cleared
I (18446) DISPLAY:
I (18446) ENHANCED_SENSOR: 🌡️  Temperature: 39.90°C
I (18446) ENHANCED_SENSOR: 💧 Humidity: 60.10%
I (18446) LAB7-3: 🔥 Heat Index: 69.95
I (18446) DISPLAY: ┌─────────────────────────────────┐
I (18446) DISPLAY: │        SENSOR DATA DISPLAY      │
I (18446) DISPLAY: ├─────────────────────────────────┤
I (18446) DISPLAY: │ 🌡️  Temperature:  39.90°C      │
I (18446) DISPLAY: │ 💧 Humidity:     60.10%       │
I (18446) DISPLAY: │ 🔥 Heat Index:   69.95        │
I (18446) DISPLAY: └─────────────────────────────────┘
I (18456) DISPLAY: ┌─────────────────────────────────┐
I (18456) DISPLAY: │         SYSTEM STATUS           │
I (18456) DISPLAY: ├─────────────────────────────────┤
I (18456) DISPLAY: │ Status: ✅ Comfortable         │
I (18456) DISPLAY: └─────────────────────────────────┘
I (18456) LAB7-3: ==========================================
I (24456) LAB7-3: 📋 Reading #3
I (24456) DISPLAY: 🧹 Display cleared
I (24456) DISPLAY: 
I (24456) ENHANCED_SENSOR: 🌡️  Temperature: 27.10°C
I (24456) ENHANCED_SENSOR: 💧 Humidity: 65.30%
I (24456) LAB7-3: 🔥 Heat Index: 59.75
I (24456) DISPLAY: ┌─────────────────────────────────┐
I (24456) DISPLAY: │        SENSOR DATA DISPLAY      │
I (24456) DISPLAY: ├─────────────────────────────────┤
I (24456) DISPLAY: │ 🌡️  Temperature:  27.10°C      │
I (24456) DISPLAY: │ 💧 Humidity:     65.30%       │
I (24456) DISPLAY: │ 🔥 Heat Index:   59.75        │
I (24456) DISPLAY: └─────────────────────────────────┘
I (24456) DISPLAY: ┌─────────────────────────────────┐
I (24466) DISPLAY: │         SYSTEM STATUS           │
I (24466) DISPLAY: ├─────────────────────────────────┤
I (24466) DISPLAY: │ Status: ✅ Comfortable         │
I (24466) DISPLAY: └─────────────────────────────────┘
I (24466) LAB7-3: ==========================================
I (30466) LAB7-3: 📋 Reading #4
I (30466) DISPLAY: 🧹 Display cleared
I (30466) DISPLAY: 
I (30466) ENHANCED_SENSOR: 🌡️  Temperature: 32.30°C
I (30466) ENHANCED_SENSOR: 💧 Humidity: 47.90%
I (30466) LAB7-3: 🔥 Heat Index: 56.25
I (30466) DISPLAY: ┌─────────────────────────────────┐
I (30466) DISPLAY: │        SENSOR DATA DISPLAY      │
I (30466) DISPLAY: ├─────────────────────────────────┤
I (30466) DISPLAY: │ 🌡️  Temperature:  32.30°C      │
I (30466) DISPLAY: │ 💧 Humidity:     47.90%       │
I (30466) DISPLAY: │ 🔥 Heat Index:   56.25        │
I (30466) DISPLAY: └─────────────────────────────────┘
I (30466) DISPLAY: ┌─────────────────────────────────┐
I (30466) DISPLAY: │         SYSTEM STATUS           │
I (30466) DISPLAY: ├─────────────────────────────────┤
I (30466) DISPLAY: │ Status: ✅ Comfortable         │
I (30466) DISPLAY: └─────────────────────────────────┘
I (30476) LAB7-3: ==========================================
I (36476) LAB7-3: 📋 Reading #5
I (36476) DISPLAY: 🧹 Display cleared
I (36476) DISPLAY: 
I (36476) ENHANCED_SENSOR: 🌡️  Temperature: 20.40°C
I (36476) ENHANCED_SENSOR: 💧 Humidity: 79.30%
I (36476) LAB7-3: 🔥 Heat Index: 60.05
I (36476) DISPLAY: ┌─────────────────────────────────┐
I (36476) DISPLAY: │        SENSOR DATA DISPLAY      │
I (36476) DISPLAY: ├─────────────────────────────────┤
I (36476) DISPLAY: │ 🌡️  Temperature:  20.40°C      │
I (36476) DISPLAY: │ 💧 Humidity:     79.30%       │
I (36476) DISPLAY: │ 🔥 Heat Index:   60.05        │
I (36476) DISPLAY: └─────────────────────────────────┘
I (36476) DISPLAY: ┌─────────────────────────────────┐
I (36486) DISPLAY: │         SYSTEM STATUS           │
I (36486) DISPLAY: ├─────────────────────────────────┤
I (36486) DISPLAY: │ Status: ✅ Comfortable         │
I (36486) DISPLAY: └─────────────────────────────────┘
I (36486) LAB7-3: ==========================================
```