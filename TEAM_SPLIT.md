# TEAM_SPLIT.md

## Team Members

* นางสาวดาวประกาย เสาร์สิงห์
* นางสาวกชพร วงศ์ใหญ่

---

## Work Allocation

### Student 1: นางสาวดาวประกาย เสาร์สิงห์

* รับผิดชอบ **Auth Service**
* พัฒนาระบบ **Login และ JWT Authentication**
* ออกแบบ **Database schema สำหรับ users**
* ตั้งค่า **Nginx Reverse Proxy และ Rate Limiting**
* ทดสอบ **Authentication API และ Security flow**

### Student 2: นางสาวกชพร วงศ์ใหญ่

* รับผิดชอบ **Task Service**
* พัฒนาระบบ **Task CRUD API**
* พัฒนา **Log Service สำหรับบันทึกเหตุการณ์ในระบบ**
* พัฒนา **Frontend สำหรับ Task Board**
* จัดการ **Docker Compose และการเชื่อมต่อระหว่าง services**

---

## Shared Responsibilities

* ร่วมกันออกแบบ **Microservices Architecture**
* ร่วมกันออกแบบ **Database structure**
* ทดสอบ **End-to-End flow ของระบบ**
* ตรวจสอบ **Security เช่น JWT validation และ Rate Limiting**
* จัดทำ **README, Screenshots และเอกสารประกอบโปรเจกต์**

---

## Reason for Work Split

การแบ่งงานใช้แนวคิด **Service-based responsibility** โดยแบ่งตามหน้าที่ของแต่ละ microservice เพื่อให้แต่ละคนสามารถพัฒนาและทดสอบ service ของตนเองได้อย่างอิสระ จากนั้นจึงนำมารวมกันผ่าน **API Gateway (Nginx)** และ Docker Compose ทำให้การพัฒนาระบบมีความเป็นระบบและลดความซ้ำซ้อนของงาน

---

## Integration Notes

ระบบถูกออกแบบในรูปแบบ **Microservices Architecture** โดยแต่ละ service ทำงานแยกกันแต่เชื่อมต่อผ่าน API

* **Auth Service** ทำหน้าที่ตรวจสอบผู้ใช้และสร้าง JWT Token
* **Task Service** ใช้ JWT Token เพื่อตรวจสอบสิทธิ์ก่อนจัดการข้อมูล Task
* **Log Service** บันทึกเหตุการณ์สำคัญ เช่น login, task creation, task deletion
* **Nginx** ทำหน้าที่เป็น **API Gateway** รับ request จาก client แล้วส่งต่อไปยัง service ที่เกี่ยวข้อง
* **Frontend** ติดต่อกับ backend ผ่าน API Gateway

การทำงานร่วมกันของทั้งสองสมาชิกช่วยให้ระบบสามารถทำงานครบทั้ง **Authentication, Task Management, Logging และ Security Control**
