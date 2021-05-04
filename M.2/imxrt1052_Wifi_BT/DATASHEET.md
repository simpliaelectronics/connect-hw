# Connect IMXRT 1052 Wifi/BT Datasheet

Table of Contents
=================

  * [Functional Description](#functional-description)
    * [Overview](#overview)
	* [Processor features](#processor-features)
    * [Module features](#module-features)
    * [Interfaces](#interfaces)
       * [Block Diagram](#block-diagram)
       * [Peripherals and GPIOs](#peripherals-and-gpios)
	* [Security](#security)
		* [Processor security](#processor-security)
		* [Secure element](#secure-element)
	* [Wireless](#wireless)
		* [Wifi AW-NM191NF](#wifi-aw-nm191nf)
  * [AW-NM191MA module Connector description](#aw-nm191ma-module-connector-description)
    * [M.2 Interface Top Side](#m.2-interface-top-side)
    * [M.2 Interface Bottom Side](#m.2-interface-bottom-side)
	* [40 Pin Expansion Connector](#40-pin-expansion-connector)
	* [Antenna connector](#antenna-connector)
  * [Electrical Specifications](#electrical-specifications)
	* [Operating conditions](#operating-conditions)
	* [Footprint](#footprint)
  * [Mechanical Specifications](#mechanical-specifications)
	* [Dimensions and Weight](#dimensions-and-weight)
	* [Tested Connectors](#tested-connectors)
		* [Key B M.2 connector](#key-b-m.2-connector)
		* [Expansion connector](#expansion-connector)
		* [AW-NM191MA module tested antennas] (#aw-nm191ma-module-tested-antennas)
  * [Compliance](#compliance)
        * [AW-NM191MA module](#aw-nm191ma-module)
  * [Ordering](#ordering)

# Functional Description

## Overview

IMXRT Module is a M.2 2230 format board based in an IMXRT 1052 processor with 16MB SDRAM and 16MB QSPI flash memory. It has a Plug and Trust device to provide a root of trust at IC level. Multiple interfaces such as LCD, USB, CSI, SD and RMII make this module suitable for different applications.

 This module adds wireless communications based on Wifi and BT protocols.

![Connect imxrt1052 Wifi/BT](/M.2/imxrt1052_Wifi_BT/images/connect_imxrt1052_wifi.jpg)

## Processor features

* [IMXRT 1052 processor](https://www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/i-mx-rt-crossover-mcus/i-mx-rt1050-crossover-mcu-with-arm-cortex-m7-core:i.MX-RT1050), based on Arm Cortex-M7 MPCore Platform.
* 3020 CoreMark/1284 DMIPS @ 600 MHz
* Up to 512 kB Tightly Coupled Memory (TCM)
* FreeRTOS and Azure OS support available with MCUXpresso SDK
* Real-time, low-latency response as low as 20 ns
* Industry’s lowest dynamic power with an integrated DC-DC converter
* Low-power run modes at 24 MHz
* Advanced multimedia for GUI and enhanced HMI
	* 2D graphics acceleration engine
	* Parallel camera sensor interface
	* LCD display controller (up to WXGA 1366x768)
	* 3x I2S for high-performance, multichannel audio
* Extensive external memory interface options 
	* NAND, eMMC, QuadSPI NOR Flash, and Parallel NOR Flash (not all available on the module)

![imxrt1052 block diagram](/M.2/imxrt1052_Wifi_BT/images/iMX-RT1050-BD.jpg)

## Module features

* [IMXRT 1052 processor](#processor-features), based on Arm Cortex-M7 MPCore Platform.
* Different options for RAM/FLASH
* [EdgeLock SE050](#secure-element) secure element for secure communicatios.
* M.2 Interface, 2230 Form Factor with expansion connector
* Standard interfaces sucha as GPIO, Ethernet (RMII/MDIO), I2C, SPI, UART
* Camera input via MIPI
* Display output vis parallel LCD
* Wireless communications

## Interfaces

### Block Diagram

![Connect imxrt1052 connect wifi AW-NM191NF block diagram](/M.2/imxrt1052_Wifi_BT/images/block_diagram.jpg)

### Peripherals and GPIOs
SDK software makes the pin configuration described in the table. Other configurations are possible just changing processor pin muxing.

| Type      | Qty  | Input/Output |
|-----------|------|--------------|
| GPIO      | 9    | I/O          |
| ADC       | 2    | I            |
| UART      | 2    | I/O          |
| I2C       | 1    | I/O          |
| CAN       | 2    | I/O          |
| USB       | 2    | I/O          |
| LCD       | 1    | I/O          |
| SD        | 1(1) | I/O          |
| CSI       | 1    | I/O          |
| RMII/MDIO | 1    | I/O          |

(1) SDIO not available in wifi AW-NM191NF version

## Security

### Processor security
Security functions are enabled and accelerated by the following hardware:
* High Assurance Boot (HAB)
* Data Co-Processor (DCP):
	* AES-128, ECB, and CBC mode
	* SHA-1 and SHA-256
	* CRC-32
* Bus Encryption Engine (BEE)
	* AES-128, ECB, and CTR mode
	* On-the-fly QSPI Flash decryption
* True random number generation (TRNG)
* Secure Non-Volatile Storage (SNVS)
	* Secure real-time clock (RTC)
	* Zero Master Key (ZMK)
* Secure JTAG Controller (SJC)

### Secure element
The [EdgeLock SE050](https://www.nxp.com/products/security-and-authentication/authentication/edgelock-se050-plug-trust-secure-element-family-enhanced-iot-security-with-maximum-flexibility:SE050) product family of Plug & Trust devices offers enhanced Common Criteria EAL 6+ based security, for unprecedented protection against the latest attack scenarios. This ready-to-use secure element for IoT devices provides a root of trust at the IC level and delivers real end-to-end security – from edge to cloud – without the need to write security code.

* Common Criteria EAL 6+ certified up to OS level as a safe environment to run pre-installed NXP IoT applets, supporting full encrypted communications and secured lifecycle management
* RSA & ECC functionalities, high key length and future proof curves, for example, brainpool, Edwards, and Montgomery
* AES & 3DES encryption and decryption
* HMAC, CMAC, SHA-1, SHA-224/256/384/512 operations
* HKDF, MIFARE® KDF, PRF (TLS-PSK)
* Support of main TPM functionalities
* Secured flash user memory up to 50kB

By default when a part number with security is selected the SE050C2 version is installed on the module. This art number has support for all crypto algorithms available in the SE050 platform as described in [AN12436](https://www.nxp.com/docs/en/application-note/AN12436.pdf).

## Wireless

### Wifi AW-NM191NF

Manufacturer information can be found [here](https://www.azurewave.com/wireless-modules-nxp.html).

AzureWave Technologies, Inc. introduces the IEEE 802.11b/g/n 1X1WLAN M.2 1216 module AW-NM191NF. The module is targeted to mobile devices including Notebook, TV, Tablet and Gaming Device which need small package module, low power consumption, multiple interfaces and OS support. By using AW-NM191NF, the customers can easily enable the Wi-Fi applications with the benefits of high design flexibility, short development cycle, and quick time-to-market.

Compliance with the IEEE 802.11b/g/n standard, the AW-NM191MA uses Direct Sequence Spread Spectrum (DSSS), Orthogonal Frequency Division Multiplexing (OFDM), DBPSK, DQPSK, CCK and QAM baseband modulation technologies. A high level of integration and full implementation of the power management functions specified in the IEEE 802.11 standard minimize the system power requirements by using AW-NM191NF. In addition to the support of WPA/WPA2 and WEP 64-bit and 128-bit encryption, the AW-NM191NF also supports the IEEE 802.11i security standard through the implementation of Advanced Encryption Standard (AES)/Counter Mode CBC-MAC Protocol (CCMP), Wired Equivalent Privacy (WEP) with Temporal Key Integrity Protocol (TKIP), Advanced Encryption Standard (AES)/Cipher-Based Message Authentication Code (CMAC), and WLAN Authentication and Privacy Infrastructure (WAPI) security mechanisms.

![AW-NM191MA module](/M.2/imxrt1052_Wifi_BT/images/aw-nm191nf_diagram.jpg)

AW-NM191NF supports SDIO or USB2.0 interface for WLAN to the host processor.

AW-NM191NF is suitable for multiple mobile processors for different applications with the support cellular phone co-existence.

AW-NM191NF module adopts NXP’s latest highly-integrated WLAN SoC---88W8801. All the other components are implemented by all means to reach the mechanical specification required.

![AW-NM191MA module block diagram](/M.2/imxrt1052_Wifi_BT/images/aw-nm191nf_block_diagram.jpg)

# AW-NM191MA module Connector description
SDK software makes the pin configuration described in the table. Other configurations are possible just changing processor pin muxing.

## M.2 Interface Top Side

| Pos | Pin        | Function | Processor PIN | Default MUX | Description                              |
|-----|------------|----------|---------------|-------------|------------------------------------------|
| 1   | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 3   | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 5   | DGNG (1)   | POWER    | DGND          |             | System Ground                            |
| 7   | ADC2       | IO       | GPIO_AD_B1_00 | ADC2_IN5    | Analog to Digital Input 2 / Digital GPIO |
| 9   | ADC1       | IO       | GPIO_AD_B0_15 | ADC1_IN4    | Analog to Digital Input 1 / Digital GPIO |
| 11  | POR        | I        | POR           |             | Active Low Reset Input                   |
| 21  | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 23  | USB1_DP    | IO       | USB1.D_P      | USB1.D_P    | Data+ pin USB OTG                        |
| 25  | USB1_DN    | IO       | USB1.D_N      | USB1.D_N    | Data- pin USB OTG                        |
| 27  | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 29  | USB2_DP    | IO       | USB2.D_P      | USB2.D_P    | Data+ pin USB                            |
| 31  | USB2_DN    | IO       | USB2.D_N      | USB2.D_N    | Data+ pin USB                            |
| 33  | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 35  | SD1_CLK    | IO       | NC            |             | Not connected                            |
| 37  | SD1_CD     | I        | NC            |             | Not connected                            |
| 39  | SD1_CMD    | IO       | NC            |             | Not connected                            |
| 41  | SD1_D0     | IO       | NC            |             | Not connected                            |
| 43  | SD1_D1     | IO       | NC            |             | Not connected                            |
| 45  | SD1_D2     | IO       | NC            |             | Not connected                            |
| 47  | SD1_D3     | IO       | NC            |             | Not connected                            |
| 49  | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 51  | CSI_VSYNC  | IO       | GPIO_AD_B1_06 | CSI.VSYNC   | Camera Interface Vertical Sync.          |
| 53  | CSI_HSYNC  | IO       | GPIO_AD_B1_07 | CSI.HSYNC   | Camera Interface Horizontal Sync.        |
| 55  | CSI_PIXCLK | IO       | GPIO_AD_B1_04 | CSI.PIXCLK  | Camera Interface Pixel Clock             |
| 57  | CSI_MCLK   | IO       | GPIO_AD_B1_05 | CSI.MCLK    | Camera Interface Master Clock            |
| 59  | DGND (1)   | POWER    | DGND          |             | System Ground                            |
| 61  | CSI_D2     | IO       | GPIO_AD_B1_15 | CSI.D2      | Camera Interface Data 2                  |
| 63  | CSI_D3     | IO       | GPIO_AD_B1_14 | CSI.D3      | Camera Interface Data 3                  |
| 65  | CSI_D4     | IO       | GPIO_AD_B1_13 | CSI.D4      | Camera Interface Data 4                  |
| 67  | CSI_D5     | IO       | GPIO_AD_B1_12 | CSI.D5      | Camera Interface Data 5                  |
| 69  | CSI_D6     | IO       | GPIO_AD_B1_11 | CSI.D6      | Camera Interface Data 6                  |
| 71  | CSI_D7     | IO       | GPIO_AD_B1_10 | CSI.D7      | Camera Interface Data 7                  |
| 73  | CSI_D8     | IO       | GPIO_AD_B1_09 | CSI.D8      | Camera Interface Data 8                  |
| 75  | CSI_D9     | IO       | GPIO_AD_B1_08 | CSI.D9      | Camera Interface Data 9                  |

(1) Connect to carrier board GND

## M.2 Interface Bottom Side

| Pos | Pin         | Function | Processor PIN | Default MUX | Description                                                        |
|-----|-------------|----------|---------------|-------------|--------------------------------------------------------------------|
| 2   | VIN         | POWER    | +3V3          |             | +3V3 in to power the digital circuits of the module. Up to 500mA   |
| 4   | VIN         | POWER    | +3V3          |             | +3V3 in to power the digital circuits of the module. Up to 500mA   |
| 6   | VIN         | POWER    | +3V3          |             | +3V3 in to power the digital circuits of the module. Up to 500mA   |
| 8   | SNVS        | POWER    | +SNVS         |             | +SNVS to power IMXRT processor                                     |
| 10  | AVIN        | POWER    | +3V3A         |             | +3V3A to power processor’s ADC. Should properly filtered           |
| 20  | WAKEUP      | I        | WAKEUP        |             | Active High wakeup pin, wakes the module from sleep/standby modes  |
| 22  | USB1_VBUS   | I        | USB1.VBUS     | VBUS        | USB1 VBUS Supply                                                   |
| 24  | USB1_OC     | I        | USB1.OC       | OC          | VBUS Over current detection pin                                    |
| 26  | USB1_ID     | I        | USB1.ID       | ID          | Host/Device pin indicator                                          |
| 28  | USB1_PWR    | I        | USB1.PWR      | PWR         | PMIC Control pin for VBUS supply voltage                           |
| 30  | USB2_VBUS   | I        | USB2.VBUS     | VBUS        | USB2 VBUS Supply                                                   |
| 32  | GPIO1       | IO       | GPIO_AD_B0_00 | GPIO1_IO00  | Digital GPIO                                                       |
| 34  | GPIO2       | IO       | GPIO_AD_B0_02 | GPIO1_IO02  | Digital GPIO                                                       |
| 36  | GPIO3       | IO       | GPIO_AD_B0_01 | PWM2_B03    | Digital GPIO and PWM                                               |
| 38  | SWD_IO      | IO       | GPIO_AD_B0_06 | SW.DIO      | SWD debug interface Data pin                                       |
| 40  | SWD_CLK     | IO       | GPIO_AD_B0_07 | SW.CLK      | SWD debug interface Clock pin                                      |
| 42  | CAN1_TX     | IO       | GPIO_SD_B1_02 | CAN1.TX     | CAN Interface Transmit                                             |
| 44  | CAN1_RX     | IO       | GPIO_SD_B1_03 | CAN1.RX     | Can Interface Receive                                              |
| 46  | UART1_RX    | IO       | GPIO_SD_B1_00 | UART1.TX    | UART Interface Receive                                             |
| 48  | UART1_TX    | IO       | GPIO_SD_B1_01 | UART1.RX    | UART Interface Transmit                                            |
| 50  | I2C_SDA     | IO       | GPIO_SD_B1_05 | I2C1_SDA    | I2C Interface Data                                                 |
| 52  | I2C_SCL     | IO       | GPIO_SD_B1_04 | I2C1_SCL    | I2C Interface Clock                                                |
| 54  | MDIO_MDC    | IO       | GPIO_EMC_40   | MDIO.MDC    | SMI Data IO                                                        |
| 56  | MDIO_MDIO   | IO       | GPIO_EMC_41   | MDIO.MDIO   | SMI Clock                                                          |
| 58  | RMII_RX_D0  | IO       | GPIO_B1_04    | RMII.RX_D0  | RMII Interface Receive Data 0                                      |
| 60  | RMII_RX_D1  | IO       | GPIO_B1_05    | RMII.RX_D1  | RMII Interface Receive Data 1                                      |
| 62  | RMII_RX_EN  | IO       | GPIO_B1_06    | RMII.RX_EN  | RMII Interface Receive Enable                                      |
| 64  | RMII_RX_ER  | IO       | GPIO_B1_11    | RMII.RX_ER  | RMII Interface Receive Error                                       |
| 66  | DGND        | POWER    | DGND          |             | System Ground                                                      |
| 68  | RMII_TX_CLK | IO       | GPIO_B1_10    | RMII.TX_CLK | RMII Interface Transmit Clock                                      |
| 70  | RMII_TX_D0  | IO       | GPIO_B1_07    | RMII.TX_D0  | RMII Interface Transmit Data 0                                     |
| 72  | RMII_TX_D1  | IO       | GPIO_B1_08    | RMII.TX_D1  | RMII Interface Transmit Data 1                                     |
| 74  | RMII_TX_EN  | IO       | GPIO_B1_09    | RMII.TX_EN  | RMII Interface Transmit Enable                                     |

## 40 Pin Expansion Connector
| Pos | Pin       | Function | Processor PIN | Default MUX | Description                    |
|-----|-----------|----------|---------------|-------------|--------------------------------|
| 1   | DGND      | POWER    | DGND          |             | System Ground                  |
| 2   | BOOT      | I        | BOOT          |             | Boot Mode pin Selector         |
| 3   | LCD_CLK   | IO       | GPIO_B0_00    | LCDIF.CLK   | LCD Interface Clock            |
| 4   | LCD_D0    | IO       | GPIO_B0_04    | LCDIF.D0    | LCD Interface Data 0           |
| 5   | LCD_D1    | IO       | GPIO_B0_05    | LCDIF.D1    | LCD Interface Data 1           |
| 6   | LCD_D2    | IO       | GPIO_B0_06    | LCDIF.D2    | LCD Interface Data 2           |
| 7   | LCD_D3    | IO       | GPIO_B0_07    | LCDIF.D3    | LCD Interface Data 3           |
| 8   | LCD_D4    | IO       | GPIO_B0_08    | LCDIF.D4    | LCD Interface Data 4           |
| 9   | LCD_D5    | IO       | GPIO_B0_09    | LCDIF.D5    | LCD Interface Data 5           |
| 10  | LCD_D6    | IO       | GPIO_B0_10    | LCDIF.D6    | LCD Interface Data 6           |
| 11  | LCD_D7    | IO       | GPIO_B0_11    | LCDIF.D7    | LCD Interface Data 7           |
| 12  | LCD_D8    | IO       | GPIO_B0_12    | LCDIF.D8    | LCD Interface Data 8           |
| 13  | LCD_D9    | IO       | GPIO_B0_13    | LCDIF.D9    | LCD Interface Data 9           |
| 14  | LCD_D10   | IO       | GPIO_B0_14    | LCDIF.D10   | LCD Interface Data 10          |
| 15  | LCD_D11   | IO       | GPIO_B0_15    | LCDIF.D11   | LCD Interface Data 11          |
| 16  | LCD_D12   | IO       | GPIO_B1_00    | LCDIF.D12   | LCD Interface Data 12          |
| 17  | LCD_D13   | IO       | GPIO_B1_01    | LCDIF.D13   | LCD Interface Data 13          |
| 18  | LCD_D14   | IO       | GPIO_B1_02    | LCDIF.D14   | LCD Interface Data 14          |
| 19  | LCD_D15   | IO       | GPIO_B1_03    | LCDIF.D15   | LCD Interface Data 15          |
| 20  | LCD_VSYNC | IO       | GPIO_B0_03    | LCDIF.VSYNC | LCD Interface Vertical Sync    |
| 21  | LCD_HSYNC | IO       | GPIO_B0_02    | LCDIF.HSYNC | LCD Interface Horizontal Sync  |
| 22  | LCD_EN    | I        | GPIO_B0_01    | CDIF.EN     | LCD Interface Enable           |
| 23  | DGND      | POWER    | DGND          |             | System Ground                  |
| 24  | DGND      | POWER    | DGND          |             | System Ground                  |
| 25  | UART2_TX  | IO       | GPIO_SD_B1_00 | UART4.TX    | UART Interface Transmit        |
| 26  | CAN2_TX   | IO       | GPIO_AD_B0_14 | CAN2.TX     | CAN Interface Transmit         |
| 27  | UART2_RX  | IO       | GPIO_SD_B1_01 | UART4.RX    | UART Interface Receive         |
| 28  | CAN2_RX   | IO       | GPIO_AD_B0_03 | CAN2.RX     | CAN Interface Receive          |
| 29  | GPIO4     | IO       | GPIO_EMC_39   | GPIO3_IO25  | Digital GPIO                   |
| 30  | GPIO5     | IO       | GPIO_AD_B0_09 |  PWM2_A03   | Digital GPIO and PWM           |
| 31  | GPIO6     | IO       | GPIO_B1_15    | GPIO2_IO31  | Digital GPIO                   |
| 32  | GPIO7     | IO       | GPIO_AD_B0_08 |  GPIO1_IO08 | Digital GPIO                   |
| 33  | GPIO8     | IO       | GPIO_B1_13    |  GPIO2_IO29 | Digital GPIO                   |
| 34  | GPIO9     | IO       | PMIC_STBY_REQ |  GPIO5_02   | Digital GPIO                   |
| 35  | RESERVED  |          |               |             |                                |
| 36  | RESERVED  |          |               |             |                                |
| 37  | RESERVED  |          |               |             |                                |
| 38  | RESERVED  |          |               |             |                                |
| 39  | RESERVED  |          |               |             |                                |
| 40  | RESERVED  |          |               |             |                                |

## Antenna connector

The wifi module has two antenna connectors:

![AW-NM191MA module](/M.2/imxrt1052_Wifi_BT/images/aw-nm191nf_diagram.jpg)

The modules has a 1T1R antenna diversity configuration. Antenna can be placed in any of the tow connectors. One or two antennas can be used.

Connector used is I-PEX MHF4.

![I-PEX Connector](/M.2/imxrt1052_Wifi_BT/images/ipex.jpg)

# Electrical Specifications
## Operating conditions

|Parameter                      |Min value | Typical value | Max value | Unit |
|-------------------------------|----------|---------------|-----------|------|
| Input digital +3V3            | 3        | 3.3           | 3.6       | V    |
| Input analog +3V3A            | 3        | 3.3           | 3.6       | V    |
| SNVSS +3V3_SNVS               | 2.4      | 3.3           | 3.6       | V    |
| VCC SDIO (1)                  | 1.85     | 3.15          | 3.15      | V    |
| USB VBUS (2)                  | 4.4      | 5             | 5.5       | V    |
| Current consumption (3)       | TBD      | 230           | 2000      | mA   |
| Analog current consumption (4)| -        | -             | 40        | mA   |
| SNVSS current consumption     | -        | -             | 0.25      | mA   |
| SDIO current consumption (5)  | -        | 200           | -         | mA   |
| USB VBUS current consumption  | -        | 50            | -         | mA   |
| Temperature (6)               | -40      |               | 85        | ºC   |

* (1) This voltage is used for I/O communication with SD card. Two voltages, 3V3 and 1V8, can be selected to enable different speed modes. methods. Consult Reference design documentation for usage example.
* (2) VBUS voltage from USB connector.
* (3) Minimum values depend on power down mode selected and external elements connected to I/O. Value shown for reference purposes only.
* (4) 3.3 V power supply for 12-bit ADC, 600uA typical, 750 uA max, for each ADC. 100 Ohm max loading for touch panel, cause 33 mA current.
* (5) Current supplied by VCC SDIO for I/O, do not connect directly to SD card.
* (6) All parts are rated for industrial temperature range

## Footprint

![Module footprint](/M.2/imxrt1052_Wifi_BT/images/footprint.jpg)

# Mechanical Specifications
## Dimensions and Weight

The Module complies with the mechanical 2230 M.2 specifications.

![Module dimmensions](/M.2/imxrt1052_Wifi_BT/images/mod_size.jpg)

| Dimmension | Value  |
|------------|--------|
| Width      | 26 mm  |
| Height     | 30 mm  |
| Thickness  | 3.8 mm |
| Weight     | TBD    |

3D files available in the repository.

## Tested Connectors

### Key B M.2 conector

| Part number | Manufacturer    | Link |
|-------------|-----------------|------|
| 2199230-3   | TE CONNECTIVITY | [link](https://www.te.com/usa-en/product-2199230-3.html)|

### Expansion connector

| Part number | Manufacturer    | Link |
|-------------|-----------------|------|
| DF40HC(2.5)-40DS-0.4V(58) | Hirose | [link](https://www.hirose.com/product/p/CL0684-4112-9-58)|

### AW-NM191MA module tested antennas

| Brand       | Model             | Ant. Gain (dBi) inc cable loss | Frequency range | Ant. Type | Cable Length (cm) |
|-------------|-------------------|--------------------------------|-----------------|-----------|-------------------|
| MAG. Layers | MSA-4008-25GC1-A2 | 2.98                           | 2400 -  2500    | PIFA      | 15                |

# Ordering
The standard part number are shown in this table. Other configurations are available under demand.

|     Código        |     Descripción                                                                                           |
|-------------------|-----------------------------------------------------------------------------------------------------------|
|     BA10520000    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 0MB RAM 0MB Flash No security chip          |
|     BA10520010    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 0MB RAM 0MB Flash Security chip installed   |
|     BA10520300    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 0MB RAM 4MB Flash No security chip          |
|     BA10520310    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 0MB RAM 4MB Flash Security chip installed   |
|     BA10523400    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 8MB RAM 8MB Flash No security chip          |
|     BA10523410    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 8MB RAM 8MB Flash Security chip installed   |
|     BA10524500    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 16MB RAM 16MB Flash No security chip        |
|     BA10524510    |     M.2 Connect module Processor i.MX RT 1052 WIFI AW-NM191NF 16MB RAM 16MB Flash Security chip installed |
