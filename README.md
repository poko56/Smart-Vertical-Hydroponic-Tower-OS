# 🗼 Smart Vertical Hydroponic Tower OS 

ระบบปฏิบัติการ (OS) สำหรับควบคุมคอนโดปลูกผักไฮโดรโปนิกส์แนวตั้ง (Vertical NFT) ขนาด 1x1 เมตร ออกแบบมาเพื่อบริหารจัดการทรัพยากรน้ำ แสง และอุณหภูมิอัตโนมัติ พร้อมระบบความปลอดภัยป้องกันปั๊มน้ำเสียหาย เพื่อให้พืช (เช่น ผักคอส) เติบโตได้อย่างสมบูรณ์ที่สุด

## ✨ Features (ฟีเจอร์เด่นของระบบ)

* **🌊 Dual-Zone Water Management:** ควบคุมปั๊มน้ำ DC 12V จำนวน 2 ตัว ทำงานแบบสลับพัก (Interval) หรือแยกรดน้ำซ้าย-ขวา เพื่อยืดอายุมอเตอร์
* **🚨 Flow-Watchdog Security:** ใช้เซนเซอร์วัดการไหลของน้ำ (Flow Sensor) 2 ตัว คอยจับตาดูระบบ หากท่อตันหรือปั๊มเสีย ระบบจะตัดไฟและแจ้งเตือนทันที
* **🌡️ Evaporative Auto-Cooling:** ตรวจจับอุณหภูมิน้ำในถังพัก หากเกิน 30°C ระบบจะสั่งเปิดพัดลมเป่าผิวน้ำเพื่อลดอุณหภูมิอัตโนมัติ
* **☀️ Smart Grow Light:** เซนเซอร์ LDR ตรวจจับแสงแดดธรรมชาติ หากฟ้ามืดหรือแสงไม่พอ จะสั่งเปิดหลอดไฟ LED Grow Light ชดเชยให้พืชทันที
* **📱 LINE Notify Alerts:** แจ้งเตือนสถานะฉุกเฉินส่งตรงเข้ามือถือ (เช่น น้ำไม่ไหล, อุณหภูมิสูงเกินกำหนด)
* **📊 Local Monitor:** แสดงผลสถานะการทำงาน (อุณหภูมิ, อัตราการไหล, สถานะปั๊ม) ผ่านหน้าจอ OLED

## 🛠️ Hardware Requirements (อุปกรณ์ที่ใช้)

* **Microcontroller:** ESP32 Board
* **Display:** OLED Display 0.96" (I2C)
* **Sensors:**
    * 2x YF-S201 (Hall Effect Water Flow Sensor)
    * 1x DS18B20 (Water Temperature Sensor - Waterproof)
    * 1x LDR Module (Light Sensor)
* **Actuators & Control:**
    * 2x 12V DC Submersible Water Pumps
    * 1x 12V DC Cooling Fan
    * LED Grow Light
    * 4-Channel Relay Module
* **Power Supply:** Switching Power Supply 12V (Step-down to 5V for ESP32)

## 💻 Tech Stack & Developer Skills

โปรเจกต์นี้และระบบต่างๆ ที่เกี่ยวข้อง ถูกพัฒนาและต่อยอดโดยใช้เทคโนโลยีดังนี้:
* **C / C++** (For ESP32 Embedded Logic)
* **Python**
* **HTML, CSS, JavaScript**
* **C#**
* **Firebase** (Realtime Database & Cloud Functions)

## ⚙️ How it works (หลักการทำงาน)

1.  **Centralized Control:** ESP32 รับไฟ 5V ทำหน้าที่เป็นสมองกล อ่านค่าจากเซนเซอร์ทุกตัวแบบ Real-time
2.  **Smart Irrigation:** สั่งงาน Relay เพื่อจ่ายไฟ 12V ให้ปั๊มน้ำทำงานเป็นรอบเวลา (เช่น ทำงาน 15 นาที พัก 15 นาที) 
3.  **Fail-safe Mechanism:** ทุกครั้งที่ปั๊มทำงาน Flow Sensor ต้องอ่านค่าการไหลได้ หากค่าเป็น 0 ระบบจะตีความว่าเกิดเหตุขัดข้อง สั่งตัดไฟปั๊มเพื่อป้องกันมอเตอร์ไหม้ และส่ง LINE Notify
4.  **Energy Saving:** ระบบทั้งหมดรันผ่าน Switching 12V จบในปลั๊กเดียว ประหยัดไฟและปลอดภัยจากไฟดูด

## 👨‍💻 Let's Connect

**Supachok Hornsombat (Pluem)**
*Computer Technology, Faculty of Industrial Education and Technology, KMITL*

* **Instagram:** [https://www.instagram.com/pokomankrub/](https://www.instagram.com/pokomankrub/)

---
*Built with passion for Smart Farming and IoT Development.*
