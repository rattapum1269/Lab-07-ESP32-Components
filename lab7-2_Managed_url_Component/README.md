# Lab 7-2: Managed Component from GitHub URL Demo

## คำอธิบาย
การทดลองนี้แสดงการใช้งาน managed component จาก GitHub Repository
ใช้ `Sensors` component จาก https://github.com/APPLICATIONS-OF-MICROCONTROLLERS/Lab7_Components

## ผลลัพธ์ที่คาดหวัง
- แสดงข้อความการเริ่มต้น sensor จาก GitHub component
- แสดงข้อมูล temperature และ humidity ทุก 4 วินาที
- แสดงสถานะการทำงานของ sensor
- แสดงแหล่งที่มาของ component (GitHub Repository)

## ความแตกต่างจาก Lab 7-1
- Lab 7-1: ใช้ local component (ในเครื่อง)
- Lab 7-2: ใช้ managed component จาก GitHub URL

## การใช้งาน
1. เข้าไปในโฟลเดอร์ lab7-2_Managed_url_Component
2. รันคำสั่ง `idf.py build` (จะดาวน์โหลด component จาก GitHub อัตโนมัติ)
3. ทดสอบด้วย QEMU

```c
I (16373) LAB7-2: 📋 Reading #2 from GitHub Component
I (16373) SENSOR: 📊 Reading sensor data from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 18
I (16373) SENSOR: 🌡️  Temperature: 26.6°C
I (16373) SENSOR: 💧 Humidity: 61.8%
I (16373) SENSOR: ✅ Sensor status check from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 30
I (16373) SENSOR: 📈 All sensors operating normally
I (16373) LAB7-2: � Component Source: GitHub Repository
I (16373) LAB7-2: ==========================================
I (20373) LAB7-2: 📋 Reading #3 from GitHub Component
I (20373) SENSOR: 📊 Reading sensor data from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 18
I (20373) SENSOR: 🌡️  Temperature: 30.0°C
I (20373) SENSOR: 💧 Humidity: 87.0%
I (20373) SENSOR: ✅ Sensor status check from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 30
I (20373) SENSOR: 📈 All sensors operating normally
I (20373) LAB7-2: � Component Source: GitHub Repository
I (20373) LAB7-2: ==========================================
I (24373) LAB7-2: 📋 Reading #4 from GitHub Component
I (24373) SENSOR: 📊 Reading sensor data from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 18
I (24373) SENSOR: 🌡️  Temperature: 26.0°C
I (24373) SENSOR: 💧 Humidity: 88.0%
I (24373) SENSOR: ✅ Sensor status check from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 30
I (24373) SENSOR: 📈 All sensors operating normally
I (24373) LAB7-2: � Component Source: GitHub Repository
I (24373) LAB7-2: ==========================================
I (28373) LAB7-2: 📋 Reading #5 from GitHub Component
I (28373) SENSOR: 📊 Reading sensor data from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 18
I (28373) SENSOR: 🌡️  Temperature: 31.2°C
I (28373) SENSOR: 💧 Humidity: 62.8%
I (28373) SENSOR: ✅ Sensor status check from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 30
I (28373) SENSOR: 📈 All sensors operating normally
I (28373) LAB7-2: � Component Source: GitHub Repository
I (28373) LAB7-2: ==========================================
```