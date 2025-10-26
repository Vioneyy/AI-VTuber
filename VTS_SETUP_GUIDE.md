# 🎭 VTube Studio Setup Guide สำหรับ AI VTuber Demo

## 📋 ขั้นตอนการตั้งค่า VTube Studio

### 1. เตรียม VTube Studio
- เปิด VTube Studio
- ไปที่ **Settings (⚙️)** → **Plugins**
- ตรวจสอบว่า **"Allow plugins"** เปิดอยู่ ✅

### 2. เชื่อมต่อ AI VTuber Demo
```bash
# รันสคริปต์ทดสอบการเชื่อมต่อ
python setup_vts_permissions.py
```

### 3. ตั้งค่า Permissions
หลังจากเชื่อมต่อสำเร็จ:

1. ใน VTube Studio ไปที่ **Settings** → **Plugins**
2. คลิกที่ **"AI VTuber Demo"** plugin
3. เปิดใช้งาน **"Load custom images"** ✅
4. คลิก **"Done"** เพื่อบันทึก

### 4. ตรวจสอบ Custom Parameters
ไปที่ **Settings** → **Custom parameters** ควรเห็น:
- `AIVTuber_Mood_Happy`
- `AIVTuber_Mood_Sad` 
- `AIVTuber_Mood_Thinking`
- `AIVTuber_Speaking`
- `AIVTuber_Energy`

## 🔧 การแก้ไขปัญหา

### ❌ Custom Parameters ไม่ปรากฏ
1. ตรวจสอบว่า VTube Studio เปิด "Allow plugins"
2. ลองเชื่อมต่อใหม่ด้วยสคริปต์
3. Restart VTube Studio

### ❌ "Load custom images" ไม่สามารถเปิดได้
1. ตรวจสอบว่าเชื่อมต่อ plugin สำเร็จแล้ว
2. ลอง restart VTube Studio
3. ตรวจสอบว่า plugin ปรากฏในรายการ

### ❌ การเชื่อมต่อล้มเหลว
1. ตรวจสอบว่า VTube Studio เปิดอยู่
2. ตรวจสอบ port 8001 ว่าง
3. ตรวจสอบ firewall settings
4. ลอง restart ทั้ง VTube Studio และ AI VTuber Demo

## 📊 การทดสอบ

### ทดสอบการเชื่อมต่อ
```bash
python test_vts_connection.py
```

### ทดสอบ Custom Parameters
```bash
python setup_vts_permissions.py
# เลือกตัวเลือก 1 เพื่อทดสอบการเชื่อมต่อ
```

## ⚠️ หมายเหตุสำคัญ

1. **Custom Parameters** จะปรากฏใน VTS หลังจากเชื่อมต่อสำเร็จเท่านั้น
2. **"Load custom images"** ต้องอนุญาตผ่าน UI ของ VTube Studio เท่านั้น (ไม่สามารถทำผ่าน API ได้)
3. หาก parameters ไม่ขึ้น ให้ลองเชื่อมต่อใหม่หรือ restart VTube Studio
4. การตั้งค่า permissions จะถูกบันทึกไว้ใน VTube Studio

## 🎯 ขั้นตอนต่อไป

หลังจากตั้งค่าเสร็จแล้ว คุณสามารถ:
1. ใช้งาน AI VTuber Demo ได้เต็มรูปแบบ
2. Custom parameters จะถูกควบคุมโดย AI
3. สามารถโหลดรูปภาพเพิ่มเติมได้ (หากต้องการ)

---

💡 **เคล็ดลับ**: หากมีปัญหา ให้รันสคริปต์ `setup_vts_permissions.py` เพื่อดูสถานะการเชื่อมต่อและได้รับคำแนะนำเพิ่มเติม