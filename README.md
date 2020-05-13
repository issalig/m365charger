# m365charger
Friendly charger for m365. Reads BLE packets from battery status to stop charging as recommended charge level is 20%-80%.

Still a project to be developed. These are main ideas.

Requirements
- SW
  - Read battery status from BLE (already working in python/raspi)
  - Web interface for setting limits and display info (not mandatory)

- HW
  - ESP32
  - Relay board
  - DC Step-down 42-5V (XL7015)
  - Display and button and/or led to not depend on wifi?
  
- Expected problems
  - If BT connection shuts down while charging, get a time estimation and continue charging until expected.
  - If no BT connection from the beginning just enable relay and charge forever.
