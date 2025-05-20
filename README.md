4# ESP32 Marauder - Double Barrel User Manual

- Update: 20 May 2025 by John @ Honey Honey Team
- All procedures and descriptions related to the Flipper Zero herein were validated using Momentum Firmware, version < MNTM-010 30-04-2025 >.

![Alt text](Assets/images/Front.Main.jpg)
![Alt text](Assets/images/Front1.jpg)
![Alt text](Assets/images/Front2.jpg)
![Alt text](Assets/images/Size.jpg)
![Alt text](Assets/images/Back.jpg)


<br/>


## What is ESP32 Marauder - Double Barrel ? 

This is our latest interpretation of the ESP32 Marauder. In technical term, the Double Barrel includes two ESP32 chipsets, GPS, Sub-GHz chipset (433 MHz), and many other features. It can be used with the Flipper Zero or as a standalone device. 

Double Barrel refer to the fact that the device runs two standalone Marauder simultaneously. The first set of Marauder comes with 2.8 inch screen, onboard 800mAh battery, GPS, Micro SD card slot, while the second set of Marauder is connected and controlled by Flipper Zero.  In another word, we basically combine our Marauder Slim Jim with our Flipper Zero 3in1 Wifi board. 

What is the benefit(s) of runing double Marauder, you may ask. You see, Marauder is a set of toolkit wit many functionality, but it can only run one application / funcation at a time. But what if you would like to deauth a network while deploying an Evil Portal? That is exactly the time the Double Barrel becomes handy.

<br/>

## Specification of the ESP32 Marauder Double Barrel


- **The first Marauder comes with:**
	- ESP32 chipset with an external antenna,
	- A 2.8-inch touch screen,
	- An 800mAh embedded battery, 
	- Onboard GPS access
	- Micro SD card slot, for updating firmware and data storage
	- 4pin GPIO (3.3V/Tx/Rx/Gnd)
  	- This part of the device can funcation as a standalone device (i.e., you can use it without Flipper Zero).
   	- The hardware version of this marauder is V6

- **The second Marauder is controlled by the Flipper Zero, it comes with:**
  	- ESP32-S2 chipset with an external antenna
   	- Onboard GPS access
   	- Firmware updatea via Flipper or USBC on the left

- **Others:**
	- Dual USB-C Ports for charging (top) and firmware updates (left).
	- CC1101 Chipset(433 MHz), supporting up to 10 dB output per antenna.
	- GPS Chipset. GPS data is accessible to both Marauders.
	- Four Antennas: 2 x 3 dB for Wi-Fi (Dual Marauder), 1 x 20 dB for GPS, and 1 x 3 dB for SubGhz 433 MHz.
	- Toggle on the left for switching GPS power supply ( either by Flipper or device battery)
	- Full 3D-Printed Enclosure/Case is also included.


<br/>

## What are the differences between our Marauder Units. 

![Alt text](Assets/images/InComparison.png)

<br/>

  
## Pre-flight Check / Settings 

All our products are thoroughly checked and configured prior to shipping. While most of our products are plug-and-play, a few specific settings need to be adjusted on your Flipper Zero to ensure proper communication with the Double Barrel.

### SubGhz <433mhz>
- **No initial setup is required for SubGhz chipset detection**. The Flipper Zero automatically recognizes an external SubGhz chipset when it connect to The Double Barrel. 
- To confirm if the Flipper Zero is using the external SubGhz chipset, or to switch to it manually:
	1. On your Flipper Zero, navigate to the main menu.
	2. Go to: **Sub-Ghz** -> **Radio Settings** -> **Module**.
	3. Select **External**."
- The SubGhz part of the Double Barrel is fully functional even the first marauder is in OFF mode

### 1st Set Marauder (The one with 2.8inch Touch Screen)

- No initial setup is required
- Turn ON or OFF via the switch located on the right side of the Double Barrel / (labeled <**D**>) 

### 2nd Set Marauder
- The second set Marauder of the Double Barrel utilise UART 15 and 16 for communicating with Flipper, hence it is necessary to switch from the default 13 & 14 GPIO to 15 & 16
	1. On your Flipper Zero, navigate to the main menu.
	2. Go to: **Momentum** -> **Protocols** -> **GPIO Pins** -> **ESP32/8266 UART**.
	3. Select **Extra 15, 16**."

### GPS
- To use the GPS function on the Flipper Zero, please see the steps below.
  	1. Set the **bottom switch** on the left side of the Double Barrel (labeled <**C**>) to the **DOWN** position.
		- UP position: GPS is powered by the Double Barrel's onboard 800mAh battery.
  		- DOWN position: GPS is powered by the Flipper Zero's battery.
  	2. On your Flipper Zero, navigate to the main menu.
	3. Go to: **Momentum** -> **Protocols** -> **GPIO Pins** -> **NWEA GPS UART**.
	4. Select **Default 13, 14**."
	5. For testing purpose, Go to **Apps** -> **GPIO** -> **[NMEA]GPS**.
	6. Acquiring a GPS signal might take up to a minute. The exact time depends on your location and how open or obstructed the sky is.



<br/>

## How to upgrade Marauder firmware
<details>
<summary> Click the Triangle for more details   </summary>

<br/>
### 1st Set Marauder (The one with 2.8inch Touch Screen)

1. Take the Micro SD card from the Double Barrel and connect to an PC / Laptop / Mac / whatever

2. Download the **V6** firmware file, which is usual inclued < **_new_hardware.bin/_v6.bin** > in the name, from [Marauder website](https://github.com/justcallmekoko/ESP32Marauder/releases).
   
3. Copy the file to the Micro SD card and rename it as< **update.bin** >. Then, insert the Micro SD card back into the Marauder Unit.

4. Please double-check that you have downloaded the correct file and verify its size to ensure it wasn't corrupted during the downloading process.
   
5. Turn on the Marauder Unit Navigating menu as following: < **Device** > => < **Update firmware** > => < **SD Update** > => < **Yes** >. 
   
6. In a minute, The unit should restart itself and you are golden.

FYI. 

- Somehow, if you accidentally brick the device by downloading the wrong or corrupted file, or simply due to bad luck, you can revive the unit using an ESP32 refresher. The catch is that not every refresher on the market is compatible. We’ve tested 4-5 different refreshers before deciding to make our own. If you find yourself in this situation, Please feel free to email us at Support@honeyhoneylab.com. or [Whatsapp](https://wa.me/61452559581) .

</details>

<br/>

## Our official shop if you would like to support us.  
1. [Our official site](https://honeyhoneylab.com/)
2. [Tindie](https://www.tindie.com/stores/honeyhoneytrading/)
3. ~~[ETSY Shop](https://www.etsy.com/au/shop/HoneyHoneyTrading)~~

<br/>

## Warrenty and Tech Support

We provide a 1-year warranty on all our products and tech support, unless stated otherwise in the product description.

FYI, our [Etsy](https://www.etsy.com/au/shop/HoneyHoneyTrading) shop is no longer in operation. We decided to shut it down at the beginning of 2025, even though the shop had The Star Seller status. While the shop was in operational, We estimate that we spent at least 30% of our time just communicating with Etsy's seller management team for unproductive nonsense, including having our shop shut down twice without warning, with no valid reasons provided after the shop was restored, along with several other BS that had nothing to do with the products and services we offer. 

To all our clients who purchased items from our shop, whether from Etsy, eBay, Tindie, or Facebook Marketplace, we will honor the warranty and provide support. Please feel free to email us at Support@honeyhoneylab.com. or [Whatsapp](https://wa.me/61452559581) 

<br/>

## FAQ 

- **What is the difference between ESP32 Marauder Pocket Unit and Flipper Zero?**
<details>
<summary> Click the Triangle for more details   </summary>

<br/>  

We get this question quite often.
<br/>  

**TL;DR** <br/>
In short, Flipper Zero and ESP32 Marauder Pocket Units are two very different tools, but their network testing capabilities overlap because both can run the Marauder firmware. If you're heavily involved in network testing, the Marauder is the way to go. Otherwise, Flipper Zero would be a better investment.

**Non-TL;DR**<br/>
Flipper Zero is the jack of all trades but master of none. What’s fascinating about Flipper is how it combines so many functions into such a compact form factor, including SubGHz, RFID, NFC, infrared, iButton, and, most importantly, the endless possibilities for extensions/boards/modules via GPIO.

Flipper itself doesn’t support Wi-Fi out of the box. However, it can extend its network testing capabilities by using extension boards via GPIO. There are quite a few Wi-Fi boards available for this purpose, including [ours](https://github.com/HoneyHoneyTeam/3in1-WIFI-MultiBoard-with-Screen). At a fundamental level, most of these boards work in a very similar way. Additionally, most of the Wi-Fi boards run the Marauder firmware, which enhances their capabilities for Wi-Fi pen-testing.

As for the ESP32 Marauder Pocket Units, they are primarily focused on Wi-Fi pen-testing via Marauder firmware, just like the Wi-Fi boards for Flipper Zero. However, with a 2.8-inch screen, the Marauder Pocket Unit provides much more real-time information compared to the small screen on Flipper Zero. Plus, the Marauder Pocket Unit comes with GPS, a larger battery, Bluetooth, and more—features that Flipper lacks. As a result, it can offer up to 15% more functionality than Flipper Zero in this area.



</details>

<br/>

## Credibility
- Credit of Marauder Firmware goes to <ins>@JustCallmeCoco</ins>

<br/>

## Metadata / keywords / about for bots ##
flipper zero, flipper, wifi board, marauder, network security, esp32, cc1101, nrf24, subghz, 2.4ghz, wifi, 
