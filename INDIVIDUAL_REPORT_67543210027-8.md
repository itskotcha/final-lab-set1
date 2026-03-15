# INDIVIDUAL_REPORT_67543210027-8.md

## ข้อมูลผู้จัดทำ

ชื่อ: นางสาวดาวประกาย เสาร์สิงห์
รหัสนักศึกษา: 67543210027-8

---

## ส่วนที่รับผิดชอบ

ในโปรเจกต์ Final Lab Set 1 ข้าพเจ้ารับผิดชอบในส่วนของ **Auth Service และการจัดการระบบ Authentication** รวมถึงการตั้งค่าด้านความปลอดภัยของระบบ โดยมีหน้าที่หลักดังนี้

* พัฒนา **Auth Service** สำหรับการเข้าสู่ระบบของผู้ใช้
* ออกแบบ **JWT Authentication Flow**
* ออกแบบ **โครงสร้างตาราง users ใน PostgreSQL**
* ตั้งค่า **Nginx Reverse Proxy**
* ตั้งค่า **Rate Limiting เพื่อป้องกัน brute-force login**
* ทดสอบ API สำหรับการเข้าสู่ระบบ

---

## สิ่งที่ได้ลงมือพัฒนาด้วยตนเอง

งานที่ข้าพเจ้าได้ลงมือพัฒนาด้วยตนเองประกอบด้วย

* เขียน API สำหรับ **Login Authentication**
* ใช้ **bcrypt** สำหรับการเข้ารหัสรหัสผ่านของผู้ใช้
* สร้าง **JWT Token** เพื่อใช้สำหรับการยืนยันตัวตนในระบบ
* กำหนด middleware สำหรับ **ตรวจสอบ token ก่อนเข้าถึง API**
* ตั้งค่า **Nginx เป็น API Gateway** เพื่อจัดการ routing ไปยัง service ต่าง ๆ
* ตั้งค่า **Rate Limit** สำหรับ endpoint /api/auth/login
* ทดสอบ API ผ่าน **curl และ browser**

---

## ปัญหาที่พบและวิธีการแก้ไข

ระหว่างการพัฒนาระบบพบปัญหาหลายประการ เช่น

1. ปัญหาการเชื่อมต่อระหว่าง Docker containers

   * แก้ไขโดยตรวจสอบ network ใน docker-compose.yml

2. ปัญหา HTTPS และ certificate ใน Nginx

   * แก้ไขโดยปรับ configuration ให้รองรับ HTTP ในระหว่างการพัฒนา

3. ปัญหาการเรียก API แล้วได้รับ error เช่น

   * 401 Unauthorized
   * 429 Too Many Requests

   วิธีแก้คือ

   * ตรวจสอบ JWT Token
   * ตรวจสอบ Rate Limit configuration ใน Nginx

---

## สิ่งที่ได้เรียนรู้จากงานนี้

จากการทำโปรเจกต์นี้ ข้าพเจ้าได้เรียนรู้เกี่ยวกับ

* การออกแบบ **Microservices Architecture**
* การใช้ **Docker และ Docker Compose** ในการจัดการหลาย services
* การใช้ **JWT Authentication** เพื่อยืนยันตัวตนของผู้ใช้
* การตั้งค่า **Nginx เป็น API Gateway**
* การเพิ่มความปลอดภัยของระบบ เช่น **Rate Limiting และ Logging**

นอกจากนี้ยังได้เรียนรู้การทำงานร่วมกันเป็นทีมและการแบ่งงานตามหน้าที่ของแต่ละ service

---

## แนวทางที่ต้องการพัฒนาต่อใน Set 2

สำหรับ Final Lab Set 2 ข้าพเจ้ามีแนวคิดที่จะพัฒนาระบบเพิ่มเติม เช่น

* ปรับปรุง **ระบบ Logging ให้มีการวิเคราะห์ข้อมูลได้ดีขึ้น**
* เพิ่ม **ระบบ Monitoring สำหรับ services**
* ปรับปรุง **Security ของระบบ เช่น HTTPS และ Token Management**
* พัฒนาระบบให้สามารถ **Deploy บน Cloud Platform**