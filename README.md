# Bobby-Car Telemetry PCB

This board should be mounted on the Bobby-Car.

There are 2 CAN bus connectors, pin-compatible with the boardcomputer PCB, and can either be wired:
- after the boardcomputer or
- in-line between the motorcontrollers and the boardcomputer

### Hardware Features
- SN65HVD230 CAN transceiver
- ESP32-WROOM-32E (8MB)
- CH343G USB to UART converter for programming
- ATGM336H-5N31 GNSS
  - supports GPS (US), GLONASS (Russia), Galileo (EU), BeiDou (China), QZSS (Japan)
  - u.FL connector for active antenna 
  - protocol compatible with NEO-6M
  - optional 3V rechargeable battery for fast cold start
- self bomb microSD card slot
- LM75B temperature sensor
- RA-01SH 868MHz LoRa module with two antenna options:
  - integrated u.FL connector for external helical antenna
  - solder jumper to enable the onboard PCB helical antenna
- TPMP2359DJ DC-DC converter (up to 30V input, 3.3V output), so board can be powered by:
  - USB-C connector (5V) or
  - CAN bus (12V-15V)

### Use cases
- Acquire data with onboard sensors and send it to the boardcomputer
  - GPS/GNSS time, position, speed, heading
  - temperature
- Log measurements and CAN bus messages to the microSD card
- GPS geofencing (slowdown/stop, notification to other Bobby-Cars)
- Calibrate wheel circumference by comparing GPS speed with wheel speed
- Send GPS position over LoRa so that:
  - other Bobby-Cars can show nearby Bobby-Cars on a radar display
  - the Bobby-Car can be tracked on a map in case of loss or theft
- Control actuators such as door openers, lights, etc. over LoRa
- Receive LoRa messages from environmental sensors such as weather stations, air quality sensors, etc.
- Send ESP-NOW beacons with the current UTC time to other Bobby-Cars that lack a GNSS receiver
- Upload microSD card data to a cloud service automatically when connected to a Wi-Fi network

![PCB image](documentation/top_view_annotated.png)

### Compliance
- Compliant with RED Directive 2014/53/EU (Radio Equipment Directive)
- Wi-Fi 2.4GHz 802.11b/g/n certified by Wi-Fi Alliance
- FCC ID of ESP32-WROOM-32E: [2AC7Z-ESP32WROOM32E](https://fccid.io/2AC7Z-ESP32WROOM32E)
- Compliant with LVD Directive 2014/35/EU (Low Voltage Directive)
- Compliant with EMC standard EN 55032, EN 55024, EN 61000-6-2, EN 61000-6-4 (Class B)
- Compliant with RoHS Directive 2011/65/EU (Restriction of Hazardous Substances)
- Compliant with REACH Regulation (EC) No 1907/2006 (Registration, Evaluation, Authorisation and Restriction of Chemicals)
- Compliant with WEEE Directive 2012/19/EU (Waste Electrical and Electronic Equipment)
- Compliant with ELV Directive 2011/65/EU (End of Life Vehicle)
- Compliant with ISO 11898-1:2003 CAN bus physical layer and data link layer specifications
