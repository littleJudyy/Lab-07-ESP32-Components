# Lab 7-1: Local Component Demo

## คำอธิบาย
การทดลองนี้แสดงการใช้งาน component ที่มีอยู่ในโฟลเดอร์ `components/Sensors/` ของ project

## สรุปคำสั่งที่ใช้ และผลลัพธ์ที่ได้
cd lab7-1_Managed_Local_Component เข้าไปในโฟด์์เดอร์ lab7-1_Managed_Local_Component
ผลลัพท์ที่ได้คือ 
```
root@cf6391ee6c29:/project/lab7-1_Managed_Local_Component# 
```

. $IDF_PATH/export.sh  export environment เพื่อให้สามารถเรียกใช้ idf tools ได้
ผลลัพท์ที่ได้คือ
```
root@cf6391ee6c29:/project/lab7-1_Managed_Local_Component# . $IDF_PATH/export.sh
Checking "python3" ...
Python 3.12.3
"python3" has been detected
Activating ESP-IDF 6.0
Setting IDF_PATH to '/opt/esp/idf'.
* Checking python version ... 3.12.3
* Checking python dependencies ... OK
* Deactivating the current ESP-IDF environment (if any) ... OK
* Establishing a new ESP-IDF environment ... OK
* Identifying shell ... bash
* Detecting outdated tools in system ... OK - no outdated tools found
* Shell completion ... Autocompletion code generated

Done! You can now compile ESP-IDF projects.
Go to the project directory and run:
idf.py build 
```
idf.py set-target esp32 กำหนด target ESP32

idf.py build คือการ Build project 

idf.py qemu moniter รัน QEMU (สำหรับการทดสอบ)
ผลลัพท์ที่ได้คือ 
```
I (2387) LAB7-1: 🚀 Lab 7-1: Local Component Demo Started
I (2387) SENSOR: 🔧 Sensor initialized from file: /project/components/Sensors/sensor.c, line: 12
I (2387) SENSOR: 📡 Sensor module ready for operation
I (2387) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (2387) SENSOR: 🌡️  Temperature: 35.0°C
I (2397) SENSOR: 💧 Humidity: 72.9%
I (2397) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (2397) SENSOR: 📈 All sensors operating normally
I (2397) LAB7-1: ----------------------------
I (5397) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (5397) SENSOR: 🌡️  Temperature: 34.3°C
I (5397) SENSOR: 💧 Humidity: 96.9%
I (5397) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (5397) SENSOR: 📈 All sensors operating normally
I (5397) LAB7-1: ----------------------------
```

## โจทย์ท้าทาย

### 1. สร้าง  component ชื่อ `Display` โดย นำไฟล์ `display.c` และ `display.h` จากใบงานที่ 6 มาใช้ 

สิ่งที่ต้องมีใน display component
1. ไฟล์ `CMakeLists.txt` 
2. ไฟล์ `display.h`
3. ไฟล์ `display.c`


### 2. นำโค้ดจาก main.c ในใบงานที่ 6 มาใช้ แล้ว build พร้อมทดสอบ
```
rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6372
load:0x40078000,len:15928
load:0x40080400,len:3880
entry 0x40080638
I (759) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (760) boot: compile time Aug 13 2025 02:43:28
I (760) boot: Multicore bootloader
I (857) boot: chip revision: v3.0
I (859) boot.esp32: SPI Speed      : 40MHz
I (859) boot.esp32: SPI Mode       : DIO
I (859) boot.esp32: SPI Flash Size : 2MB
I (873) boot: Enabling RNG early entropy source...
I (886) boot: Partition Table:
I (886) boot: ## Label            Usage          Type ST Offset   Length
I (887) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (887) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (887) boot:  2 factory          factory app      00 00 00010000 00100000
I (896) boot: End of partition table
I (973) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=095c4h ( 38340) map
I (1014) esp_image: segment 1: paddr=000195ec vaddr=3ff80000 size=00024h (    36) load
I (1048) esp_image: segment 2: paddr=00019618 vaddr=3ffb0000 size=025e0h (  9696) load
I (1089) esp_image: segment 3: paddr=0001bc00 vaddr=40080000 size=04418h ( 17432) load
I (1131) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=0f044h ( 61508) map
I (1172) esp_image: segment 5: paddr=0002f06c vaddr=40084418 size=08be8h ( 35816) load
I (1303) boot: Loaded app from partition at offset 0x10000
I (1304) boot: Disabling RNG early entropy source...
I (1328) cpu_start: Multicore app
I (2314) cpu_start: Pro cpu start user code
I (2315) cpu_start: cpu freq: 160000000 Hz
I (2316) app_init: Application information:
I (2316) app_init: Project name:     lab7-1
I (2316) app_init: App version:      1
I (2316) app_init: Compile time:     Aug 13 2025 02:43:25
I (2317) app_init: ELF file SHA256:  ac48cf6f4...
I (2317) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (2317) efuse_init: Min chip rev:     v0.0
I (2317) efuse_init: Max chip rev:     v3.99 
I (2317) efuse_init: Chip rev:         v3.0
I (2318) heap_init: Initializing. RAM available for dynamic allocation:
I (2319) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (2320) heap_init: At 3FFB2EA8 len 0002D158 (180 KiB): DRAM
I (2320) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (2320) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (2320) heap_init: At 4008D000 len 00013000 (76 KiB): IRAM
I (2359) spi_flash: detected chip: winbond
I (2365) spi_flash: flash io: dio
I (2377) main_task: Started on CPU0
I (2387) main_task: Calling app_main()
I (2387) LAB7-1: 🚀 Lab 7-1: Local Component Demo Started
I (2387) SENSOR: 🔧 Sensor initialized from file: /project/components/Sensors/sensor.c, line: 12
I (2387) SENSOR: 📡 Sensor module ready for operation
I (2387) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (2387) SENSOR: 🌡️  Temperature: 35.0°C
I (2397) SENSOR: 💧 Humidity: 72.9%
I (2397) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (2397) SENSOR: 📈 All sensors operating normally
I (2397) LAB7-1: ----------------------------
I (5397) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (5397) SENSOR: 🌡️  Temperature: 34.3°C
I (5397) SENSOR: 💧 Humidity: 96.9%
I (5397) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (5397) SENSOR: 📈 All sensors operating normally
I (5397) LAB7-1: ----------------------------
I (8397) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (8397) SENSOR: 🌡️  Temperature: 35.2°C
I (8397) SENSOR: 💧 Humidity: 70.6%
I (8397) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (8397) SENSOR: 📈 All sensors operating normally
I (8397) LAB7-1: ----------------------------
---
```