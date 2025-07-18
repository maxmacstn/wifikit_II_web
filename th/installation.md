# การติดตั้ง
> ถึงแม้ว่าตัว WiFiKit-II จะรองรับเครื่องปรับอากาศหลายรุ่น แต่สายที่ใช้ในการเชื่อมต่ออาจจะไม่เหมือนกัน โปรดตรวจสอบและแจ้งรุ่นก่อนสั่งซื้อ

**⚠️คำเตือน⚠️** การติดตั้งโมดูล Wi-Fi จำเป็นต้องแกะเครื่องปรับอากาศออกจนถึงบอร์ดคอนโทรลหลัก **ต้องปิดเบรคเกอร์ไฟฟ้าก่อนติดตั้ง** หากไม่เชี่ยวชาญอาจมีความเสี่ยงที่จะถูกไฟฟ้าช็อกหรือพลัดตกจากที่สูงได้ ชุด Kit นี้เหมาะสำหรับผู้ที่เข้าใจว่าตัวเองทำอะไร ผู้จัดทำไม่รับผิดหากเกิดความเสียหายใด ๆ ขึ้น หากไม่ชำนาญควรว่าจ้างช่างแอร์ให้ติดตั้งให้
## Mitsubishi Mr.Slim
### รุ่นที่รองรับ
เชื่อมต่อกับแอร์ผ่านพอร์ต `CN105` หรือช่องที่เขียนว่า `IT` ที่อยู่บนบอร์ด PCB ของแอร์ หลัก ๆ แล้ว **สามารถใช้กับแอร์ทุกรุ่นตั้งแต่ปี 2008 เป็นต้นไปที่เป็นระบบ Inverter** ส่วนรุ่นอื่น ๆ ที่เป็นแบบ Fixed Speed (เช่น Econo Air) อาจจะใช้ได้เช่นกัน แต่ต้องมีการดัดแปลงตัวบอร์ดเล็กน้อยเพื่อติดตั้งตัว Header และ Resistor ลงบนบอร์ด 

**สามารถตรวจสอบรุ่นที่รองรับได้จาก** [Google Sheets](https://docs.google.com/spreadsheets/d/103b2I2YXNDqoh_jmmbp_vK3BQh_1u48ZsYAht3kVg7E/edit?usp=sharing)

### การติดตั้ง
1. **ปิดเบรกเกอร์**
2. แกะหน้ากากฝาหน้าของแอร์ออก
3. หาช่องต่อ `CN105` หรือ `IT` ตามในภาพ ตำแหน่งของช่องเชื่อมต่ออาจอยู่ในกล่องคอนโทรล​ (กล่องเหล็ก) หรือบอร์ดเล็กด้านหน้า (แล้วแต่รุ่น)
4. นำปลั๊กเสียบเข้าไปที่ช่อง
5. สามารถเก็บโมดูลไว้ที่จุดใดก็ได้ แต่แนะนำว่าไม่ควรใส่ไว้ในกล่องแผงวงจรเนื่องจากจะทำให้ประสิทธิภาพการรับสัญญาณ Wi-Fi ลดลง การติดไว้ภายนอกจะได้สัญญาณดีที่สุด
6. **เปิดเบรกเกอร์** แล้วตรวจสอบไฟสถานะของโมดูล
7. [ทำการเชื่อมต่อเข้าแอป](/setup-tuya.md)

### ตำแหน่งพอร์ท `CN105`
![ins_mrslim](../img/port-ms.jpeg )

### ตำแหน่งการติดตั้งโมดูลที่แนะนำ
![rec_mrslim](../img/ms-recommended-installation.jpg )


## Daikin
### รุ่นที่รองรับ
ตัวโมดูลนั้นสามารถใช้แทน Daikin Wi-Fi Module รุ่น BRPO72C42 และ BRPO72C42-1 ได้ เงื่อนไขการรองรับเหมือนกัน
- แอร์ติดผนังเชื่อมต่อผ่านพอร์ท `S21`*
- แอร์ฝังฝ้า (SkyAir) เชื่อมต่อผ่านพอร์ท `X50A` + `X35A`

*แอร์ที่เป็นติดผนังส่วนใหญ่ **จำเป็นต้องติดอุปกรณ์เสริม (PC Board) เพื่อให้ติดตั้งตัว Wi-Fi Module เข้าไปที่แอร์ได้** ยกเว้นซีรีย์ FTKZ และ FTKM (บางรุ่น) สามารถติดตั้งโมดูลได้เลยโดยที่ไม่ต้องใช้ PC Board

Part number ของตัว PC Board คือ BRP067A42 และ BRP980B42 สามารถสั่งซื้อได้โดยตรงจาก Daikin หรือตัวแทนจำหน่ายใกล้บ้าน

**สามารถตรวจสอบรุ่นที่รองรับได้จาก**
- [Daikin Thai](https://www.daikinthai.com/product/dmobile/appmodel-room-air)
- [Google Sheets](https://docs.google.com/spreadsheets/d/1APodIng-e5hc8Ip3vwsKF282vglZvPuGMtBxKGGDL_g/edit?usp=sharing)
  
### การติดตั้ง
1. **ปิดเบรกเกอร์**
2. แกะหน้ากากฝาหน้าของแอร์ออก
3. สำหรับรุ่นที่ต้องใช้ PC Board ให้ติดตั้งตัว PC Board ลงบน Main Board ของแอร์ก่อน (ตามคู่มือในกล่อง)
4. นำปลั๊กเสียบเข้าไปที่ช่อง `S21` หรือ `X50A` + `X35A`
5. สามารถเก็บโมดูลไว้ในช่องว่างด้่านในแอร์ที่ออกแบบมาเผื่อสำหรับ Wi-Fi Module หรือติดตั้งไว้ด้านนอกแอร์เพื่อให้รับสัญญาณ Wi-Fi ได้ดีที่สุด
6. **เปิดเบรกเกอร์** แล้วตรวจสอบไฟสถานะของโมดูล
7. [ทำการเชื่อมต่อเข้าแอป](/setup-tuya.md)
   
#### ตัวอย่างการติดตั้ง แอร์ติดผนัง
- Daikin FTKQ + PC Board  (S403 -> PC Board -> S21)

![wall-1](../img/installation-ftkq.jpg ':size=50%')
![wall-1-2](../img/DSC04894.jpg ':size=50%') 

- Daikin FTKZ ต่อตรงได้เลย ไม่ต้องใช้ PC Board
  
![wall-2](../img/installation-ftkz.jpg ':size=50%')

#### ตัวอย่างการติดตั้ง แอร์ฝังฝ้า (SkyAir)
![dk_manual](../img/installation-brp.png ':size=50%')

- Daikin Cassette FBA

![wall-3](../img/installation-fba.jpg  ':size=50%')

### ขั้นตอนถัดไป [เชื่อมต่อเข้าแอป](/th/setup-tuya)

