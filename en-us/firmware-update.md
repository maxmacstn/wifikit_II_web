# Firmware Update

The WiFiKit-II can be updated via OTA through the app or by connecting to a computer via USB-C.

_Note: After every update, the Buzzer and LED settings will be reset to default values._

## OTA Update
1. Go to the app control page.
2. Tap the top right button to open the menu.
3. Scroll down to the Device Update menu.
4. If a new firmware version is available, tap Start Update and follow the instructions.

## Update via Computer (USB-C)
_Updating via USB-C should only be used if OTA update is not possible._
1. Remove the module from the air conditioner.
2. Enter Recovery Mode by holding the setup button while connecting the module to the computer.
3. The green LED will blink slowly (breathing effect).
4. A drive named `WIFIKIT` will appear on your computer.
5. Copy the `.UF2` firmware file to the `WIFIKIT` drive.
6. The `WIFIKIT` drive will automatically eject after the firmware copy is complete.
7. Reconnect the module to the air conditioner.
