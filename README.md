### LE202 ### 
## ความรู้ก่อนทำการทดลอง ##
# Digital
  - เป็นข้อมูลทางสัญญาณทางไฟฟ้าที่เป็นตัวเลช
  - 1 digit = 4 bit
# Voltage
  - ไฟฟ้ากระแสสลับ เช่น ไฟบ้าน แรงดัน 230v
  - ไฟฟ้ากระแสตรง เช่น แบตเตอร์รี่ แบตเตอร์รี่Li
# Computer
  - ในอดีตมีขนาดใหญ่มาก เวลาผ่านไปถูกพัฒนาจนมีขนาดล็กเท่าทุกวันนี้
  - ทำหน้าที่เชื่อมอินเตอร์เน็ต
# Program language
  - ภาษาคอมพิวเตอร์ Assembly ภาษาC Python JAVA
  - ปัจจุบันเข้าใจง่ายขึ้นส่งผลให้เขียนโปรแกรมง่ายและโปรแกรมถูกพัฒนาอย่างรวดเร็ว
# Platformio
  - การพัฒนา software รูปแบบใหม่
  - มีวิธีการเขียนแบบเดียวแต่สามารถใช้ได้ใน Microcontroller ได้หลายแบบ
  -  Workframe หลากหลาย
  -  มีบอร์ดหลากหลาย
  -  มีโปรแกรมไลบรารี่ให้ประยุกต์ใช้ได้หลากหลาย
# Iotset1
  - เป็นการเตรียมพร้อมสำหรับการพัฒนา microcontroller
## ตัวอย่างการรันโปรแกรม ## 
# Run ex01
  - เป็นการทดสอบ microcontroller
  - โปรแกรมกำหนดให้ serial port มีความเร็วเท่ากับ 5200 และมีการวนลูปเพิ่มตัวแปรcntไปเรื่อยๆพร้อมกับหร่วงเวลา 1 วินาที
# Run ex02
  - เป็นการหา Wifi รอบตัว
  - โปรแกรมกำหนดให้ ส่วน set up เป็นการเซ็ทให้ไวไฟทำงาน และมีการวนลูปค้นหา Wifi ที่อยู่รอบตัว
# Run ex03
  - เป็นการนำ output แสดงออกไปข้างนอก
  - โปรแกรมกำหนดให้ port 0 เป็น output และมีการวนลูปทุก 0.5 วินาที โดยจะอ่านค่า cnt เป็นเลขคู่ไฟจะเปิดและถ้าเป็นเลขคี่ไฟจะปิด
# Run ex03 reley 
  - นำ Microcontroller มาต่อกับ reley โดย reley จะทำหน้าที่เป็นเหมือนสวิชต์เปิด/ปิด
  - โปรแกรมเหมือนของ Run ex03
# Run ex04
  - เอา input ภายนอกเข้ามาใน Microcontroller
  - โปรแกรมกำหนดให้ที่ port 0 เป็น input และport 2 เป็น output แล้วจะมีการวนลูปโดย digital read อ่านค่าว่าถ้าเท่ากับ 1 = LOW ทำให้ไฟปิด0 และ 0 = HIGH ทำให้ไฟเปิด
  - กรณีเอาสายไฟสีขาวจ่อสีดำจะอ่านค่าได้ 0 = HIGH ทำให้ไฟเปิด
  - กรณีเอาเซนเซอร์แสงมาต่อจะอ่านค่าได้คือ ปิดหน้าเซนเซอร์=ไฟปิด,เปิดหน้าเซนเซอร์=ไฟเปิด
 # Run ex05
  - สร้างเว็บserverผ่านไวไฟ
  - โปรแกรมกำหนดให้คือ ส่วนแรกกำหนดให้ตั้งชื่อไวไฟและรหัสก่อน จากนั้นจะมีการ setup server ให้แสดงผล Hello count
  - แสดงผลโดยเปิดบราวเซอร์แล้ววาง ip address
 # Run ex06
  - สร้างไวไฟ access ขึ้นมาเอง
  - โปรแกรมกำหนดให้คือ ส่วนแรกกำหนดชื่อไวไฟ รหัส gateway subnet ip address ก่อน จากนั้นเตรียม web server กำหนด access point
  - แสดงผลโดยค้นหาไวไฟแล้วใส่รหัส



