# การเพิ่มเข้า Home Assistant

โมดูล WiFiKit-II ออกแบบมาเพื่อทำงานกับแอป Tuya Smart / Smart Life โดยเฉพาะ หากต้องการเชื่อมต่อเข้า Home Assistant ก็สามารถทำได้หลายทาง โดยในบทความนี้จะแนะนำวิธีที่ผ่านตัว Local Tuya Integration ซึ่งทำงานได้รวดเร็ว และฟีเจอร์การทำงานครบที่สุด 

บทความนี้แบ่งเป็น 3 ส่วน ประกอบด้วย

1. ตั้งค่า Tuya IoT Platform: ขอรหัสและ Token ต่างๆ จากเว็บ Tuya IoT Platform
2. ลง HACS และติดตั้ง Local Tuya
3. ตั้งค่า Local Tuya Integration

### **สิ่งที่ต้องมีก่อนเริ่มทำการติดตั้ง**

1. Tuya IoT Platform (คนละ Account กับที่ใช้ Log in ในแอป) [สมัครได้จากที่นี่](https://auth.tuya.com/register?)
2. Github Account [สมัครได้จากที่นี่](https://github.com/signup)

<br>

# ตั้งค่า Tuya IoT Platform

## สร้างโปรเจกต์และเชื่อมต่อแอป

1. Log in เข้าที่ Tuya IoT Platform 
2. ที่ Sidebar, ให้กด `Cloud > Project Management`
![](/img/localtuya/iot-1.png)
3. ในหน้า Project Management กด `Create Cloud Project`
4. กรอกข้อมูลดังนี้ และกด Create
    1. **Project Name**: ชื่อโปรเจกต์ `ตั้งอะไรก็ได้`
    2. **Industry:** เลือก `Smart Home`
    3. **Development Method:** เลือก `Smart Home`
    4. **Data Center:** เลือกตามที่ใช้งาน โดยทั่วไปสำหรับ Region ประเทศไทย ให้เลือก `Western America Data Center`
    ![](/img/localtuya/iot-2.png)


5. ในหน้า Configuration Wizard ให้เลือก API ที่ต้องการใช้งาน ดังนี้ หลังจากนั้นกด Authorize
    - IoT Core
    - Industry Basic Service
    - Authorization Token Management
    - Smart Home Basic Service
    - Device Status Notification
    ![](/img/localtuya/iot-3.png)

6. ในหน้าของโปรเจกต์ ไปที่แท็บ `Devices > Link App Account` แล้วกด `Add App Account` QR Code จะปรากฎขึ้นมา ให้สแกนด้วยแอป Tuya Smart หรือ Smart Life ที่ได้ผูกอุปกรณ์ WiFiKit-II ไว้ แล้วทำการกด Confirm Login
    ![](/img/localtuya/iot-4.png)
    ![](/img/localtuya/iot-5.jpg)
        **หากไม่สามารถ Link ได้ แสดงว่า Region ของแอปไม่ตรงกับ Data Center ที่เลือกในข้อ 5 ให้ทำการ Delete Project และสร้างใหม่


7. ในหน้าต่าง Link App Account เลือก `Automatic Link` หลังจากนั้นจะมีข้อความแจ้งขึ้นมาว่าลิงก์อุปกรณ์แล้วทั้งหมดกี่ตัว หากขึ้น 0 Devices อาจจะเป็นไปได้ว่าเลือกผิด Data center
![](/img/localtuya/iot-6.png)

## หาข้อมูล Token และ ID ที่ต้องใช้

มี 3 ค่าที่ต้องใช้เชื่อมต่อกับ LocalTuya ประกอบด้วย

1. `Access ID/Client ID`
2. `Access Secret/Client Secret`
3. `App Account UID`

สำหรับ `Access ID/Client ID` และ `Access Secret/Client Secret` สามารถหาได้จากหน้า Overview
![](/img/localtuya/iot-7.png)

สำหรับ `App Account UID` สามารถหาได้จาก `Devices > Link App Account` 
![](/img/localtuya/iot-8.png)

# ลง HACS และติดตั้ง Integrations

## ติดตั้ง HACS

HACS: Home Assistant Community Store เป็น Add-on ที่ทำให้สามารถติดตั้ง Integretion ได้ง่ายขึ้น 

วิธีการตามด้านล่างนั้นสำหรับท่านที่ติดตั้ง Home Assistant แบบ OS (Supervised) หากคุณติดตั้งด้วยวิธีอื่น เช่น Docker หรือ Core สามารถดูขั้นตอนได้จากเว็บไซต์ของ [HACS](https://www.hacs.xyz/docs/use/download/download/)

1. กดที่ [ลิงก์นี้](https://my.home-assistant.io/redirect/supervisor_addon/?addon=cb646a50_get&repository_url=https%3A%2F%2Fgithub.com%2Fhacs%2Faddons)
    
    หากใช้งานครั้งแรก ให้ทำการใส่ URL ของ Home Assistant ของเรา หลังจากนั้นกด Open link
    
2. จะมีหน้าต่าง **Missing add-on repository** ขึ้นมา ให้ทำการกด **ADD**
3. กด **INSTALL** (ใช้เวลาประมาณ 5 นาที)
4. กด **START** แล้วไปที่หน้า Log ของ Get HACS
![](/img/localtuya/hacs-1.png)

5. รอให้ใน Log ขึ้นว่า `Installation Complete. Remember to restart Home Assistant before you configure it` แสดงว่าติดตั้งเสร็จเรียบร้อย แล้วให้ทำการ **Restart Home Assistant**
![](/img/localtuya/hacs-2.png)

6. หลังจาก Restart เสร็จ ให้ไปที่ `Settings > ADD INTEGRATION > HACS`  
7. ในหน้าของ **Acknowledgement** ให้ติ๊กถูกทุกข้อ แล้วทำการกด **SUBMIT**
8. เชื่อมต่อ Github ตามขั้นตอนที่ขึ้นมา
9. เมื่อเสร็จสิ้น จะมี HACS ขึ้นมาที่ Sidebar
![](/img/localtuya/hacs-3.png)

## ติดตั้ง Local Tuya

Local Tuya คือ Unofficial Integration สำหรับการเชื่อมต่ออุปกรณ์ Tuya เข้า Home Assistant

สำหรับ LocalTuya มีหลายเวอร์ชั่นจากหลายนักพัฒนา โดย**เวอร์ชั่นที่เราใช้จะเป็นของ [xZetsubou](https://github.com/xZetsubou)** เนื่องจากรองรับฟีเจอร์เยอะกว่า และตั้งค่าได้ง่ายกว่าตัวหลักจาก [rospogrigio](https://github.com/rospogrigio/localtuya)

1. กดเมนู HACS จาก Sidebar
2. กดปุ่มเมนูด้านบนขวา เลือก `Custom repositories` 
3. ใส่ข้อมูลตามด้านล่าง กด **ADD** แล้วปิดหน้าต่าง
    - Repository: `https://github.com/xZetsubou/hass-localtuya`
    - Type: `Integration`
4. ค้นหา `localtuya` **เลือกอันที่มาจาก Repository ของ xZetsubou** แล้วกด **DOWNLOAD** รอให้การดาวน์โหลดเสร็จสิ้น
![](/img/localtuya/hacs-4.png)
5. ไปที่ **Settings** แล้วจะเห็นว่ามี HACS/LocalTuya แจ้งเตือนขึ้นมา ให้ทำการ Restart โดยการ **SUBMIT** แล้วรอระบบ Restart

## ติดตั้ง File editor

*File editor ใช้สำหรับการอัปโหลดไฟล์ Config เข้ามา สำหรับท่านที่สามารถใช้ SMB เพื่อเข้าโฟลเดอร์ `config` ของ Home Assistant ได้อยู่แล้ว สามารถข้ามขั้นตอนนี้ได้*

ขั้นตอนการติดตั้ง

1. ไปที่ `Settings > Add-ons`  
2. กด ADD-ON STORE ค้นหา **File Editor** แล้วกด INSTALL เพื่อทำการติดตั้ง
3. หลังจากติดตั้งเสร็จ กด **Show in sidebar** เพื่อให้ขึ้นมาแสดงผลด้านข้าง หลังจากนั้นกด START
![](/img/localtuya/fe-1.png)

# ตั้งค่า Local Tuya Integration

1. โหลดไฟล์ YAML template สำหรับการตั้งค่า WiFiKit-II 
    - <a href="/files/WiFiKIT-II-DK.yaml" download> `WiFiKIT-II-DK.yaml` </a>
    - <a href="/files/WiFiKIT-II-MRSLIM.yaml" download> `WiFiKIT-II-MRSLIM.yaml` </a> 
2. คัดลอกไฟล์ไปวางไว้ในโฟลเดอร์ `custom_components/localtuya/templates/` โดยสามารถใช้วิธีใดก็ได้ หรือจะใช้ File Editor ที่ได้ติดตั้งไปก่อนหน้านี้ในการอัปโหลดไฟล์ไปที่ Folder ดังกล่าวก็ได้เช่นกัน
![](/img/localtuya/localtuya-1.png)

3. ไปที่ `Settings > Device & Services > ADD INTEGRATION` แล้วทำการค้นหา Local Tuya
4. ทำการตั้งค่าโดยใส่ข้อมูลให้ตรงกับที่ได้จาก Tuya IoT Plaform
    - **Data Center Region** สำหรับ Region ไทย เลือก `Western America Data Center`
    - **Access ID / Client ID**
    - **Access Secret / Client Secret**
    - **App Account UID / User ID**

    ![](/img/localtuya/localtuya-2.png)


5. กด CONFIGURE แล้ว `Add new device`  แล้วเลือกอุปกรณ์ที่ค้นหาเจอ
    ![](/img/localtuya/localtuya-3.png)
6. ในหน้า `Configure device connectivity` กด SUBMIT ได้เลย
7. ในหน้า `Configure device entities` กด Use saved template แล้วเลือก Template `WiFiKIT-II-XX.yaml` ที่ได้เพิ่มเข้าไปแล้วกด SUBMIT
8. ไฟล์ Template ได้ทำการจับคู่ฟังก์ชันการทำงานของ Tuya (DP ID) เข้ากับ Entity ของ Home Assistant เรียบร้อย **ให้ทำการกด SUBMIT ไปเรื่อยๆ จนจบขั้นตอนได้เลย** แต่ถ้าอยากปรับค่าเพิ่ม หรือไม่ต้องการเชื่อมต่อฟีเจอร์ไหนเข้า Home Assistant ก็สามารถมาปรับแต่งเพิ่มได้
9. อุปกรณ์ถูกเพิ่มเข้า Home Assistant เรียบร้อย 
10. เพื่อลดปัญหาที่อาจเกิดขึ้น แนะนำให้ทำการ Fix IP ของอุปกรณ์ Tuya ด้วย

![](/img/localtuya/localtuya-4.png)