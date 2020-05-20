# m365charger
Friendly charger for m365. Reads BLE packets from battery status to stop charging as recommended charge level is 20%-80%.

Still a project to be developed. These are main ideas.

Requirements
- SW
  - Read battery status from BLE (already working in python/raspi)
  - Web interface for setting limits and display info (not mandatory)
  - nRF project to read from  M365 https://github.com/heardrwt/Xiaomi-M365-Display/blob/master/main.c
  - Simple python script to read from M365 https://github.com/Emeryth/ReadM365
  
- HW
  - ESP32
  - Relay board
  - DC Step-down 42-5V (XL7015)
  - Display and button and/or led to not depend on wifi?
  
- Expected problems
  - If BT connection shuts down while charging, get a time estimation and continue charging until expected.
  - If no BT connection from the beginning just enable relay and charge forever.


- Some theory from https://randomnerdtutorials.com/esp32-bluetooth-low-energy-ble-arduino-ide/

[image] https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/GATT-BLE-ESP32.png?w=750&ssl=1
https://circuitdigest.com/microcontroller-projects/esp32-ble-client-connecting-to-fitness-band-to-trigger-light

GATT: Profile->Service->Characteristic(Properties,Value,Descriptor)

There are services for Battery monitor, heart rate, ectc, ...

Characteristics are owned by a service. Properties inform about data accessing, value is raw data and descriptor is an uuid.

We will create a BLE client that will connect to m365 server.

