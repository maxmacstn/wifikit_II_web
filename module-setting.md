# การตั้งค่าโมดูล

![module_img](/img/module-outer.jpeg ':size=70%')


## สถานะของไฟ LED

<style type="text/css">
.tg  {border-collapse:collapse;border-color:black;border-spacing:0;}
.tg td{background-color:#fff;border-color:black;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:black;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-1wig{font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-hyan{background-color:#059bff;text-align:left;vertical-align:top;color:white;font-weight:bold}
.tg .tg-fymr{border-color:black;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-ncd7{background-color:#5d9600;border-color:black;text-align:left;vertical-align:top;color:white;font-weight:bold}
.tg .tg-0pky{border-color:black;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-fymr">สี</th>
    <th class="tg-fymr">ลักษณะ</th>
    <th class="tg-fymr">ความหมาย</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-ncd7" rowspan="3">เขียว</td>
      <td class="tg-0pky">ติดค้าง*</td>
      <td class="tg-0pky">การทํางานปรกติ</td>
    <tr>
      <td class="tg-0lax">กระพริบ</td>
      <td class="tg-0pky">มีปัญหาในการเชื่อมต่อกับเครอื่งปรับอากาศ</td>
    </tr>
    <tr>
      <td class="tg-0lax">Breathing</td>
      <td class="tg-0pky">Recovery Mode</td>
    </tr>
  </tr>
  <tr>
    <td class="tg-hyan" rowspan="2">น้ำเงิน</td>
    <td class="tg-0pky">ติด</td>
      <td class="tg-0pky">กำลังทำงาน</td>
    <tr>
      <td class="tg-0lax">กระพริบ</td>
      <td class="tg-0pky">อยู่ระหวา่งการเชื่อมต่อเครือข่าย</td>
    </tr>
  </tr>
</tbody>
</table>

## ปุ่มสั่งงาน

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-1wig{font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-1wig">เวลาในการกดปุ่ม (วินาที)</th>
    <th class="tg-1wig">การทำงาน</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">&lt; 2 วินาที</td>
    <td class="tg-0lax">ทดสอบส่ังงาน เปิด/ปิด แอร์</td>
  </tr>
  <tr>
    <td class="tg-0lax">5 - 10</td>
    <td class="tg-0lax">Reset และเข้า Setup Mode (เชื่อมต่อผ่าน Bluetooth)</td>
  </tr>
  <tr>
    <td class="tg-0lax">&gt; 10</td>
    <td class="tg-0lax">Reset และเข้า Setup Mode (เชื่อมต่อผ่าน Wi-Fi AP)</td>
  </tr>
    <tr>
    <td class="tg-0lax">กดปุ่มค้างตอน boot</td>
    <td class="tg-0lax">เข้า Recovery Mode (USB Update)</td>
  </tr>
</tbody>
</table>

## การเปิด/ปิดเสียง Buzzer และไฟ LED
สามารถทำได้ในแอปตามภาพด้านล่าง

<img src="/img/app-settings.jpg" style="max-width:500px;width:100%">

