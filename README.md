# ESP32 Marauder - Double Barrel User Manual

![Alt text](Assets/images/Front.with.jpg)
![Alt text](Assets/images/Back.with.jpg)
![Alt text](Assets/images/left.without.jpg)
![Alt text](Assets/images/right.without.jpg)
![Alt text](Assets/images/front.with.no.FZ.jpg)
![Alt text](Assets/images/front.with.laydown.jpg)

> [!NOTE]
> - Update: 19 July 2025 by John @ Honey Honey Team, by adding a FAQ section
> - All procedures and descriptions related to the Flipper Zero herein were validated using Momentum Firmware, version < MNTM-010 30-04-2025 >.




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
  
## Pre-flight Check / Settings Before First Use 

> [!NOTE]
> All our products are thoroughly checked and configured prior to shipping. While most of our products are plug-and-play, a few specific settings need to be adjusted on your Flipper Zero to ensure proper communication with the Double Barrel.

<br/>

### SubGhz <433mhz>
- **No initial setup is required for SubGhz chipset detection**. The Flipper Zero automatically recognizes an external SubGhz chipset when it connect to The Double Barrel. 
- To confirm if the Flipper Zero is using the external SubGhz chipset, or to switch to it manually:
	1. On your Flipper Zero, navigate to the main menu.
	2. Go to: **Sub-Ghz** -> **Radio Settings** -> **Module**.
	3. Select **External**."
- The SubGhz part of the Double Barrel is fully functional even the first marauder is in OFF mode


<br/>

### 1st Set Marauder (The one with 2.8inch Touch Screen)

- No initial setup is required
- Turn ON or OFF via the switch located on the right side of the Double Barrel / (labeled <**D**>)

<br/>

### 2nd Set Marauder

- The second set Marauder of the Double Barrel utilise UART 15 and 16 for communicating with Flipper, hence it is necessary to switch from the default 13 & 14 GPIO to 15 & 16
	1. On your Flipper Zero, navigate to the main menu.
	2. Go to: **Momentum** -> **Protocols** -> **GPIO Pins** -> **ESP32/8266 UART**.
	3. Select **Extra 15, 16**."

<br/>

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

### 1st Set Marauder (The one with 2.8inch Touch Screen)

1. Take the Micro SD card from the Double Barrel and connect to an PC / Laptop / Mac / whatever

2. Download the **V6** firmware file, which is usual inclued < **_new_hardware.bin/_v6.bin** > in the name, from [Marauder website](https://github.com/justcallmekoko/ESP32Marauder/releases).
   
3. Copy the file to the Micro SD card and rename it as< **update.bin** >. Then, insert the Micro SD card back into the Marauder Unit.

4. Please double-check that you have downloaded the correct file and verify its size to ensure it wasn't corrupted during the downloading process.
   
5. Turn on the Marauder Unit Navigating menu as following: < **Device** > => < **Update firmware** > => < **SD Update** > => < **Yes** >. 
   
6. In a minute, The unit should restart itself and you are golden.



### 2nd Set Marauder


> To flash / update the Marauder onto the 2nd Marauder, we suggest using **Google Chrome**.

> On the back of the Double Barrel, you will find **two boot buttons**:
>	- **Middle Button**: This is the boot button for the 1st Marauder (the one with the screen).
>	- **Side/Outer Button**: This button, located closer to the edge/side of the device, is the boot button for the 2nd Marauder with ESP32-S2.


1. Open the Web Flasher called < ESPWebTool > [https://esp.huhn.me/](https://esp.huhn.me).
   
2. To start the 2nd Marauder in Bootloader mode:

	- Use the metal stylus to **press and hold the boot button** for the 2nd Marauder (this is the button closer to the side/edge of the Double Barrel).
	- While still **holding the boot button, connect the USB-C cable** to the Double Barrel.
	- The board will then launch into Bootloader mode instead of starting up normally. You can now release the boot button.

3. Then, navigate to https://esp.huhn.me/,
	- On the webpage, click the [ **Connect** ] button.
 	- A pop-up window will appear, select the option similar to [ **USB Serial (ComXxX) - Paired** ]
  	- Then, click [ **Connect** ] button within the pop-up window.
   
4. Navigate to the Firmware Page:
	- Go to the [ESP32 Marauder firmware update guide:](https://github.com/justcallmekoko/ESP32Marauder/wiki/update-firmware#using-spacehuhn-web-update). 
	- On this page, find / search the section specifically for the "Flipper Zero Wifi Dev Board", like the following picture. This is crucial for getting the correct files.
	- From the "Flipper Zero Wifi Dev Board" section, download the following four (4) files:
	- Bootloader, Partitions, Boot App, Firmware(Look for a .bin file that specifically includes _rev_feather.bin in its name for the firmware)

![Alt text](Assets/images/FlipperZeroWiFiDevBoard.png)

5. Return to the [HESP.huhn.me](https://esp.huhn.me/). You will now select the files you downloaded in the previous steps. Carefully match each downloaded file (Bootloader, Partitions, Boot App, and Firmware) to its correct field on the webpage, as shown in the picture below/adjacent.

![Alt text](Assets/images/ESPWebTool.png)

6. Please double check everything before clicking [ **PROGRAM** ] bottom.
    
7. In a minute then you are golden. 

</details>

<br/>

## Our official shop if you would like to support us.  
1. [ESP32 Marauder - Double Barrel via Tindie](https://www.tindie.com/products/38768/)
2. [ESP32 Marauder - Double Barrel 5G via Tindie](https://www.tindie.com/products/39064/)
3. [Our official site](https://honeyhoneylab.com/)
4. [Tindie](https://www.tindie.com/stores/honeyhoneytrading/)
5. ~~[ETSY Shop](https://www.etsy.com/au/shop/HoneyHoneyTrading)~~

<br/>

## Warrenty and Tech Support

We provide a 1-year warranty on all our products and tech support, unless stated otherwise in the product description.

FYI, our [Etsy](https://www.etsy.com/au/shop/HoneyHoneyTrading) shop is no longer in operation. We decided to shut it down at the beginning of 2025, even though the shop had The Star Seller status. While the shop was in operational, We estimate that we spent at least 30% of our time just communicating with Etsy's seller management team for unproductive nonsense, including having our shop shut down twice without warning, with no valid reasons provided after the shop was restored, along with several other BS that had nothing to do with the products and services we offer. 

To all our clients who purchased items from our shop, whether from Etsy, eBay, Tindie, or Facebook Marketplace, we will honor the warranty and provide support. Please feel free to email us at Support@honeyhoneylab.com. or [Whatsapp](https://wa.me/61452559581) 

<br/>

## FAQ 

## What if the 2nd Marauder controlled by Flipper Zero keeps flashing 0x********** and load*********** (update on 19/07/2025)?

We’ve noticed that the latest Momentum firmware update (Version 11) may cause the second Marauder (connected via Flipper Zero) to repeatedly flash error messages like 0x********** and load***********.

Based on our current testing, this appears to be a compatibility issue between the ESP32-S2-based Marauder and Momentum. The exact root cause is still unknown, and further investigation is needed.

**Temporary Solution:**
We recommend downgrading the second Marauder to firmware version [1.21](Assets/esp32_marauder_v1_2_1_20250207_flipper.bin) or [1.62](Assets/esp32_marauder_v1_6_2_20250531_flipper.bin), which have shown better compatibility.

Based on our testing, Momentum Version 10 (30-04-2025) works well with Marauder firmware 1.2.1. Results from other combinations are currently a mixed bag.

For detailed instructions, please refer to the manual linked below:
Go to the section “How to upgrade Marauder firmware” → “2nd Set Marauder.”

## Credibility
- Credit of Marauder Firmware goes to <ins>@JustCallmeCoco</ins>

<br/>

## Metadata / keywords / about for bots ##
flipper zero, flipper, wifi board, marauder, network security, esp32, cc1101, nrf24, subghz, 2.4ghz, wifi, GPS
