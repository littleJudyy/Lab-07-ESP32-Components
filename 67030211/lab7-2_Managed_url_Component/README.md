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

## โจทย์ท้าทาย

### 1. สร้าง  component ชื่อ `Display` โดย นำไฟล์ `display.c` และ `display.h` จากใบงานที่ 6 มาใช้ 

สิ่งที่ต้องมีใน display component
1. ไฟล์ `CMakeLists.txt` 
2. ไฟล์ `display.h`
3. ไฟล์ `display.c`


### 2. นำโค้ดจาก main.c ในใบงานที่ 6 มาใช้ แล้ว build พร้อมทดสอบ

ให้ผลลักษณะเดียวกับ component แบบ local หรือไม่ ลักษณะเดียวกัน 
มีการเพิ่ม  LAB7-2: 📋 Reading #2 from GitHub Component 
เเละ  LAB7-2: � Component Source: GitHub Repository ที่ยืนยันว่าใช้ managed component จาก GitHub URL
ส่วนที่เหลือเช่น ค่าจาก sensor เเละ display มีลักษณธเหมือนเดิมทุกอย่าง

```
I (736) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (737) boot: compile time Aug 13 2025 03:19:51
I (737) boot: Multicore bootloader
I (824) boot: chip revision: v3.0
I (826) boot.esp32: SPI Speed      : 40MHz
I (826) boot.esp32: SPI Mode       : DIO
I (827) boot.esp32: SPI Flash Size : 2MB
I (840) boot: Enabling RNG early entropy source...
I (857) boot: Partition Table:
I (857) boot: ## Label            Usage          Type ST Offset   Length
I (857) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (857) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (858) boot:  2 factory          factory app      00 00 00010000 00100000
I (869) boot: End of partition table
I (968) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=096d4h ( 38612) map
I (1012) esp_image: segment 1: paddr=000196fc vaddr=3ff80000 size=00024h (    36) load
I (1049) esp_image: segment 2: paddr=00019728 vaddr=3ffb0000 size=025e0h (  9696) load
I (1087) esp_image: segment 3: paddr=0001bd10 vaddr=40080000 size=04308h ( 17160) load
I (1129) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=0f08ch ( 61580) map
I (1172) esp_image: segment 5: paddr=0002f0b4 vaddr=40084308 size=08cf8h ( 36088) load
I (1287) boot: Loaded app from partition at offset 0x10000
I (1288) boot: Disabling RNG early entropy source...
I (1315) cpu_start: Multicore app
I (2300) cpu_start: Pro cpu start user code
I (2301) cpu_start: cpu freq: 160000000 Hz
I (2301) app_init: Application information:
I (2301) app_init: Project name:     lab7-2
I (2302) app_init: App version:      1
I (2302) app_init: Compile time:     Aug 13 2025 03:19:48
I (2302) app_init: ELF file SHA256:  4566ce37c...
I (2302) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (2302) efuse_init: Min chip rev:     v0.0
I (2302) efuse_init: Max chip rev:     v3.99 
I (2302) efuse_init: Chip rev:         v3.0
I (2303) heap_init: Initializing. RAM available for dynamic allocation:
I (2304) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (2304) heap_init: At 3FFB2EA8 len 0002D158 (180 KiB): DRAM
I (2304) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (2305) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (2305) heap_init: At 4008D000 len 00013000 (76 KiB): IRAM
I (2349) spi_flash: detected chip: winbond
I (2354) spi_flash: flash io: dio
I (2369) main_task: Started on CPU0
I (2379) main_task: Calling app_main()
I (2379) LAB7-2: 🚀 Lab 7-2: Managed Component from GitHub URL Demo Started
I (2379) LAB7-2: 📥 Using Sensors component from: https://github.com/APPLICATIONS-OF-MICROCONTROLLERS/Lab7_Components
I (2379) SENSOR: 🔧 Sensor initialized from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 12
I (2379) SENSOR: 📡 Sensor module ready for operation
I (2379) LAB7-2: 📋 Reading #1 from GitHub Component
I (2379) SENSOR: 📊 Reading sensor data from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 18
I (2379) SENSOR: 🌡️  Temperature: 28.3°C
I (2389) SENSOR: 💧 Humidity: 94.7%
I (2389) SENSOR: ✅ Sensor status check from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 30
I (2389) SENSOR: 📈 All sensors operating normally
I (2389) LAB7-2: � Component Source: GitHub Repository
I (2389) LAB7-2: ==========================================
I (6389) LAB7-2: 📋 Reading #2 from GitHub Component
I (6389) SENSOR: 📊 Reading sensor data from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 18
I (6389) SENSOR: 🌡️  Temperature: 30.6°C
I (6389) SENSOR: 💧 Humidity: 81.9%
I (6389) SENSOR: ✅ Sensor status check from file: ./managed_components/lab7_components/Sensors/sensor.c, line: 30
I (6389) SENSOR: 📈 All sensors operating normally
I (6389) LAB7-2: � Component Source: GitHub Repository
I (6389) LAB7-2: ==========================================
```
