<h1 align="center">🔐 Awesome Connected Things Security Resources</h1>
<p align="center">A curated repository of IoT, Embedded, Industrial & Automotive, Core Tech security knowledge.</p>

<p align="center">
  <img src="/docs/images/banner.png" />
</p>

<p align="center">
  <a href="https://awesome.re">
    <img src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" alt="Awesome Badge">
  </a>
</p>

<p align="center">
  <a href="https://github.com/V33RU/awesome-connected-things-sec/stargazers">
    <img src="https://img.shields.io/github/stars/V33RU/awesome-connected-things-sec.svg" />
  </a>
  <a href="https://github.com/V33RU/awesome-connected-things-sec/network">
    <img src="https://img.shields.io/github/forks/V33RU/awesome-connected-things-sec.svg" />
  </a>
  <a href="https://github.com/V33RU/awesome-connected-things-sec/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/V33RU/awesome-connected-things-sec.svg"/>
  </a>
    <img src="https://img.shields.io/github/last-commit/V33RU/awesome-connected-things-sec?style=flat-square" alt="Last Updated">
</p>

<p align="center">
  <a href="https://github.com/V33RU/awesome-connected-things-sec/blob/master/docs/ICS/Industrial-Control-Systems.md">
    <img src="https://img.shields.io/badge/ICS%20Security-%F0%9F%94%8D-blue?style=for-the-badge">
  </a>
  <a href="https://github.com/V33RU/awesome-connected-things-sec/blob/master/docs/Automotive/automotive-security.md">
    <img src="https://img.shields.io/badge/Automotive%20Security-%F0%9F%9A%97-green?style=for-the-badge">
  </a>
    <a href="https://github.com/V33RU/awesome-connected-things-sec/blob/master/docs/awesome-collection.md">
    <img src="https://img.shields.io/badge/Awesome-List%F0%9F%A4%9D-purple?style=for-the-badge">
  </a>
  <a href="https://github.com/V33RU/awesome-connected-things-sec/blob/master/CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/Contribute-%F0%9F%A4%9D-purple?style=for-the-badge">
  </a>
</p>

---

## Table of Contents

- [Hardware Attacks](#hardware-attacks)
  - [Fundamentals](#fundamentals)
  - [Interface Attacks](#interface-attacks)
    - [UART](#uart)
    - [JTAG](#jtag)
    - [SWD (Serial Wire Debug)](#swd-serial-wire-debug)
    - [SPI](#spi)
    - [I2C](#i2c)
    - [TPM](#tpm)
  - [Memory Extraction](#memory-extraction)
    - [eMMC](#emmc)
  - [Side-Channel and Fault Injection](#side-channel-and-fault-injection)
    - [Fundamentals](#fundamentals-1)
    - [Glitching Attacks](#glitching-attacks)
    - [Power Analysis](#power-analysis)
- [Wireless Protocols](#wireless-protocols)
  - [RF Fundamentals](#rf-fundamentals)
  - [Bluetooth / BLE](#bluetooth-ble)
    - [Fundamentals](#fundamentals-2)
    - [Exploitation Techniques](#exploitation-techniques)
    - [Vulnerability Research](#vulnerability-research)
    - [Conference Talks](#conference-talks)
    - [Tools - Software](#tools-software)
    - [Tools - Hardware](#tools-hardware)
    - [Tools](#tools)
    - [Hacking Bluetooth Coffee Machines](#hacking-bluetooth-coffee-machines)
  - [Zigbee / Z-Wave](#zigbee-z-wave)
    - [Fundamentals](#fundamentals-3)
    - [Exploitation](#exploitation)
    - [Tools - Software](#tools-software-1)
    - [Tools - Hardware](#tools-hardware-1)
  - [LoRa / LoRaWAN](#lora-lorawan)
    - [Fundamentals](#fundamentals-4)
    - [Exploitation](#exploitation-1)
    - [Tools](#tools-1)
  - [Matter / Thread](#matter-thread)
    - [Fundamentals](#fundamentals-5)
    - [Security Research](#security-research)
  - [Cellular (GSM/LTE/5G)](#cellular-gsmlte5g)
    - [Fundamentals](#fundamentals-6)
    - [Exploitation](#exploitation-2)
    - [Tools](#tools-2)
  - [NFC/RFID](#nfcrfid)
  - [DECT (Digital Enhanced Cordless Telecommunications)](#dect-digital-enhanced-cordless-telecommunications)
  - [Wi-Fi](#wi-fi)
    - [Protocol Vulnerabilities](#protocol-vulnerabilities)
    - [Exploitation](#exploitation-3)
    - [Reverse Engineering WiFi](#reverse-engineering-wifi)
  - [USB](#usb)
  - [UWB (Ultra-Wideband)](#uwb-ultra-wideband)
  - [TETRA](#tetra)
- [Firmware Security](#firmware-security)
  - [Fundamentals](#fundamentals-7)
  - [Extraction](#extraction)
  - [Static Analysis Tools](#static-analysis-tools)
  - [Dynamic Analysis and Emulation](#dynamic-analysis-and-emulation)
    - [Emulation Tutorials](#emulation-tutorials)
  - [OTA Update Security](#ota-update-security)
    - [Fundamentals](#fundamentals-8)
    - [Attack Vectors](#attack-vectors)
  - [RTOS Security](#rtos-security)
    - [Zephyr RTOS](#zephyr-rtos)
    - [FreeRTOS](#freertos)
  - [Reverse Engineering Tools](#reverse-engineering-tools)
    - [Reverse Engineering Tutorials](#reverse-engineering-tutorials)
    - [Ghidra Tutorials](#ghidra-tutorials)
  - [Online Assemblers](#online-assemblers)
  - [ARM Exploitation](#arm-exploitation)
  - [Binary Analysis](#binary-analysis)
  - [Secure Boot](#secure-boot)
    - [Development](#development)
    - [Bypasses](#bypasses)
  - [UEFI Security](#uefi-security)
  - [Symlink Attacks](#symlink-attacks)
  - [Router Firmware Analysis](#router-firmware-analysis)
  - [Router Exploitation](#router-exploitation)
    - [Netgear Series](#netgear-series)
    - [TP-Link Series](#tp-link-series)
    - [Cisco Series](#cisco-series)
  - [Secure Boot Bypasses](#secure-boot-bypasses)
- [Network and Web Protocols](#network-and-web-protocols)
  - [MQTT](#mqtt)
    - [Fundamentals](#fundamentals-9)
    - [Security and Exploitation](#security-and-exploitation)
    - [Known CVEs](#known-cves)
    - [Tools](#tools-3)
    - [Applications](#applications)
    - [Malware Research](#malware-research)
  - [CoAP](#coap)
    - [Specifications and Security](#specifications-and-security)
    - [Tools - Software](#tools-software-2)
    - [Tools - Hardware](#tools-hardware-2)
    - [Research and Tutorials](#research-and-tutorials)
  - [IoT Protocols Overview](#iot-protocols-overview)
- [Cloud and Backend Security](#cloud-and-backend-security)
  - [AWS IoT Security](#aws-iot-security)
    - [Fundamentals](#fundamentals-10)
    - [Tools](#tools-4)
    - [Vulnerabilities](#vulnerabilities)
  - [Firebase / Cloud Misconfigurations](#firebase-cloud-misconfigurations)
- [Mobile Application Security](#mobile-application-security)
  - [Android](#android)
    - [Android Kernel Exploitation](#android-kernel-exploitation)
    - [Android Scudo Allocator](#android-scudo-allocator)
  - [iOS](#ios)
- [Industrial and Automotive](#industrial-and-automotive)
  - [ICS/SCADA](#icsscada)
  - [Automotive Security](#automotive-security)
  - [EV Chargers](#ev-chargers)
- [Payment Systems](#payment-systems)
  - [ATM Hacking](#atm-hacking)
  - [Payment Village](#payment-village)
- [Tools](#tools-5)
  - [Hardware Tools](#hardware-tools)
    - [Multi-Purpose](#multi-purpose)
    - [Debug Adapters](#debug-adapters)
    - [RF/SDR](#rfsdr)
    - [USB](#usb-1)
    - [Glitching](#glitching)
    - [Flipper Zero](#flipper-zero)
    - [Hak5](#hak5)
  - [Software Tools](#software-tools)
    - [Exploitation Frameworks](#exploitation-frameworks)
    - [Firmware Analysis](#firmware-analysis)
  - [Fuzzing Tools](#fuzzing-tools)
    - [Fundamentals](#fundamentals-11)
    - [IoT-Specific Fuzzing](#iot-specific-fuzzing)
    - [Tools](#tools-6)
  - [Pentesting Operating Systems](#pentesting-operating-systems)
  - [Search Engines](#search-engines)
- [Defensive Security](#defensive-security)
  - [Threat Modeling](#threat-modeling)
    - [STRIDE Framework](#stride-framework)
    - [IoT-Specific Threat Modeling](#iot-specific-threat-modeling)
  - [Secure Development](#secure-development)
    - [Guidelines and Standards](#guidelines-and-standards)
    - [Hardening Guides](#hardening-guides)
  - [Incident Response](#incident-response)
- [Learning Resources](#learning-resources)
  - [Training Platforms](#training-platforms)
  - [Cheatsheets](#cheatsheets)
  - [Vulnerability Guides](#vulnerability-guides)
  - [Pentesting Guides](#pentesting-guides)
  - [YouTube Channels](#youtube-channels)
  - [Books](#books)
    - [Hardware Hacking](#hardware-hacking)
    - [Firmware and Reverse Engineering](#firmware-and-reverse-engineering)
    - [IoT Security](#iot-security)
    - [Wireless and RF](#wireless-and-rf)
    - [Embedded and Mobile](#embedded-and-mobile)
    - [NFC/RFID](#nfcrfid-1)
    - [Industrial and General Security](#industrial-and-general-security)
    - [White Papers and Reports](#white-papers-and-reports)
  - [IoT Series](#iot-series)
- [Labs and CTFs](#labs-and-ctfs)
  - [Vulnerable Applications](#vulnerable-applications)
    - [IoT](#iot)
    - [Router/Firmware](#routerfirmware)
    - [Hardware](#hardware)
    - [Wireless](#wireless)
    - [Industrial](#industrial)
    - [VoIP](#voip)
  - [CTF Competitions](#ctf-competitions)
    - [Hardware CTFs](#hardware-ctfs)
    - [IoT CTFs](#iot-ctfs)
    - [Embedded/Firmware CTFs](#embeddedfirmware-ctfs)
    - [ARM CTFs](#arm-ctfs)
  - [Continuous Learning Platforms](#continuous-learning-platforms)
  - [Lab Setup](#lab-setup)
- [Research and Community](#research-and-community)
  - [Technical Research](#technical-research)
  - [Blogs](#blogs)
  - [Community Platforms](#community-platforms)
  - [Villages](#villages)
  - [Researchers to Follow](#researchers-to-follow)
  - [Device-Specific Research](#device-specific-research)
    - [Cameras](#cameras)
    - [Smart Home Devices](#smart-home-devices)
    - [Smart Speakers](#smart-speakers)
    - [Printers](#printers)
    - [Drones](#drones)
    - [Kitchen Appliances](#kitchen-appliances)
    - [NAS Devices](#nas-devices)
    - [Game Consoles](#game-consoles)
    - [Phones/Tablets](#phonestablets)
  - [TrustZone and TEE Research](#trustzone-and-tee-research)
  - [Pwn2Own Research](#pwn2own-research)
- [Contributing](#contributing)
- [License](#license)
    - [Other Microcontrollers](#other-microcontrollers)
  - [PCIe and DMA Attacks](#pcie-and-dma-attacks)

## Hardware Attacks

### Fundamentals

- [IoT Hardware Guide](https://www.postscapes.com/internet-of-things-hardware/)
- [Intro to Hardware Hacking - Dumping Your First Firmware](https://blog.nvisium.com/intro-to-hardware-hacking-dumping-your-first-firmware)
- [An Introduction to Hardware Hacking](https://securityboulevard.com/2020/09/an-introduction-to-hardware-hacking/)
- [Hardware Toolkits for IoT Security Analysis](https://defcon-nn.ru/0x0B/Hardware%20toolkits%20for%20IoT%20security%20analysis.pdf)
- [Hardware Hacking for IoT Devices - Offensive IoT Exploitation](https://resources.infosecinstitute.com/hardware-hacking-iot-devices-offensive-iot-exploitation/)

### Interface Attacks

#### UART

- [Identifying UART Interface](https://www.mikroe.com/blog/uart-serial-communication)
- [Serial Terminal Basics](https://learn.sparkfun.com/tutorials/terminal-basics/all)
- [Reverse Engineering Serial Ports](http://www.devttys0.com/2012/11/reverse-engineering-serial-ports/)
- [Intro to Embedded RE: UART Discovery and Firmware Extraction via UBoot](https://voidstarsec.com/blog/uart-uboot-and-usb)
- [Using UART to Connect to a Chinese IP Cam](https://www.davidsopas.com/using-uart-to-connect-to-a-chinese-ip-cam/)
- [A Journey into IoT Hardware Hacking: UART](https://techblog.mediaservice.net/2019/03/a-journey-into-iot-hardware-hacking-uart/)
- [Accessing and Dumping Firmware Through UART](https://www.cyberark.com/resources/threat-research-blog/accessing-and-dumping-firmware-through-uart)
- [UART Connections and Dynamic Analysis on Linksys e1000](https://www.youtube.com/watch?v=ix6rSV2Dj44)
- [UARTBruteForcer](https://github.com/FireFart/UARTBruteForcer)
- [UART Exploiter](https://github.com/exploitsecurity.io/uart-exploiter)

#### JTAG

- [Hardware Hacking 101: Introduction to JTAG](https://www.riverloopsecurity.com/blog/2021/05/hw-101-jtag/)
- [How to Find the JTAG Interface](https://www.youtube.com/watch?v=_FSM_10JXsM)
- [Analyzing JTAG](https://nse.digital/pages/guides/hardware/jtag.html)
- [Bus Pirate JTAG Connections with OpenOCD](https://research.kudelskisecurity.com/2014/05/01/jtag-debugging-made-easy-with-bus-pirate-and-openocd/)
- [Extracting Firmware from External Memory via JTAG](https://www.youtube.com/watch?v=IadnBUJAvks)
- [The Hitchhacker's Guide to iPhone Lightning and JTAG Hacking](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/stacksmashing%20-%20The%20hitchhackers%20guide%20to%20iPhone%20Lightning%20%20%20JTAG%20hacking.pdf)
- [Debugging AVR Microcontrollers Through JTAG](https://hev0x.github.io/posts/debugging-avr-with-atmelice-and-gdb/)

#### SWD (Serial Wire Debug)

- [SWD Protocol Overview - HardBreak Wiki](https://www.hardbreak.wiki/hardware-hacking/interface-interaction/jtag-swd/swd)
- [Unveiling Vulnerabilities: Exploring SWD Attack Surface in Hardware](https://redfoxsec.com/blog/unveiling-vulnerabilities-exploring-swd-attack-surface-in-hardware/)
- [Introduction to ARM Serial Wire Debug Protocol](https://developer.arm.com/documentation/ihi0031/a/The-Serial-Wire-Debug-Port--SW-DP-/Introduction-to-the-ARM-Serial-Wire-Debug--SWD--protocol)
- [Serial Wire Debug and CoreSight Architecture](https://community.nxp.com/pwmxy87654/attachments/pwmxy87654/imxrt/4786/2/Serial_Wire_Debug.pdf)
- [LibSWD - Serial Wire Debug Open Library](https://github.com/cederom/LibSWD)
- [Hardware Hacking and Exploitation Bootcamp - SWD](https://happeningnext.com/event/hardware-hacking-and-exploitation-bootcamp-eid4sntq7lbas1)

#### SPI

- [Hardware Hacking 101: Identifying and Dumping eMMC Flash](https://www.riverloopsecurity.com/blog/2020/03/hw-101-emmc/)
- [Dumping Firmware from Router Using Bus Pirate - SPI](https://www.iotpentest.com/2019/06/dumping-firmware-from-device-using.html)
- [Extracting Flash Memory over SPI](https://akimbocore.com/article/extracting-flash-memory-over-spi/)
- [Extracting Firmware from Embedded Devices (SPI NOR Flash)](https://www.youtube.com/watch?v=nruUuDalNR0)
- [How to Flash Chip of a Router with a Programmer](https://www.youtube.com/watch?v=fbt4OJXJdOc)
- [TPM 2.0: Extracting Bitlocker Keys Through SPI](https://lucasteske.dev/2024/01/tpm2-bitlocker-keys)

#### I2C

- [IoT Security Part 16: Hardware Attack Surface I2C](https://payatu.com/masterclass/iot-security-part-16-101-hardware-attack-surface-i2c/)
- [I2C Exploitation - HackTricks](https://book.hacktricks.xyz/todo/hardware-hacking/i2c)
- [Non-invasive I2C Hardware Trojan Attack Vector (PDF)](https://hal.science/hal-03703165/document)
- [Hardware Hacking: I2C Injection with Bus Pirate](http://www.rockfishsec.com/2014/09/hardware-hacking-i2c-injection-with-bus.html)
- [Safeguarding SPI, I2C, and I3C Protocols](https://ez.analog.com/ez-blogs/b/engineering-mind/posts/do-your-embedded-systems-safeguard-against-threats-to-spi-i2c-and-i3c)

#### TPM

- [Introduction to TPM (Trusted Platform Module)](https://sergioprado.blog/introduction-to-tpm-trusted-platform-module/)
- [Trusted Platform Module Security Defeated in 30 Minutes](https://arstechnica.com/gadgets/2021/08/how-to-go-from-stolen-pc-to-network-intrusion-in-30-minutes/)

### Memory Extraction

#### eMMC

- [eMMC Protocol](https://prodigytechno.com/emmc-protocol/)
- [RPMB: A Secret Place Inside the eMMC](https://sergioprado.blog/rpmb-a-secret-place-inside-the-emmc/)
- [Hardware Hacking 101: Identifying and Dumping eMMC Flash](https://www.riverloopsecurity.com/blog/2020/03/hw-101-emmc/)
- [eMMC Data Recovery from Damaged Smartphone](https://dangerouspayload.com/2018/10/24/emmc-data-recovery-from-damaged-smartphone/)
- [Unleash Your Smart-Home Devices: Vacuum Cleaning Robot Hacking](https://media.ccc.de/v/34c3-9147-unleash_your_smart-home_devices_vacuum_cleaning_robot_hacking)
- [Hands-On IoT Hacking: Rapid7 at DEF CON 30](https://www.rapid7.com/blog/post/2022/10/18/hands-on-iot-hacking-rapid7-at-def-con-30-iot-village-part-1/)

### Side-Channel and Fault Injection

#### Fundamentals

- [Side Channel Attacks - Yifan Lu](https://yifan.lu/)
- [Attacks on Implementations of Secure Systems](https://github.com/Yossioren/AttacksonImplementationsCourseBook)
- [Fuzzing, Binary Analysis, IoT Security Collection](https://github.com/0xricksanchez/paper_collection)

#### Glitching Attacks

- [NAND Glitching Attack on Wink Hub](http://www.brettlischalk.com/posts/nand-glitching-wink-hub-for-root)
- [Voltage Glitching with Crowbars Tutorial](https://wiki.newae.com/index.php?title=Tutorial_CW305-4_Voltage_Glitching_with_Crowbars)
- [Voltage Glitching Attack using iCEstick Glitcher](https://www.youtube.com/watch?v=FVUhVewFmxw)
- [FPGA Glitching and Side Channel Attacks - Samy Kamkar](https://www.youtube.com/watch?v=oGndiX5tvEk)
- [Hardware Power Glitch Attack - rhme2](https://www.youtube.com/watch?v=6Pf3pY3GxBM)
- [Keys in Flash - Glitching AES Keys from Arduino](https://srfilipek.medium.com/keys-in-a-flash-3e984d0de54b)
- [Implementing Practical Electrical Glitching Attacks](https://blackhat.com/docs/eu-15/materials/eu-15-Giller-Implementing-Electrical-Glitching-Attacks.pdf)
- [How to Voltage Fault Injection](https://www.synacktiv.com/publications/how-to-voltage-fault-injection)
- [Glitcher Part 1 - Reproducible Voltage Glitching on STM32 Microcontrollers](https://sec-consult.com/blog/detail/secglitcher-part-1-reproducible-voltage-glitching-on-stm32-microcontrollers/)
- [STM32L05 Voltage Glitching](https://blog.syss.com/posts/voltage-glitching-the-stm32l05-microcontroller/)

#### Power Analysis

- [Breaking AES with ChipWhisperer](https://www.youtube.com/watch?v=FktI4qSjzaE)
- [ChipWhisperer Wiki](http://wiki.newae.com/Main_Page)
- [Rowhammer Bit Flips to Steal Crypto Keys](https://arstechnica.com/information-technology/2019/06/researchers-use-rowhammer-bitflips-to-steal-2048-bit-crypto-key/)

#### Other Microcontrollers

- [Dumping the Amlogic A113X Bootrom](https://haxx.in/posts/dumping-the-amlogic-a113x-bootrom/)
- [Retreading The AMLogic A113X TrustZone Exploit Process](https://boredpentester.com/retreading-the-amlogic-a113x-trustzone-exploit-process/)
- [Reverse Engineering an Unknown Microcontroller](https://dmitry.gr/?r=05.Projects&proj=30.%20Reverse%20Engineering%20an%20Unknown%20Microcontroller)
- [Hacking Microcontroller Firmware Through a USB](https://securelist.com/hacking-microcontroller-firmware-through-a-usb/89919/)
- [There's A Hole In Your SoC: Glitching The MediaTek BootROM](https://research.nccgroup.com/2020/10/15/theres-a-hole-in-your-soc-glitching-the-mediatek-bootrom/)

### PCIe and DMA Attacks

- [A Practical Tutorial on PCIe for Total Beginners on Windows - Part 1](https://ctf.re/windows/kernel/pcie/tutorial/2023/02/14/pcie-part-1/)
- [A Practical Tutorial on PCIe for Total Beginners on Windows - Part 2](https://ctf.re/kernel/pcie/tutorial/dma/mmio/tlp/2024/03/26/pcie-part-2/)
- [PCIe DMA Attack against a Secured Jetson Nano (CVE-2022-21819)](https://www.thegoodpenguin.co.uk/blog/pcie-dma-attack-against-a-secured-jetson-nano-cve-2022-21819/)


---

## Wireless Protocols

### RF Fundamentals

- [Complete Course in Software Defined Radio - Michael Ossmann](https://greatscottgadgets.com/sdr/)
- [SDR Notes - Radio IoT Protocols Overview](https://github.com/notpike/SDR-Notes)
- [Understanding Radio](https://www.taitradioacademy.com/lessons/introduction-to-radio-communications-principals/)
- [Introduction to Software Defined Radio](https://www.allaboutcircuits.com/technical-articles/introduction-to-software-defined-radio/)
- [Introduction to GNU Radio Companion](https://wiki.gnuradio.org/index.php/Guided_Tutorial_GRC)
- [Creating a Flow Graph in GNU Radio Companion](https://blog.didierstevens.com/2017/09/19/quickpost-creating-a-simple-flow-graph-with-gnu-radio-companion/)
- [Analyzing Radio Signals 433MHz](https://www.rtl-sdr.com/analyzing-433-mhz-transmitters-rtl-sdr/)
- [Recording Specific Radio Signals](https://www.rtl-sdr.com/freqwatch-rtl-sdr-frequency-scanner-recorder/)
- [Replay Attacks with Raspberry Pi and rpitx](https://www.rtl-sdr.com/tutorial-replay-attacks-with-an-rtl-sdr-raspberry-pi-and-rpitx/)
- [Reverse Engineering a Car Key Fob Signal](https://0x44.cc/radio/2024/03/13/reversing-a-car-key-fob-signal.html)
- [GRCON 2021 - Capture the Signal](https://blog.tclaverie.eu/posts/grcon-2021---capture-the-signal/)
### Bluetooth / BLE

#### Fundamentals

- [Awesome Bluetooth Security](https://github.com/engn33r/awesome-bluetooth-security)
- [BLE-NullBlr: Step by Step Guide to BLE Understanding and Exploiting](https://github.com/V33RU/BLE-NullBlr)
- [Traffic Engineering in a Bluetooth Piconet](http://www.diva-portal.org/smash/get/diva2:833159/FULLTEXT01.pdf)
- [BLE Characteristics: A Beginner's Tutorial](https://devzone.nordicsemi.com/nordic/short-range-guides/b/bluetooth-low-energy/posts/ble-characteristics-a-beginners-tutorial)
- [Intro to Bluetooth Low Energy (PDF)](https://daskalakispiros.com/files/Ebooks/Intro+to+Bluetooth+Low+Energy+v1.1.pdf)
- [Bluetooth LE Security Study Guide](https://www.bluetooth.com/bluetooth-resources/le-security-study-guide/)
- [Intro to Bluetooth Low Energy](https://daskalakispiros.com/files/Ebooks/Intro+to+Bluetooth+Low+Energy+v1.1.pdf)
- [Reverse Engineering BLE Devices](https://reverse-engineering-ble-devices.readthedocs.io/en/latest/)
- [My Journey Towards Reverse Engineering a Smart Band — Bluetooth-LE RE](https://medium.com/@arunmag/my-journey-towards-reverse-engineering-a-smart-band-bluetooth-le-re-d1dea00e4de2)
#### Exploitation Techniques

- [Intel Edison as Bluetooth LE Exploit Box](https://medium.com/@arunmag/intel-edison-as-bluetooth-le-exploit-box-a63e4cad6580)
- [Reverse Engineering and Exploiting a Smart Massager](https://medium.com/@arunmag/how-i-reverse-engineered-and-exploited-a-smart-massager-ee7c9f21bf33)
- [Reverse Engineering a Smart Band - Bluetooth LE RE](https://medium.com/@arunmag/my-journey-towards-reverse-engineering-a-smart-band-bluetooth-le-re-d1dea00e4de2)
- [I Hacked MiBand 3](https://medium.com/@yogeshojha/i-hacked-xiaomi-miband-3-and-here-is-how-i-did-it-43d68c272391)
- [GATTacking Bluetooth Smart Devices](https://securing.pl/en/gattacking-bluetooth-smart-devices-introducing-a-new-ble-proxy-tool/index.html)
- [Examining the August Smart Lock](https://blog.quarkslab.com/examining-the-august-smart-lock.html)
- [Practical Introduction to BLE GATT Reverse Engineering](https://jcjc-dev.com/2023/03/19/reversing-domyos-el500-elliptical/)
- [MojoBox - Yet Another Not So Smartlock](https://mandomat.github.io/2023-03-15-testing-mojobox-security/)
- [Bluetooth Smartlocks](https://www.getkisi.com/blog/smart-locks-hacked-bluetooth-ble)
- [Bluetooth Beacon Vulnerability](https://www.beaconzone.co.uk/blog/category/security/)
- [Denial of Pleasure: Attacking Unusual BLE Targets with a Flipper Zero](https://www.whid.ninja/blog/denial-of-pleasure-attacking-unusual-ble-targets-with-a-flipper-zero)
- [Grand Theft Auto: A peek of BLE relay attack](https://rollingpwn.github.io/BLE-Relay-Aattck/)
- [How I Hacked Smart Lights: CVE-2022-47758](https://pwning.tech/cve-2022-47758/)
- [NFC Relay Attack on Tesla Model Y](https://act-on.ioactive.com/acton/attachment/34793/f-6460b49e-1afe-41c3-8f73-17dc14916847/1/-/-/-/-/NFC-relay-TESlA_JRoriguez.pdf)
#### Vulnerability Research

- [Finding Bugs in Bluetooth](https://bluetooth.lol/)
- [Sweyntooth Vulnerabilities](https://asset-group.github.io/disclosures/sweyntooth/)
- [BrakTooth: Causing Havoc on Bluetooth Link Manager](https://asset-group.github.io/disclosures/braktooth/)
- [BLUFFS: Bluetooth Forward and Future Secrecy Attacks (CVE-2023-24023)](https://github.com/francozappa/bluffs)
- [AirDrop Leak - Sniffing BLE Traffic from Apple Devices](https://github.com/hexway/apple_bleee)
- [BleedingTooth: Linux Bluetooth Zero-Click Remote Code Execution](https://google.github.io/security-research/pocs/linux/bleedingtooth/writeup.html)
- [BRAKTOOTH: Causing Havoc on Bluetooth Link Manager (PDF)](https://asset-group.github.io/disclosures/braktooth/braktooth.pdf)
- [Norec Attack: Stripping BLE encryption from Nordic's Library (CVE-2020-15509)](https://infosecwriteups.com/norec-attack-stripping-ble-encryption-from-nordics-library-cve-2020-15509-9798ab893b95)
#### Conference Talks

- [Blue2thprinting: WTF Am I Even Looking At?](https://darkmentor.com/publication/2023-11-hardweario/)
- [Open Wounds: Last 5 Years Have Left Bluetooth to Bleed](https://darkmentor.com/publication/2023-10-hacklu/)
- [Sniffing Bluetooth Through My Mask During the Pandemic](https://darkmentor.com/publication/2023-08-hitb/)

#### Tools - Software

- [Bluing - Intelligence Gathering for Bluetooth](https://github.com/fO-000/bluing)
- [BlueToolkit - Bluetooth Classic Vulnerability Testing](https://github.com/sgxgsx/BlueToolkit)
- [btproxy](https://github.com/conorpp/btproxy)
- [hcitool and bluez](https://www.pcsuggest.com/linux-bluetooth-setup-hcitool-bluez)
- [Testing with GATT Tool](https://www.jaredwolff.com/blog/get-started-with-bluetooth-low-energy/)
- [crackle - Cracking BLE Encryption](https://github.com/mikeryan/crackle)
- [bettercap](https://github.com/bettercap/bettercap)
- [BtleJuice - Bluetooth Smart MITM Framework](https://github.com/DigitalSecurity/btlejuice)
- [GATTacker](https://github.com/securing/gattacker)
- [BTLEjack - BLE Swiss Army Knife](https://github.com/virtualabs/btlejack)
- [DEDSEC Bluetooth Exploit](https://github.com/0xbitx/DEDSEC-Bluetooth-exploit)
- [BrakTooth ESP32 PoC](https://github.com/Matheus-Garbelini/braktooth_esp32_bluetooth_classic_attacks)
- [SweynTooth BLE Attacks](https://github.com/Matheus-Garbelini/sweyntooth_bluetooth_low_energy_attacks)
- [ESP32 Bluetooth Classic Sniffer](https://github.com/Matheus-Garbelini/esp32_bluetooth_classic_sniffer)
- [Bluetooth Hacking Collection](https://github.com/zedxpace/bluetooth-hacking-)

#### Tools - Hardware

- [nRF52840 Dongle](https://www.nordicsemi.com/Software-and-tools/Development-Kits/nRF52840-Dongle)
- [Ubertooth One](https://github.com/greatscottgadgets/ubertooth/wiki/Ubertooth-One)
- [CSR 4.0 Bluetooth Dongle](https://www.amazon.in/GENERIC-Ultra-Mini-Bluetooth-Dongle-Adapter/dp/B0117H7GZ6/)
- [ESP32](https://www.espressif.com/en/products/hardware/esp32/overview)
- [Sena UD100](http://www.senanetworks.com/ud100-g03.html)
- [ESP-WROVER-KIT](https://www.digikey.in/en/products/detail/espressif-systems/ESP-WROVER-KIT-VB/8544301)

#### Tools

- [Ubertooth One](https://github.com/greatscottgadgets/ubertooth/wiki/Ubertooth-One)
- [nRF52840 Dongle](https://www.nordicsemi.com/Software-and-tools/Development-Kits/nRF52840-Dongle)
- [BTLEjack - BLE Swiss Army Knife](https://github.com/virtualabs/btlejack)
- [GATTacker](https://github.com/securing/gattacker)
- [BrakTooth ESP32 PoC](https://github.com/Matheus-Garbelini/braktooth_esp32_bluetooth_classic_attacks)
- [SweynTooth BLE Attacks](https://github.com/Matheus-Garbelini/sweyntooth_bluetooth_low_energy_attacks)
- [ice9-bluetooth-sniffer](https://github.com/mikeryan/ice9-bluetooth-sniffer)
- [InternalBlue - Bluetooth Experimentation Framework](https://github.com/seemoo-lab/internalblue)

#### Hacking Bluetooth Coffee Machines

- [Hacking Bluetooth to Brew Coffee from Github Actions - Part 1](https://grack.com/blog/2022/12/01/hacking-bluetooth-to-brew-coffee-on-github-actions-part-1/)
- [Hacking Bluetooth to Brew Coffee from Github Actions - Part 2](https://grack.com/blog/2022/12/02/hacking-bluetooth-to-brew-coffee-on-github-actions-part-2/)
- [Hacking Bluetooth to Brew Coffee from Github Actions - Part 3](https://grack.com/blog/2022/12/04/hacking-bluetooth-to-brew-coffee-on-github-actions-part-3/)

### Zigbee / Z-Wave

#### Fundamentals

- [Introduction and Protocol Overview](http://www.informit.com/articles/article.aspx?p=1409785)
- [ZigBee and Z-Wave Security Brief](http://www.riverloopsecurity.com/blog/2018/05/zigbee-zwave-part1/)
- [Hacking ZigBee Networks](https://resources.infosecinstitute.com/topic/hacking-zigbee-networks/)

#### Exploitation

- [Hacking IoT Devices with Attify Zigbee Framework](https://blog.attify.com/hack-iot-devices-zigbee-sniffing-exploitation/)
- [Zigator: Analyzing Security of Zigbee-Enabled Smart Homes](https://mews.sv.cmu.edu/papers/wisec-20.pdf)
- [Security Analysis of Zigbee with Zigator and GNU Radio](https://mews.sv.cmu.edu/research/zigator/testbed-grcon2020-slides.pdf)
- [Low-Cost ZigBee Selective Jamming](https://www.bastibl.net/reactive-zigbee-jamming/)

#### Tools - Software

- [Killerbee](https://github.com/riverloopsec/killerbee)
- [ZigDiggity](https://github.com/BishopFox/zigdiggity)
- [Zigator](https://github.com/akestoridis/zigator)
- [Z3sec](https://github.com/IoTsec/Z3sec)
- [zigbear](https://github.com/philippnormann/zigbear)

#### Tools - Hardware

- [ApiMote](https://www.riverloopsecurity.com/projects/apimote/)
- [RaspBee](https://phoscon.de/en/raspbee/)
- [ATUSB IEEE 802.15.4 Adapter](http://shop.sysmocom.de/products/atusb)
- [nRF52840 Dongle](https://www.nordicsemi.com/Software-and-tools/Development-Kits/nRF52840-Dongle)
- [USRP](https://www.ettus.com/products/)

### LoRa / LoRaWAN

- [LoRaWAN Security Overview - Tektelic](https://tektelic.com/expertise/lorawan-security/)
- [Security Vulnerabilities in LoRaWAN](https://www.cyber-threat-intelligence.com/publications/IoTDI2018-LoraWAN.pdf)
- [Low Powered and High Risk: Attacks on LoRaWAN Devices](https://www.trendmicro.com/en_us/research/21/a/Low-Powered-but-High-Risk-Evaluating-Possible-Attacks-on-LoRaWAN-Devices.html)
- [LAF - LoRaWAN Auditing Framework](https://github.com/IOActive/laf)
- [ChirpOTLE - LoRaWAN Security Framework](https://github.com/seemoo-lab/chirpotle)
#### Fundamentals

- [LoRaWAN Security Overview - Tektelic](https://tektelic.com/expertise/lorawan-security/)
- [LoRaWAN Security Survey - ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S2542660520301359)
- [Security Vulnerabilities in LoRaWAN (PDF)](https://www.cyber-threat-intelligence.com/publications/IoTDI2018-LoraWAN.pdf)
- [LoRaWAN - Wikipedia](https://en.wikipedia.org/wiki/LoRa)

#### Exploitation

- [Low Powered and High Risk: Attacks on LoRaWAN Devices - Trend Micro](https://www.trendmicro.com/en_us/research/21/a/Low-Powered-but-High-Risk-Evaluating-Possible-Attacks-on-LoRaWAN-Devices.html)
- [Millions of Devices Using LoRaWAN Exposed - SecurityWeek](https://www.securityweek.com/millions-devices-using-lorawan-exposed-hacker-attacks/)
- [Do You Blindly Trust LoRaWAN Networks? - IOActive](https://www.ioactive.com/do-you-blindly-trust-lorawan-networks-for-iot/)
- [LoRaWAN Encryption Keys Easy to Crack - Threatpost](https://threatpost.com/lorawan-encryption-keys-easy-to-crack-jeopardizing-security-of-iot-networks/152276/)
- [LoPT: LoRa Penetration Testing Tool (PDF)](https://www.ijitee.org/wp-content/uploads/papers/v8i9S2/I10810789S219.pdf)

#### Tools

- [LAF - LoRaWAN Auditing Framework](https://github.com/IOActive/laf)
- [ChirpOTLE - LoRaWAN Security Framework](https://github.com/seemoo-lab/chirpotle)
- [LoRa Craft - Packet Interception](https://github.com/PentHertz/LoRa_Craft)
- [Open Source LoRaWAN Hacking Tool](https://www.thethingsnetwork.org/forum/t/open-source-tool-for-hacking-auditing-and-monitoring-lorawan-networks/31185)
- [LoRaWAN Hackaday Projects](https://hackaday.com/tag/lorawan/)

### Matter / Thread

#### Fundamentals

- [Matter Standard - CSA-IoT](https://csa-iot.org/all-solutions/matter/)
- [Matter Protocol Wikipedia](https://en.wikipedia.org/wiki/Matter_(standard))
- [Matter Protocol Complete Guide 2025](https://thinkrobotics.com/blogs/learn/matter-protocol-explained-for-smart-homes-complete-guide-2025)
- [How to Secure Smart Home Devices with Matter](https://www.iot-now.com/2022/07/12/122292-how-to-secure-smart-home-devices-with-the-matter-standard/)
- [Smart Home Device Solutions for Matter - DigiCert](https://www.digicert.com/solutions/security-solutions-for-matter-devices)

#### Security Research

- [Security Vulnerabilities and Attack Scenarios in Smart Home with Matter](https://www.ndss-symposium.org/wp-content/uploads/2024/07/sdiotsec2024-48-paper.pdf)
- [Trust Matters: Uncovering Vulnerabilities in Matter Protocol - Nozomi](https://www.nozominetworks.com/blog/trust-matters-uncovering-vulnerabilities-in-the-matter-protocol)
- [Matter over Thread Security](https://sensereo.com/community/matter-over-thread-security-how-safe-is-your-smart-home-network/)
- [State-of-the-Art Review on IoT Wireless PAN Protocol Security](https://www.mdpi.com/2073-8994/12/4/579)
- [Matter Smart Home - Krasamo](https://www.krasamo.com/matter-smart-home/)

### Cellular (GSM/LTE/5G)

- [Awesome Cellular Hacking](https://github.com/W00t3k/Awesome-Cellular-Hacking/)
- [Introduction to GSM Security](http://www.pentestingexperts.com/introduction-to-gsm-security/)
- [Breaking LTE on Layer Two](https://alter-attack.net/)
- [5Ghoul - 5G NR Attacks and Fuzzing](https://github.com/asset-group/5ghoul-5g-nr-attacks)
- [Exploiting CSN.1 Bugs in MediaTek Basebands](https://labs.taszk.io/articles/post/mtk_baseband_csn1_exploitation/)
- [SIM Hijacking](https://sensepost.com/blog/2022/sim-hijacking/)
- [SigPloit - Telecom Signaling Exploitation Framework](https://github.com/SigPloiter/SigPloit)
- [LTE Sniffer](https://github.com/SysSec-KAIST/LTESniffer)
#### Fundamentals

- [Introduction to GSM Security](http://www.pentestingexperts.com/introduction-to-gsm-security/)
- [GSM Security Part 2](https://www.ehacking.net/2011/02/gsm-security-2.html)
- [What is Base Transceiver Station](https://en.wikipedia.org/wiki/Base_transceiver_station)
- [Introduction to SS7 Signaling](https://www.patton.com/whitepapers/Intro_to_SS7_Tutorial.pdf)
- [SS7 Network Architecture](https://youtu.be/pg47dDUL1T0)
- [Introduction to SIGTRAN](https://www.youtube.com/watch?v=XUY6pyoRKsg)

#### Exploitation

- [Awesome Cellular Hacking](https://github.com/W00t3k/Awesome-Cellular-Hacking/)
- [How to Build Your Own Rogue GSM BTS](https://l33t.gg/how-to-build-a-rogue-gsm-bts/)
- [GSM Vulnerabilities with USRP B200](https://ieeexplore.ieee.org/document/7581461/)
- [Security Testing 4G (LTE) Networks](https://labs.mwrinfosecurity.com/assets/BlogFiles/mwri-44con-lte-presentation-2012-09-11.pdf)
- [Case Study of SS7/SIGTRAN Assessment](https://nullcon.net/website/archives/pdf/goa-2017/case-study-of-SS7-sigtran.pdf)
- [Breaking LTE on Layer Two](https://alter-attack.net/)
- [5Ghoul - 5G NR Attacks and Fuzzing](https://github.com/asset-group/5ghoul-5g-nr-attacks)

#### Tools

- [SigPloit - Telecom Signaling Exploitation Framework](https://github.com/SigPloiter/SigPloit)
- [ss7MAPer - SS7 Pentesting Toolkit](https://n0where.net/ss7-pentesting-toolkit-ss7maper)
- [LTE Sniffer](https://github.com/SysSec-KAIST/LTESniffer)
- [Fake BTS Detector (SCL-8521)](https://www.shoghicom.com/fake-bts-detector.php)

### NFC/RFID

- [Awesome RFID/NFC Security Talks](https://github.com/doegox/awesome-rfid-talks)
- [RFID Discord Group](https://discord.gg/Z43TrcVyPr)
- [SoK: Security of EMV Contactless Payment Systems](https://arxiv.org/pdf/2504.12812)
### DECT (Digital Enhanced Cordless Telecommunications)

- [Real Time Interception of DECT Cordless Telephone](https://www.youtube.com/watch?v=MDF1eUvOte0)
- [Eavesdropping on Unencrypted DECT Voice Traffic](https://www.youtube.com/watch?v=WBvYsXrs3DI)
- [Decoding DECT Voice Traffic: In-depth Explanation](https://www.youtube.com/watch?v=oiMkirm_xfY)

---

### Wi-Fi

#### Protocol Vulnerabilities

- [Framing Frames: Bypassing Wi-Fi Encryption by Manipulating Transmit Queues](https://papers.mathyvanhoef.com/usenix2023-wifi.pdf)
- [Man-in-the-Middle Attacks without Rogue AP: When WPAs Meet ICMP Redirects](https://csis.gmu.edu/ksun/publications/WiFi_Interception_SP23.pdf)
- [WPAxFuzz: Sniffing Out Vulnerabilities in Wi-Fi Implementations](https://www.mdpi.com/2410-387X/6/4/53/)
- [Untangling the Knot: Breaking Access Control in Home Wireless Mesh Networks](https://www.cs.ucr.edu/%7Ezhiyunq/pub/ccs24_wireless_mesh.pdf)

#### Exploitation

- [Over The Air: Exploiting Broadcom's Wi-Fi Stack (Part 1)](https://googleprojectzero.blogspot.com/2017/04/over-air-exploiting-broadcoms-wi-fi_4.html)
- [Over The Air: Exploiting Broadcom's Wi-Fi Stack (Part 2)](https://googleprojectzero.blogspot.com/2017/04/over-air-exploiting-broadcoms-wi-fi_11.html)
- [Over The Air: Exploiting The Wi-Fi Stack on Apple Devices](https://googleprojectzero.blogspot.com/2017/10/over-air-vol-2-pt-3-exploiting-wi-fi.html)
- [Reverse-engineering Broadcom wireless chipsets](https://blog.quarkslab.com/reverse-engineering-broadcom-wireless-chipsets.html)
- [Exploiting Qualcomm WLAN and Modem Over the Air](https://i.blackhat.com/USA-19/Thursday/us-19-Pi-Exploiting-Qualcomm-WLAN-And-Modem-Over-The-Air-wp.pdf)
- [Windows Wi-Fi Driver RCE Vulnerability – CVE-2024-30078](https://www.crowdfense.com/windows-wi-fi-driver-rce-vulnerability-cve-2024-30078/)
- [When a Wi-Fi SSID Gives You Root on an MT02 Repeater - Part 1](https://chocapikk.com/posts/2025/when-a-wifi-name-gives-you-root/)
- [When a Wi-Fi SSID Gives You Root on an MT02 Repeater - Part 2](https://chocapikk.com/posts/2025/when-a-wifi-name-gives-you-root-part-two/)

#### Reverse Engineering WiFi

- [Reverse Engineering WiFi on RISC-V BL602](https://lupyuen.github.io/articles/wifi)
- [Unveiling secrets of the ESP32: creating an open-source MAC Layer](https://zeus.ugent.be/blog/23-24/open-source-esp32-wifi-mac/)
- [Unveiling secrets of the ESP32: reverse engineering RX](https://zeus.ugent.be/blog/23-24/esp32-reverse-engineering-continued/)
### USB

- [ALL ABOUT USB-C: INTRODUCTION FOR HACKERS](https://hackaday.com/2022/12/06/usb-c-introduction-for-hackers/)
- [Hi, My Name is Keyboard](https://github.com/skysafe/reblog/blob/main/cve-2024-0230/README.md)
- [How to Weaponize the Yubikey](https://www.blackhillsinfosec.com/how-to-weaponize-the-yubikey/)

### UWB (Ultra-Wideband)

- [UWB Real Time Locating Systems: How Secure Radio Communications May Fail in Practice](https://uploads-ssl.webflow.com/645a4534705010e2cb244f50/64912bac55ece2717e14e84a_Nozomi-Networks-WP-UWB-Real-Time-Locating-Systems.pdf)

### TETRA

- [All cops are broadcasting: TETRA under scrutiny](https://uploads-ssl.webflow.com/64a2900ed5e9bb672af9b2ed/64d42fcc2e3fdcf3d323f3d9_All_cops_are_broadcasting_TETRA_under_scrutiny.pdf)

---

## Firmware Security

### Fundamentals

- [Introduction to Firmware Analysis - OWASP](https://www.owasp.org/index.php/IoT_Firmware_Analysis)
- [OWASP Firmware Security Testing Methodology](https://scriptingxss.gitbook.io/firmware-security-testing-methodology/)
- [IoT Security Verification Standard (ISVS)](https://github.com/OWASP/IoT-Security-Verification-Standard-ISVS)
- [Reversing 101](https://0xinfection.github.io/reversing/)
- [Reverse Engineering for Everyone](https://0xinfection.github.io/reversing/)
- [Hands-on Firmware Extraction, Exploration, and Emulation](https://github.com/onekey-sec/BHEU23-firmware-workshop)
### Extraction

- [Router Analysis Part 1: UART Discovery and SPI Flash Extraction](https://wrongbaud.github.io/posts/router-teardown/)
- [Hardware Hacking Tutorial: Dumping and Reversing Firmware](https://ivanorsolic.github.io/post/hardwarehacking1/)
- [Firmware Samples - firmware.center](https://firmware.center/)
- [BasicFUN Series: Hardware Analysis / SPI Flash Extraction](https://wrongbaud.github.io/posts/BasicFUN-flashing/)
- [BasicFUN Series: Reverse Engineering Firmware / Reflashing SPI Flash](https://wrongbaud.github.io/posts/BasicFUN-rom-analysis/)
- [Retrofitting encrypted firmware is a Bad Idea](https://haxx.in/posts/wtm-wtf/)
### Static Analysis Tools

- [EMBA - Embedded Linux Firmware Analyzer](https://p4cx.medium.com/emba-b370ce503602)
- [FACT - Firmware Analysis and Comparison Tool](https://github.com/fkie-cad/FACT_core)
- [Binwalk v3](https://github.com/ReFirmLabs/binwalk/tree/binwalkv3)
- [Firmwalker](https://github.com/craigz28/firmwalker)
- [fwanalyzer](https://github.com/cruise-automation/fwanalyzer)
- [fwhunt-scan - UEFI Firmware Analysis](https://github.com/binarly-io/fwhunt-scan)
- [ByteSweep](https://gitlab.com/bytesweep/bytesweep)
- [QueryX - Static Taint Tracking](https://github.com/RiS3-Lab/QueryX)
- [FirmGraph](https://github.com/ucsb-seclab/firmgraph)
- [BINSEC](https://github.com/binsec/binsec)
- [unblob - Extraction Framework](https://github.com/onekey-sec/unblob)
- [fchk - Security Checks for Firmware](https://github.com/IOActive/fchk)
- [Checksec.sh](https://github.com/slimm609/checksec.sh)
- [Firmware Modification Kit](https://code.google.com/archive/p/firmware-mod-kit/)
### Dynamic Analysis and Emulation

- [Firmadyne - Automated Firmware Emulation](https://github.com/firmadyne/firmadyne)
- [FirmAE - Firmware Analysis and Emulation](https://github.com/firmadyne/firmAE)
- [QEMU](https://www.qemu.org/)
- [PANDA - Architecture-Neutral Dynamic Analysis](https://github.com/panda-re/panda)
- [Avatar2 - Dynamic Firmware Analysis](https://github.com/avatartwo/avatar2)
- [Renode - Embedded Systems Emulator](https://github.com/renode/renode)
- [Unicorn Engine - CPU Emulator](https://github.com/unicorn-engine/unicorn)
- [Qiling Framework](https://github.com/qilingframework/qiling)
- [HALucinator](https://github.com/ucsb-seclab/HALucinator)
- [FirmWire - Baseband Firmware Emulation](https://github.com/FirmWire/FirmWire)
- [SymQEMU](https://github.com/weiwei1116/symqemu)
- [S2E - Selective Symbolic Execution](https://github.com/S2E/s2e)
- [Bochs - x86 Emulator](https://github.com/bochs-dev-team/bochs)
- [SAME70 Emulator](https://www.0x01team.com/sw_security/same70-emulator/)
- [Emulate Until You Make it](https://www.hexacon.fr/slides/hexacon_draytek_2022_final.pdf)
#### Emulation Tutorials

- [Firmware Emulation with QEMU](https://www.youtube.com/watch?v=G0NNBloGIvs)
- [Emulating ARM Router Firmware - Azeria Labs](https://azeria-labs.com/emulating-arm-firmware/)
- [Emulating IoT Firmware Made Easy](https://boschko.ca/qemu-emulating-firmware/)
- [IoT Binary Analysis and Emulation Part 1](https://hacklido.com/blog/529-iot-binary-analysis-emulation-part-1)
- [Cross Debugging for ARM/MIPS with QEMU](https://reverseengineering.stackexchange.com/questions/8829/cross-debugging-for-arm-mips-elf-with-qemu-toolchain)
- [QEMU + Buildroot 101](https://gitbook.seguranca-informatica.pt/arm/tools/qemu-101)
- [Simulating and Hunting Firmware Vulnerabilities with Qiling](https://blog.vincss.net/2020/12/pt007-simulating-and-hunting-firmware-vulnerabilities-with-Qiling.html)
- [Qiling and Binary Emulation for Automatic Unpacking](https://kernemporium.github.io/articles/en/auto_unpacking/m.html)
- [Debugging D-Link: Emulating Firmware and Hacking Hardware](https://www.greynoise.io/blog/debugging-d-link-emulating-firmware-and-hacking-hardware)
- [Adaptive Emulation Framework for Multi-Architecture IoT](https://www.techscience.com/cmc/v75n2/52069/pdf)
- [Automatic Firmware Emulation through Invalidity-guided Knowledge Inference](https://www.usenix.org/conference/usenixsecurity21/presentation/zhou)
- [Emulating RH850 architecture with Unicorn Engine](https://blog.quarkslab.com/emulating-rh850-architecture-with-unicorn-engine.html)
- [Icicle: A Re-designed Emulator for Grey-Box Firmware Fuzzing](https://arxiv.org/pdf/2301.13346.pdf)
- [Challenges and Pitfalls while Emulating Six Current Icelandic Household Routers](https://skemman.is/bitstream/1946/50456/1/Challenges_and_Pitfalls_while_Emulating_Six_Current_Icelandic_Household_Routers.pdf)
- [My Emulation Goes to the Moon... Until False Flag](https://retooling.io/blog/my-emulation-goes-to-the-moon-until-false-flag)
- [How to Emulate Android Native Libraries Using Qiling](https://www.appknox.com/security/how-to-emulate-android-native-libraries-using-qiling)
### OTA Update Security

#### Fundamentals

- [IoT Firmware Security and Update Mechanisms](https://www.encryptionconsulting.com/iot-firmware-security-and-update-mechanisms-a-deep-dive/)
- [Implementing OTA Updates for IoT Devices](https://www.kaaiot.com/iot-knowledge-base/implementing-over-the-air-updates-for-iot-devices)
- [Secure OTA Boot Chains and Firmware Verification](https://promwad.com/news/secure-ota-boot-chains-firmware-verification)
- [The Key to Firmware Security in Connected IoT Devices](https://www.keyfactor.com/blog/firmware-security-iot-devices/)
- [Security Considerations for OTA Updates - Stack Overflow](https://stackoverflow.blog/2020/12/14/security-considerations-for-ota-software-updates-for-iot-gateway-devices/)

#### Attack Vectors

- [Top 10 IoT Vulnerabilities - OTA Update Attacks](https://www.keyfactor.com/blog/top-10-iot-vulnerabilities-in-your-devices/)
- [Updating IoT Devices 2025: Best Practices](https://stormotion.io/blog/updating-iot-devices/)
- [Review of IoT Firmware Vulnerabilities and Auditing Techniques](https://pmc.ncbi.nlm.nih.gov/articles/PMC10821153/)
- [Secure OTA Firmware Update Mechanism (PDF)](https://ecejournals.in/index.php/ESA/article/download/397/632/2072)

### RTOS Security

#### Zephyr RTOS

- [Zephyr RTOS GitHub](https://github.com/zephyrproject-rtos/zephyr)
- [Zephyr Vulnerabilities List](https://docs.zephyrproject.org/latest/security/vulnerabilities.html)
- [NCC Group Zephyr and MCUboot Security Assessment](https://www.nccgroup.com/us/research-blog/research-report-zephyr-and-mcuboot-security-assessment/)
- [26 Flaws in Zephyr and MCUboot](https://embeddedcomputing.com/technology/open-source/linux-freertos-related/another-iot-security-uh-oh-26-flaws-in-open-source-zephyr-and-mcuboot-stacks)
- [Tackling Security in Zephyr RTOS](https://www.electronicdesign.com/technologies/embedded/article/21215503/percepio-tackling-security-and-reliability-in-the-zephyr-rtos)
- [Enhancing Security with Zephyr RTOS](https://witekio.com/blog/zephyr-rtos-security/)

#### FreeRTOS

- [FreeRTOS 13 Vulnerabilities in TCP/IP Stack](https://hub.packtpub.com/freertos-affected-by-13-vulnerabilities-in-its-tcp-ip-stack/)
- [Exploiting Memory Corruption in FreeRTOS - ShmooCon](https://shmoo.gitbook.io/2016-shmoocon-proceedings/bring_it_on/01_exploiting_memory_corruption)
- [RTOS Security Analysis - USENIX](https://www.usenix.org/system/files/usenixsecurity25-shao.pdf)
- [Dynamic Vulnerability Patching for RTOS](https://www.arxiv.org/pdf/2509.10213)
- [AWS FreeRTOS Vulnerabilities](https://info.cgcompliance.com/blog/vulnerabilities-in-the-aws-iot-platform-you-should-know-about)

### Reverse Engineering Tools

- [Ghidra](https://github.com/NationalSecurityAgency/ghidra)
- [IDA Pro](https://www.hex-rays.com/products/ida/)
- [Radare2](https://www.rada.re/n/)
- [Cutter - GUI for Radare2](https://github.com/rizinorg/cutter)
- [Binary Ninja](https://binary.ninja/)
- [GDB](https://www.gnu.org/software/gdb/)
- [RetDec - Decompiler](https://github.com/avast/retdec)
- [Diaphora - Binary Diffing](https://github.com/joxeankoret/diaphora)
- [Angr - Binary Analysis](https://github.com/angr/angr)
- [Frida - Dynamic Instrumentation](https://github.com/frida/frida)
- [Ret-sync](https://github.com/bootleg/ret-sync)
- [OllyDbg](http://www.ollydbg.de/)
- [x64dbg](https://x64dbg.com/)
- [Hopper](https://www.hopperapp.com/)
- [Immunity Debugger](https://www.immunityinc.com/products/debugger/)
- [PEiD](https://www.aldeid.com/wiki/PEiD)
- [Ghidriff - Ghidra Binary Diffing Engine](https://github.com/clearbluejar/ghidriff)
- [The rev.ng decompiler goes open source](https://rev.ng/blog/open-sourcing-renvg-decompiler-ui-closed-beta)
- [Intro to Cutter](https://goggleheadedhacker.com/post/intro-to-cutter)
- [pyghidra-mcp: Headless Ghidra MCP Server](https://clearbluejar.github.io/posts/pyghidra-mcp-headless-ghidra-mcp-server-for-project-wide-multi-binary-analysis/)
- [Mindshare: Using Binary Ninja API to Detect Potential Use-after-free Vulnerabilities](https://www.zerodayinitiative.com/blog/2025/3/20/mindshare-using-binary-ninja-api-to-detect-potential-use-after-free-vulnerabilities)
#### Reverse Engineering Tutorials

- [Reverse Engineering and Patching with Ghidra](https://www.coalfire.com/the-coalfire-blog/reverse-engineering-and-patching-with-ghidra)
- [Reverse Engineering with Ghidra: Breaking Firmware Encryption](https://www.youtube.com/watch?v=4urMITJKQQs)
- [Reversing Firmware with Radare](https://www.bored-nerds.com/reversing/radare/automotive/2019/07/07/reversing-firmware-with-radare.html)
- [Reversing ESP8266 Firmware](https://boredpentester.com/reversing-esp8266-firmware-part-1/)
- [Automating Binary Vulnerability Discovery with Ghidra and Semgrep](https://security.humanativaspa.it/automating-binary-vulnerability-discovery-with-ghidra-and-semgrep/)
- [Finding Bugs in Netgear Router](https://flattsecurity.medium.com/finding-bugs-to-trigger-unauthenticated-command-injection-in-a-netgear-router-psv-2022-0044-2b394fb9edc)

#### Ghidra Tutorials

- [Debugger Ghidra Class](https://github.com/NationalSecurityAgency/ghidra/tree/master/GhidraDocs/GhidraDocs/GhidraClass/Debugger)
- [Ghidra 101: Cursor Text Highlighting](https://www.tripwire.com/state-of-security/ghidra-101-cursor-text-highlighting)
- [Ghidra 101: Decoding Stack Strings](https://www.tripwire.com/state-of-security/ghidra-101-decoding-stack-strings)
- [Extending Ghidra Part 1: Setting up a Development Environment](https://voidstarsec.com/blog/ghidra-dev-environment)
- [Expanding the Dragon: Adding an ISA to Ghidra](https://trenchant.io/expanding-the-dragon-adding-an-isa-to-ghidra/)
- [Ghidra nanoMIPS ISA module](https://research.nccgroup.com/2024/05/07/ghidra-nanomips-isa-module/)
- [Binary type inference in Ghidra](https://blog.trailofbits.com/2024/02/07/binary-type-inference-in-ghidra/)
- [Writing a Ghidra processor module](https://irisc-research-syndicate.github.io/2025/02/14/writing-a-ghidra-processor-module/)

### Online Assemblers

- [AZM Online ARM Assembler - Azeria Labs](https://azeria-labs.com/azm/)
- [Online Disassembler](https://onlinedisassembler.com/odaweb/)
- [Compiler Explorer](https://godbolt.org/)

### ARM Exploitation

- [Azeria Labs ARM Tutorials](https://azeria-labs.com/)
- [ARM Exploitation for IoT](https://www.exploit-db.com/docs/english/43906-arm-exploitation-for-iot.pdf)
- [Damn Vulnerable ARM Router (DVAR)](https://blog.exploitlab.net/2018/01/dvar-damn-vulnerable-arm-router.html)
- [Exploit Education](https://exploit.education/)
- [A Guide to ARM64 / AArch64 Assembly on Linux](https://modexp.wordpress.com/2018/10/30/arm64-assembly/?ref=0xor0ne.xyz)
- [ARMv8 AArch64/ARM64 Full Beginner's Assembly Tutorial](https://mariokartwii.com/armv8/)
- [A Noobs Guide to ARM Exploitation](https://ad2001.gitbook.io/a-noobs-guide-to-arm-exploitation/)
- [ARM64 Reversing And Exploitation Series (8ksec) - Parts 1-10](https://8ksec.io/arm64-reversing-and-exploitation-part-1-arm-instruction-set-simple-heap-overflow/)
- [AArch64 memory and paging](https://krinkinmu.github.io/2024/01/14/aarch64-virtual-memory.html)
- [We are ARMed no more ROPpery Here](https://zeyadazima.com/exploit%20development/pointer_pac/)
### Binary Analysis

- [Reverse Engineering for Everyone](https://0xinfection.github.io/reversing/)
- [Practical Binary Analysis](https://nostarch.com/binaryanalysis)

### Secure Boot

#### Development

- [Writing a Bootloader](http://3zanders.co.uk/2017/10/13/writing-a-bootloader/)

#### Bypasses

- [Pwn the ESP32 Secure Boot](https://limitedresults.com/2019/09/pwn-the-esp32-secure-boot/)
- [Pwn ESP32 Forever: Flash Encryption and Secure Boot Keys Extraction](https://limitedresults.com/2019/11/pwn-the-esp32-forever-flash-encryption-and-sec-boot-keys-extraction/)
- [ESP32 Secure Boot Bypass (CVE-2020-13629)](https://raelize.com/blog/espressif-esp32-bypassing-encrypted-secure-boot-cve-2020-13629/)
- [Amlogic S905 SoC: Bypassing Secure Boot](https://fredericb.info/2016/10/amlogic-s905-soc-bypassing-not-so.html)
- [Defeating Secure Boot with Symlink Attacks](https://www.anvilsecure.com/blog/defeating-secure-boot-with-symlink-attacks.html)
- [PS4 Secure Boot Hacking - Fail0verflow](https://www.psxhax.com/threads/ps4-aux-hax-5-psvr-secure-boot-hacking-with-keys-by-fail0verflow.12820/)
- [Dell BIOS Vulnerabilities - BIOSDisconnect](https://eclypsium.com/2021/06/24/biosdisconnect/)
- [U-Boot USB DFU Vulnerability (CVE-2022-2347)](https://research.nccgroup.com/2023/01/20/technical-advisory-u-boot-unchecked-download-size-and-direction-in-usb-dfu-cve-2022-2347/)
- [Breaking Secure Boot on Silicon Labs Gecko](https://blog.quarkslab.com/breaking-secure-boot-on-the-silicon-labs-gecko-platform.html)

### UEFI Security

- [Using Symbolic Execution to Detect UEFI Vulnerabilities](https://binarly.io/posts/Using_Symbolic_Execution_to_Detect_UEFI_Firmware_Vulnerabilities/index.html)
- [HP Enterprise UEFI Vulnerabilities](https://www.binarly.io/posts/Binarly_Finds_Six_High_Severity_Firmware_Vulnerabilities_in_HP_Enterprise_Devices/index.html)
- [Emulating and Exploiting UEFI Firmware](https://margin.re/2023/09/emulating-and-exploiting-uefi-firmware/)
- [The Dark Side of UEFI: A technical Deep-Dive into Cross-Silicon Exploitation](https://www.binarly.io/blog/the-dark-side-of-uefi-a-technical-deep-dive-into-cross-silicon-exploitation)
- [Inside the LogoFAIL PoC: From Integer Overflow to Arbitrary Code Execution](https://www.binarly.io/blog/inside-the-logofail-poc-from-integer-overflow-to-arbitrary-code-execution)
- [PixieFail: Nine vulnerabilities in Tianocore's EDK II IPv6 network stack](https://blog.quarkslab.com/pixiefail-nine-vulnerabilities-in-tianocores-edk-ii-ipv6-network-stack.html)
- [For Science! - Using an Unimpressive Bug in EDK II](https://blog.quarkslab.com/for-science-using-an-unimpressive-bug-in-edk-ii-to-do-some-fun-exploitation.html)
- [Hydroph0bia: SecureBoot bypass for Insyde H2O](https://coderush.me/hydroph0bia-part1/)
---
### Symlink Attacks

- [Zip Slip Vulnerability](https://security.snyk.io/research/zip-slip-vulnerability)

---

### Router Firmware Analysis

- [A Journey into IoT: Discover Components and Ports](https://security.humanativaspa.it/a-journey-into-iot-unknown-chinese-alarm-part-1-discover-components-and-ports/)
- [A Journey into IoT: Firmware Dump and Analysis](https://security.humanativaspa.it/a-journey-into-iot-unknown-chinese-alarm-part-2-firmware-dump-and-analysis/)
- [A Journey into IoT: Radio Communications](https://security.humanativaspa.it/a-journey-into-iot-unknown-chinese-alarm-part-3-radio-communications/)
- [A Journey into IoT: Internal Communications](https://security.humanativaspa.it/a-journey-into-iot-unknown-chinese-alarm-part-4-internal-communications/)
- [Dynamic Analysis of Firmware Components in IoT Devices](https://ics-cert.kaspersky.com/publications/reports/2022/07/06/dynamic-analysis-of-firmware-components-in-iot-devices/)
- [RV130X Firmware Analysis](https://raffo24.github.io/hardware%20hacking/FirmwareAnalysis/)
- [TP-Link Firmware Decryption C210 V2 cloud camera bootloaders](https://watchfulip.github.io/28-12-24/tp-link_c210_v2.html)

### Router Exploitation

- [Hunting for Unauthenticated n-days in Asus Routers](https://www.shielder.com/blog/2024/01/hunting-for-~~un~~authenticated-n-days-in-asus-routers/)
- [Pulling MikroTik into the Limelight](https://margin.re/2022/06/pulling-mikrotik-into-the-limelight/)
- [Exploiting MikroTik RouterOS Hardware with CVE-2023-30799](https://vulncheck.com/blog/mikrotik-foisted-revisited)
- [Rooting Xiaomi WiFi Routers](https://blog.thalium.re/posts/rooting-xiaomi-wifi-routers/)
- [Route to Safety: Navigating Router Pitfalls](https://starlabs.sg/blog/2024/route-to-safety-navigating-router-pitfalls/)
- [ROPing our way to RCE](https://modzero.com/en/blog/roping-our-way-to-rce/)
- [ROPing Routers from scratch: Tenda Ac8v4](https://0reg.dev/blog/tenda-ac8-rop)
- [PwnAgent: A One-Click WAN-side RCE in Netgear RAX Routers](https://mahaloz.re/2023/02/25/pwnagent-netgear.html)
- [Puckungfu 2: Another NETGEAR WAN Command Injection](https://research.nccgroup.com/2024/02/09/puckungfu-2-another-netgear-wan-command-injection/)
- [Reversing, Discovering, And Exploiting A TP-Link Router Vulnerability — CVE-2024–54887](https://infosecwriteups.com/reversing-discovering-and-exploiting-a-tp-link-router-vulnerability-cve-2024-54887-341552c4b104)
- [Exploiting Zero-Day (CVE-2025–9961) Vulnerability in the TP-Link AX10 Router](https://blog.byteray.co.uk/exploiting-zero-day-cve-2025-9961-in-the-tp-link-ax10-router-8745f9af9c46)
- [FiberGateway GR241AG - Full Exploit Chain](https://r0ny.net/FiberGateway-GR241AG-Full-Exploit-Chain/)
- [Blackbox-Fuzzing of IoT Devices Using the Router TL-WR902AC](https://tsmr.eu/blackbox-fuzzing.html)
- [Rooting the TP-Link Tapo C200 Rev.5](https://quentinkaiser.be/security/2025/07/25/rooting-tapo-c200/)

#### Netgear Series

- [Netgear Orbi: Introduction, UART Access, Recon](http://blog.coffinsec.com/research/2022/06/12/orbi-hunting-0-intro-uart.html)
- [Netgear Orbi: Crashes in SOAP-API](http://blog.coffinsec.com/research/2022/06/19/orbi-hunting-1-soap-api-crashes.html)
- [Netgear Orbi: NDay Exploit CVE-2020-27861](http://blog.coffinsec.com/research/2022/07/02/orbi-nday-exploit-cve-2020-27861.html)
- [The Last Breath of Our Netgear RAX30 Bugs](https://starlabs.sg/blog/2022/12-the-last-breath-of-our-netgear-rax30-bugs-a-tragic-tale-before-pwn2own-toronto-2022/)

#### TP-Link Series

- [TP-Link TDDP Buffer Overflow Vulnerability](https://boschko.ca/tp-link-tddp-bof/)
- [Pwn2Own Tokyo 2020: Defeating the TP-Link AC1750](https://www.synacktiv.com/en/publications/pwn2own-tokyo-2020-defeating-the-tp-link-ac1750.html)
- [TP-Link Tapo c200 Camera Unauthenticated RCE (CVE-2021-4045)](https://www.hacefresko.com/posts/tp-link-tapo-c200-unauthenticated-rce)

#### Cisco Series

- [Patch Diffing a Cisco RV110W Firmware Update - Part 1](https://quentinkaiser.be/exploitdev/2020/09/23/ghetto-patch-diffing-cisco/)
- [CVE-2024-20356: Jailbreaking a Cisco appliance to run DOOM](https://labs.nettitude.com/blog/cve-2024-20356-jailbreaking-a-cisco-appliance-to-run-doom/)
- [Flashback Connects - Cisco RV340 SSL VPN RCE](https://www.flashback.sh/blog/flashback-connects-cisco-rv340-ssl-vpn-rce)

### Secure Boot Bypasses

- [Pwn the ESP32 Secure Boot](https://limitedresults.com/2019/09/pwn-the-esp32-secure-boot/)
- [Breaking Secure Boot on Silicon Labs Gecko](https://blog.quarkslab.com/breaking-secure-boot-on-the-silicon-labs-gecko-platform.html)
- [Bypassing Secure Boot using Fault Injection](https://raelize.com/upload/research/2016/2016_BlackHat-EU_Bypassing-Secure-Boot-Using-Fault-Injection_NT-AS.pdf)
- [Breaking Secure Boot on Google Nest Hub (2nd Gen)](https://fredericb.info/2022/06/breaking-secure-boot-on-google-nest-hub-2nd-gen-to-run-ubuntu.html)
- [Booting into Breaches: Hunting Windows SecureBoot's Remote Attack Surfaces](https://i.blackhat.com/BH-USA-25/Presentations/US-25-Yang-Booting-into-breaches-Wednesday.pdf)

## Network and Web Protocols

### MQTT

- [Introduction to MQTT](https://www.hivemq.com/blog/mqtt-essentials-part-1-introducing-mqtt)
- [MQTT Broker Security 101](https://payatu.com/blog/mqtt-broker-security/)
- [Hacking the IoT with MQTT](https://morphuslabs.com/hacking-the-iot-with-mqtt-8edaf0d07b9b)
- [IoT Security: RCE in MQTT Protocol](https://systemweakness.com/iot-security-rce-in-mqtt-protocol-929e533f12b4)
- [IoXY - MQTT Intercepting Proxy](https://blog.nviso.eu/2020/07/06/introducing-ioxy-an-open-source-mqtt-intercepting-proxy/)
- [MQTT-PWN](https://mqtt-pwn.readthedocs.io/en/latest/)
#### Fundamentals

- [Introduction to MQTT](https://www.hivemq.com/blog/mqtt-essentials-part-1-introducing-mqtt)
- [Understanding the MQTT Protocol Packet Structure](http://www.steves-internet-guide.com/mqtt-protocol-messages-overview/)

#### Security and Exploitation

- [MQTT Broker Security 101](https://payatu.com/blog/mqtt-broker-security/)
- [Hacking the IoT with MQTT](https://morphuslabs.com/hacking-the-iot-with-mqtt-8edaf0d07b9b)
- [Are Smart Homes Vulnerable to Hacking?](https://blog.avast.com/mqtt-vulnerabilities-hacking-smart-homes)
- [IoT Security: RCE in MQTT Protocol](https://systemweakness.com/iot-security-rce-in-mqtt-protocol-929e533f12b4)
- [Penetration Testing Sesame Smart Door Lock](https://www.diva-portal.org/smash/get/diva2:1750933/FULLTEXT01.pdf)
- [Servisnet Tessa - MQTT Credentials Dump (Metasploit)](https://www.exploit-db.com/exploits/50713)
- [Eclipse Mosquitto Unquoted Service Path](https://www.exploit-db.com/exploits/49673)

#### Known CVEs

- [CVE-2020-13849](https://nvd.nist.gov/vuln/detail/CVE-2020-13849) - DoS vulnerability (CVSS 7.5)
- [CVE-2023-3028](https://nvd.nist.gov/vuln/detail/CVE-2023-3028) - Insufficient authentication (CVSS 9.8)
- [CVE-2021-0229](https://nvd.nist.gov/vuln/detail/CVE-2021-0229) - Resource consumption (CVSS 5.3)
- [CVE-2019-5432](https://nvd.nist.gov/vuln/detail/CVE-2019-5432) - Malformed packet crash (CVSS 7.5)

#### Tools

- [IoXY - MQTT Intercepting Proxy](https://blog.nviso.eu/2020/07/06/introducing-ioxy-an-open-source-mqtt-intercepting-proxy/)
- [Mosquitto - Open Source MQTT Broker](https://mosquitto.org/)
- [HiveMQ](https://www.hivemq.com/)
- [MQTT Explorer](http://mqtt-explorer.com/)
- [MQTT-PWN](https://mqtt-pwn.readthedocs.io/en/latest/)
- [Nmap MQTT Library](https://nmap.org/nsedoc/lib/mqtt.html)
- [Seven Best MQTT Client Tools](https://www.hivemq.com/blog/seven-best-mqtt-client-tools)

#### Applications

- [Using IoT MQTT for V2V and Connected Cars](https://mobilebit.wordpress.com/tag/mqtt/)
- [MQTT Hardware Development Projects](https://www.hackster.io/search?i=projects&q=Mqtt)
- [100,000 Connected Cars with Kubernetes, Kafka, MQTT, TensorFlow](https://dzone.com/articles/iot-live-demo-100000-connected-cars-with-kubernete)
- [Authenticating Devices Using MQTT with Auth0](https://auth0.com/docs/integrations/authenticate-devices-using-mqtt)
- [Deep Learning UDF for MQTT IoT Anomaly Detection](https://github.com/kaiwaehner/ksql-udf-deep-learning-mqtt-iot)
- [Guide to MQTT: Hacking a Doorbell](https://youtu.be/J_BAXVSVPVI)

#### Malware Research

- [WailingCrab Malware Using MQTT for C2](https://securityonline.info/wailingcrab-malware-evolves-embracing-mqtt-for-stealthier-c2-communication)
- [Alert: New WailingCrab Malware Loader](https://thehackernews.com/2023/11/alert-new-wailingcrab-malware-loader.html)
- [MQTT on Snapcraft](https://snapcraft.io/search?q=mqtt)

### CoAP

- [IETF Security Protocol Comparison](https://datatracker.ietf.org/doc/draft-ietf-iotops-security-protocol-comparison/03/)
- [RFC 8613 - OSCORE](https://datatracker.ietf.org/doc/html/rfc8613)
- [Radware - CoAP Protocol Overview](https://www.radware.com/security/ddos-knowledge-center/ddospedia/coap/)
#### Specifications and Security

- [IETF Security Protocol Comparison (2023)](https://datatracker.ietf.org/doc/draft-ietf-iotops-security-protocol-comparison/03/)
- [EMQX on CoAP and IoT Security (2024)](https://www.emqx.com/en/blog/iot-protocols-mqtt-coap-lwm2m)
- [RFC 8613 - OSCORE](https://datatracker.ietf.org/doc/html/rfc8613)
- [RFC 8323 - CoAP over TCP](https://datatracker.ietf.org/doc/html/rfc8323)
- [RFC 8824 - SCHC Header Compression](https://datatracker.ietf.org/doc/html/rfc8824)

#### Tools - Software

- [CoAP NSE (Nmap)](https://nmap.org/nsedoc/lib/coap.html)
- [Copper - Firefox CoAP Plugin](https://github.com/mkovatsc/Copper)
- [libcoap CLI Tools](https://github.com/obgm/libcoap)
- [Scapy CoAP Plugin](https://github.com/secdev/scapy)
- [Eclipse Californium (Java)](https://www.eclipse.org/californium/)
- [Peach Fuzzer](https://www.peach.tech/)

#### Tools - Hardware

- [Raspberry Pi / Arduino + 6LoWPAN](https://docs.arduino.cc/tutorials/nano-33-iot/contiki-ng-coap-example)
- [Zolertia](https://zolertia.io/)
- [OpenMote](http://www.openmote.com/)
- [Nordic Boards](https://www.nordicsemi.com/)

#### Research and Tutorials

- [SpectralOps - Top IoT Protocol Security Issues](https://spectralops.io/blog/top-5-most-commonly-used-iot-protocols-and-their-security-issues/)
- [Radware - CoAP Protocol Overview](https://www.radware.com/security/ddos-knowledge-center/ddospedia/coap/)
- [IoT Pentest Lab Setup Guide (2025)](https://www.webasha.com/blog/how-to-set-up-a-penetration-testing-lab-in-2025-complete-guide-with-tools-os-network-topology-and-real-world-practice-scenarios)
- [CoAP Exposure Study (2024)](https://raid2024.github.io/papers/raid2024-9.pdf)

### IoT Protocols Overview

- [IoT Protocols Overview](https://www.postscapes.com/internet-of-things-protocols/)
- [IoT Attack Surface - OWASP](https://www.owasp.org/index.php/IoT_Attack_Surface_Areas)
- [IoT Architecture](https://www.c-sharpcorner.com/UploadFile/f88748/internet-of-things-part-2/)
---
- [Attacking IoT Devices from Web Perspective](https://lug.uniroma2.it/eventi/linux-day-23/files/Linux%20Day%20-%20Attacking%20IoT%20Devices.pdf)
- [Awesome Industrial Protocols](https://github.com/Orange-Cyberdefense/awesome-industrial-protocols)
## Cloud and Backend Security

### AWS IoT Security

- [AWS Penetration Testing Policy](https://aws.amazon.com/security/penetration-testing/)
- [AWS Pentesting Guide - HackerOne](https://www.hackerone.com/knowledge-center/penetration-testing-aws-practical-guide)
- [A few notes on AWS Nitro Enclaves](https://blog.trailofbits.com/2024/02/16/a-few-notes-on-aws-nitro-enclaves-images-and-attestation/)
- [Pacu - AWS Exploitation Framework](https://github.com/RhinoSecurityLabs/pacu)
- [ScoutSuite - Multi-cloud Security Auditing](https://github.com/nccgroup/ScoutSuite)
- [Prowler - Cloud Security Assessment](https://github.com/prowler-cloud/prowler)
---
#### Fundamentals

- [AWS Penetration Testing Policy](https://aws.amazon.com/security/penetration-testing/)
- [AWS Pentesting Guide - HackerOne](https://www.hackerone.com/knowledge-center/penetration-testing-aws-practical-guide)
- [Comprehensive AWS Pentesting Guide - BreachLock](https://www.breachlock.com/resources/blog/comprehensive-aws-pentesting-guide/)
- [AWS Pentest Methodology - MorattiSec](https://medium.com/@MorattiSec/my-aws-pentest-methodology-14c333b7fb58)
- [AWS Penetration Testing Methodology - Rootshell](https://www.rootshellsecurity.net/aws-penetration-testing-methodology-and-guidelines/)
- [AWS Penetration Testing Techniques 2025](https://deepstrike.io/blog/aws-penetration-testing-guide-techniques-and-methodology)

#### Tools

- [Pacu - AWS Exploitation Framework](https://github.com/RhinoSecurityLabs/pacu)
- [ScoutSuite - Multi-cloud Security Auditing](https://github.com/nccgroup/ScoutSuite)
- [Prowler - Cloud Security Assessment](https://github.com/prowler-cloud/prowler)
- [CloudFox - Cloud Attack Paths](https://github.com/BishopFox/cloudfox)
- [S3Scanner - Leaky Bucket Discovery](https://github.com/sa7mon/S3Scanner)
- [Cloudfoxable Labs](https://github.com/BishopFox/cloudfoxable)
- [AWS Security Pentesting Resources](https://github.com/redskycyber/Cloud-Security/blob/main/AWS-Security-Pentesting-Resources.md)

#### Vulnerabilities

- [AWS IoT Platform Vulnerabilities](https://info.cgcompliance.com/blog/vulnerabilities-in-the-aws-iot-platform-you-should-know-about)
- [7 Best AWS Pentesting Tools 2026](https://www.getastra.com/blog/cloud/aws/aws-pentesting-tools/)
- [PayloadsAllTheThings - AWS Pentest](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Cloud%20-%20AWS%20Pentest.md)

### Firebase / Cloud Misconfigurations

- [Firebase Security Rules Testing](https://firebase.google.com/docs/rules/unit-tests)
- [Misconfigured Firebase Databases](https://www.comparitech.com/blog/information-security/firebase-misconfiguration-vulnerability/)

---

## Mobile Application Security

### Android

- [Android App Reverse Engineering 101](https://maddiestone.github.io/AndroidAppRE/)
- [Android Application Pentesting Book](https://www.packtpub.com/hardware-and-creative/learning-pentesting-android-devices)
- [Android Pentest Video Course - TutorialsPoint](https://www.youtube.com/watch?v=zHknRia3I6s&list=PLWPirh4EWFpESLreb04c4eZoCvJQJrC6H)
- [Android Tamer](https://androidtamer.com/)
- [Android Hacker's Handbook](https://www.amazon.in/Android-Hackers-Handbook-MISL-WILEY-Joshua/dp/812654922X)
- [A first look at Android 14 forensics](https://blog.digital-forensics.it/2024/01/a-first-look-at-android-14-forensics.html?m=1)
- [Deobfuscating Android ARM64 strings with Ghidra](https://blog.nviso.eu/2024/01/15/deobfuscating-android-arm64-strings-with-ghidra-emulating-patching-and-automating/)
- [How to Emulate Android Native Libraries Using Qiling](https://www.appknox.com/security/how-to-emulate-android-native-libraries-using-qiling)
- [Introduction to Fuzzing Android Native Components](https://blog.convisoappsec.com/en/introduction-to-fuzzing-android-native-components/)
- [Hacking Android Games](https://8ksec.io/hacking-android-games/)
- [Intercepting HTTPS Communication in Flutter](https://sensepost.com/blog/2025/intercepting-https-communication-in-flutter-going-full-hardcore-mode-with-frida/)
#### Android Kernel Exploitation

- [Android Kernel Exploitation](https://cloudfuzz.github.io/android-kernel-exploitation/)
- [Attacking Android Binder: Analysis and Exploitation of CVE-2023-20938](https://androidoffsec.withgoogle.com/posts/attacking-android-binder-analysis-and-exploitation-of-cve-2023-20938/)
- [Attacking the Android kernel using the Qualcomm TrustZone](https://tamirzb.com/attacking-android-kernel-using-qualcomm-trustzone)
- [Driving forward in Android drivers](https://googleprojectzero.blogspot.com/2024/06/driving-forward-in-android-drivers.html)
- [Analyzing a Modern In-the-wild Android Exploit](https://googleprojectzero.blogspot.com/2023/09/analyzing-modern-in-wild-android-exploit.html)
- [Exploiting Android's Hardened Memory Allocator](https://www.usenix.org/system/files/woot24-mao.pdf)
- [GPUAF - Two ways of Rooting All Qualcomm based Android phones](https://powerofcommunity.net/poc2024/Pan%20Zhenpeng%20&%20Jheng%20Bing%20Jhong,%20GPUAF%20-%20Two%20ways%20of%20rooting%20All%20Qualcomm%20based%20Android%20phones.pdf)
- [The Qualcomm DSP Driver - Unexpectedly Excavating an Exploit](https://googleprojectzero.blogspot.com/2024/12/qualcomm-dsp-driver-unexpectedly-excavating-exploit.html)
- [Qualcomm DSP Kernel Internals](https://streypaws.github.io/posts/DSP-Kernel-Internals/)
- [Binder Fuzzing](https://androidoffsec.withgoogle.com/posts/binder-fuzzing/)

#### Android Scudo Allocator

- [Android: Scudo](https://technologeeks.com/blog/Scudo/)
- [Behind the Shield: Unmasking Scudo's Defenses](https://www.synacktiv.com/en/publications/behind-the-shield-unmasking-scudos-defenses)
- [scudo Hardened Allocator — Unofficial Internals Documentation](https://www.l3harris.com/newsroom/editorial/2023/10/scudo-hardened-allocator-unofficial-internals-documentation)

### iOS

- [iOS Pentesting Guide](https://web.securityinnovation.com/hubfs/iOS%20Hacking%20Guide.pdf)
- [OWASP Mobile Security Testing Guide](https://owasp.org/www-project-mobile-security-testing-guide/)
---
- [An iOS hacker tries Android](https://googleprojectzero.blogspot.com/2020/12/an-ios-hacker-tries-android.html)
- [Analyzing IOS Kernel Panic Logs](https://8ksec.io/analyzing-kernel-panic-ios/)
- [Blasting Past iOS 18](https://blog.dfsec.com/ios/2025/05/30/blasting-past-ios-18/)
- [Emulating an iPhone in QEMU](https://eshard.com/posts/emulating-ios-14-with-qemu)
- [First analysis of Apple's USB Restricted Mode bypass (CVE-2025-24200)](https://blog.quarkslab.com/first-analysis-of-apples-usb-restricted-mode-bypass-cve-2025-24200.html)
- [Exploring UNIX pipes for iOS kernel exploit primitives](https://www.corellium.com/blog/exploring-unix-pipes-for-ios-kernel-exploit-primitives)
## Industrial and Automotive

### ICS/SCADA

- [ICS Village](https://www.icsvillage.com/)
- [ICS Discord Group](https://discord.com/invite/CmDDsFK)
- [Controlthings.io Platform](https://www.controlthings.io/platform)
- [Applied Cyber Security and the Smart Grid](https://www.amazon.com/Applied-Cyber-Security-Smart-Grid/dp/1597499986/)
- [Deep Lateral Movement in OT Networks](https://www.forescout.com/resources/l1-lateral-movement-reportg)
- [Hacking ICS Historians: The Pivot Point from IT to OT](https://claroty.com/team82/research/hacking-ics-historians-the-pivot-point-from-it-to-ot)
- [OPC UA Deep Dive Series - Parts 1-5](https://claroty.com/team82/research/opc-ua-deep-dive-history-of-the-opc-ua-protocol)
- [Inside a New OT/IoT Cyberweapon: IOCONTROL](https://claroty.com/team82/research/inside-a-new-ot-iot-cyber-weapon-iocontrol)
- [Attention, High Voltage: Exploring the Attack Surface of the Rockwell Automation PowerMonitor 1000](https://claroty.com/team82/research/attention-high-voltage-exploring-the-attack-surface-of-the-rockwell-automation-powermonitor-1000)
### Automotive Security

- [Awesome Vehicle Security](https://github.com/jaredthecoder/awesome-vehicle-security)
- [Car Hacking Village](https://www.carhackingvillage.com/)
- [Jeep Hack](http://illmatics.com/Remote%20Car%20Hacking.pdf)
- [Subaru Head Unit Jailbreak](https://github.com/sgayou/subaru-starlink-research/blob/master/doc/README.md)
- [Car Hacking Practical Guide 101](https://medium.com/@yogeshojha/car-hacking-101-practical-guide-to-exploiting-can-bus-using-instrument-cluster-simulator-part-i-cd88d3eb4a53)
---
- [CAN Injection: keyless car theft](https://kentindell.github.io/2023/04/03/can-injection/)
- [How I Hacked my Car Series - Parts 1-6](https://programmingwithstyle.com/posts/howihackedmycar/)
- [How I Also Hacked my Car](https://goncalomb.com/blog/2024/01/30/f57cf19b-how-i-also-hacked-my-car)
- [Extracting Secure Onboard Communication (SecOC) keys from a 2021 Toyota RAV4 Prime](https://icanhack.nl/blog/secoc-key-extraction/)
- [Recovering an ECU firmware using disassembler and branches](https://blog.quarkslab.com/recovering-an-ecu-firmware-using-disassembler-and-branches.html)
- [Automotive Memory Protection Units: Uncovering Hidden Vulnerabilities](https://plaxidityx.com/blog/blog-post/is-your-memory-protecteduncovering-hidden-vulnerabilities-in-automotive-mpu-mechanisms/)
### EV Chargers

- [A Detailed Look at Pwn2own Automotive EV Charger Hardware](https://www.zerodayinitiative.com/blog/2023/11/28/a-detailed-look-at-pwn2own-automotive-ev-charger-hardware)
- [Pwn2Own Automotive 2024: Hacking the ChargePoint Home Flex](https://sector7.computest.nl/post/2024-08-pwn2own-automotive-chargepoint-home-flex/)
- [Reverse engineering an EV charger](https://www.mnemonic.io/no/resources/blog/reverse-engineering-an-ev-charger/)

---

## Payment Systems

### ATM Hacking

- [Introduction to ATM Penetration Testing](https://www.youtube.com/watch?v=Ff-0zXTYhuA)
- [Pwning ATMs for Fun and Profit](https://www.youtube.com/watch?v=9cG-JL0LHYw)
- [Jackpotting ATMs Redux - Barnaby Jack](https://www.youtube.com/watch?v=4StcW9OPpPc)
- [Root Shell on Credit Card Terminal](https://stefan-gloor.ch/yomani-hack)
- [SoK: Security of EMV Contactless Payment Systems](https://arxiv.org/pdf/2504.12812)
---
### Payment Village

- [Payment Village](https://www.paymentvillage.org/home)

---

## Tools

### Hardware Tools

- [Bus Pirate](https://www.sparkfun.com/products/12942)
- [Bus Pirate 5: The Swiss ARRRmy Knife of Hardware Hacking](https://eclypsium.com/blog/bus-pirate-5-the-swiss-arrrmy-knife-of-hardware-hacking/)
- [The Shikra](https://int3.cc/products/the-shikra)
- [Attify Badge](https://www.attify-store.com/products/attify-badge-assess-security-of-iot-devices)
- [ChipWhisperer](http://wiki.newae.com/Main_Page)
- [Flipper Zero](https://flipperzero.one/)
- [HackRF](https://greatscottgadgets.com/hackrf/)
- [RTL-SDR](https://www.rtl-sdr.com/)
- [An In-Depth Look at the ICE-V Wireless FPGA Development Board](https://tomverbeure.github.io/2022/12/27/The-ICE-V-Wireless-FPGA-Board.html)
#### Multi-Purpose

- [Bus Pirate](https://www.sparkfun.com/products/12942)
- [The Shikra](https://int3.cc/products/the-shikra)
- [Attify Badge](https://www.attify-store.com/products/attify-badge-assess-security-of-iot-devices)
- [Logic Analyzer - Saleae](https://www.saleae.com/)
- [JTAGulator](https://www.adafruit.com/product/1550)
- [EEPROM Reader/SOIC Cable](https://www.sparkfun.com/products/13153)

#### Debug Adapters

- [ST-Link](https://www.st.com/en/development-tools/st-link-v2.html)
- [Segger J-Link](https://www.segger.com/products/debug-probes/j-link/)
- [FTDI-based Adapters](https://ftdichip.com/)
- [Black Magic Probe](https://black-magic.org/)

#### RF/SDR

- [HackRF](https://greatscottgadgets.com/hackrf/)
- [RTL-SDR](https://www.rtl-sdr.com/)
- [USRP](https://www.ettus.com/products/)

#### USB

- [FaceDancer21](https://int3.cc/products/facedancer21)
- [RfCat](https://int3.cc/products/rfcat)

#### Glitching

- [ChipWhisperer](http://wiki.newae.com/Main_Page)

#### Flipper Zero

- [Flipper Zero](https://flipperzero.one/)

#### Hak5

- [Hak5 Field Kits](https://hakshop.com/)

### Software Tools

- [Expliot Framework](https://gitlab.com/expliot_framework/expliot)
- [RouterSploit](https://github.com/threat9/routersploit)
- [HomePwn](https://github.com/ElevenPaths/HomePWN)
- [Firmware Analysis Toolkit (FAT)](https://github.com/attify/firmware-analysis-toolkit)
- [Shambles: The Next-Generation IoT Reverse Engineering Tool](https://boschko.ca/shambles/)
#### Exploitation Frameworks

- [Expliot Framework](https://gitlab.com/expliot_framework/expliot)
- [RouterSploit](https://github.com/threat9/routersploit)
- [IoTSecFuzz](https://gitlab.com/invuls/iot-projects/iotsecfuzz)
- [HomePwn](https://github.com/ElevenPaths/HomePWN)
- [PENIOT](https://github.com/yakuza8/peniot)
- [ISF - Industrial Security Framework](https://github.com/w3h/isf)
- [HAL - Hardware Analyzer](https://github.com/emsec/hal)
- [FwAnalyzer](https://github.com/cruise-automation/fwanalyzer)
- [PRET - Printer Exploitation Toolkit](https://github.com/RUB-NDS/PRET)

#### Firmware Analysis

- [Firmware Analysis Toolkit (FAT)](https://github.com/attify/firmware-analysis-toolkit)
- [Samsung Firmware Magic](https://github.com/chrivers/samsung-firmware-magic)

### Fuzzing Tools

- [The art of Fuzzing: Introduction](https://bushido-sec.com/index.php/2023/06/19/the-art-of-fuzzing/)
- [A LibAFL Introductory Workshop](https://www.atredis.com/blog/2023/12/4/a-libafl-introductory-workshop)
- [The Blitz Tutorial Lab on Fuzzing with AFL++](https://research.checkpoint.com/2023/the-blitz-tutorial-lab-on-fuzzing-with-afl/)
- [State of Linux Snapshot Fuzzing](https://fuzzinglabs.com/state-of-linux-snapshot-fuzzing/)
- [Fuzzing between the lines in popular barcode software](https://blog.trailofbits.com/2024/10/31/fuzzing-between-the-lines-in-popular-barcode-software/)
- [Boofuzz](https://github.com/jtpereyda/boofuzz)
- [Syzkaller - Kernel Fuzzer](https://github.com/google/syzkaller)
- [parking-game-fuzzer](https://github.com/addisoncrump/parking-game-fuzzer)
#### Fundamentals

- [OWASP Fuzzing Info](https://owasp.org/www-community/Fuzzing)
- [Fuzz Testing of Application Reliability](https://pages.cs.wisc.edu/~bart/fuzz/)
- [FuzzingPaper Collection](https://github.com/wcventure/FuzzingPaper/tree/master/Paper)
- [Google Fuzzing Forum](https://github.com/google/fuzzing)

#### IoT-Specific Fuzzing

- [Fuzzing ICS Protocols](https://1modm.github.io/Fuzzing_ICS_protocols.html)
- [Fuzzowski - Network Protocol Fuzzer](https://hakin9.org/fuzzowski-the-network-protocol-fuzzer-that-we-will-want-to-use/)
- [FIRM-AFL: High-Throughput IoT Firmware Fuzzing](https://www.usenix.org/conference/usenixsecurity19/presentation/zheng)
- [Snipuzz: Black-box Fuzzing of IoT Firmware](https://arxiv.org/pdf/2105.05445.pdf)
- [Fuzzing IoT Binaries Part 1](https://blog.attify.com/fuzzing-iot-devices-part-1/)
- [Fuzzing IoT Binaries Part 2](https://blog.attify.com/fuzzing-iot-binaries-with-afl-part-ii/)
- [Awesome Embedded Fuzzing](https://github.com/andreia-oca/awesome-embedded-fuzzing)

#### Tools

- [Boofuzz](https://github.com/jtpereyda/boofuzz)
- [Syzkaller - Kernel Fuzzer](https://github.com/google/syzkaller)
- [AFL Training Exercises](https://github.com/mykter/afl-training)
- [Frankenstein - Broadcom/Cypress Firmware Emulation for Fuzzing](https://github.com/seemoo-lab/frankenstein)
- [InternalBlue - Bluetooth Experimentation Framework](https://github.com/seemoo-lab/internalblue)
- [Dr. Memory](https://github.com/DynamoRIO/drmemory)

### Pentesting Operating Systems

- [AttifyOS](https://github.com/adi0x90/attifyos)
- [IoT Penetration Testing OS v1](https://github.com/IoT-PTv)
- [EmbedOS](https://github.com/scriptingxss/EmbedOS)
- [Sigint OS - LTE IMSI Catcher](https://www.sigintos.com/)
- [Instant GNU Radio OS](https://github.com/bastibl/instant-gnuradio)
- [Dragon OS - SDR Software](https://www.rtl-sdr.com/dragonos-debian-linux-with-preinstalled-open-source-sdr-software/)
- [Skywave Linux - SDR](https://skywavelinux.com/)
- [Zephyr RTOS](https://www.zephyrproject.org/)
- [Ubuntu LTS](https://www.ubuntu.com/)
### Search Engines

- [Shodan](https://www.shodan.io/)
- [Censys](https://censys.io/)
- [ZoomEye](https://www.zoomeye.org/)
- [BinaryEdge](https://www.binaryedge.io/)
- [Thingful](https://www.thingful.net/)
- [Wigle](https://wigle.net/)
- [Hunter.io](https://hunter.io/)
- [BuiltWith](https://builtwith.com/)
- [NetDB](https://github.com/stamparm/NetDB)
- [Recon-ng](https://github.com/lanmaster53/recon-ng)
- [PublicWWW](https://publicwww.com/)
- [FCC ID Database](https://fccid.io/)
---
## Defensive Security

### Threat Modeling

- [STRIDE Threat Model Guide - Practical DevSecOps](https://www.practical-devsecops.com/what-is-stride-threat-model/)
- [OWASP Threat Modeling Process](https://owasp.org/www-community/Threat_Modeling_Process)
- [STRIDE-based Threat Modeling for IoT Precision Agriculture](https://arxiv.org/pdf/2201.09493)
#### STRIDE Framework

- [STRIDE Threat Model Guide - Practical DevSecOps](https://www.practical-devsecops.com/what-is-stride-threat-model/)
- [What is STRIDE in Threat Modeling - Security Compass](https://www.securitycompass.com/blog/stride-in-threat-modeling/)
- [OWASP Threat Modeling Process](https://owasp.org/www-community/Threat_Modeling_Process)
- [Threat Modeling with ATT&CK - MITRE](https://ctid.mitre.org/projects/threat-modeling-with-attack/)
- [What is Threat Modeling - Fortinet](https://www.fortinet.com/resources/cyberglossary/threat-modeling)

#### IoT-Specific Threat Modeling

- [STRIDE-based Threat Modeling for IoT Precision Agriculture](https://arxiv.org/pdf/2201.09493)
- [STRIDE Threat Modeling for IoT Smart Home](https://online-journals.org/index.php/i-jim/article/view/52377)
- [STRIDE Threat Modeling for Smart Solar Energy Systems](https://www.mdpi.com/2071-1050/17/6/2386)
- [STRIDE Threat Modeling for IoT Healthcare Systems](https://www.researchgate.net/publication/394711434_STRIDE-Based_Threat_Modeling_and_Risk_Assessment_Framework_for_IoT-enabled_Smart_Healthcare_Systems)
- [STRIDE for IoT Agriculture - IEEE](https://ieeexplore.ieee.org/document/9732597/)

### Secure Development

- [OWASP IoT Top 10](https://owasp.org/www-project-internet-of-things/)
- [IoT Security Verification Standard (ISVS)](https://github.com/OWASP/IoT-Security-Verification-Standard-ISVS)
- [ETSI EN 303 645 - IoT Security Standard](https://www.etsi.org/deliver/etsi_en/303600_303699/303645/02.01.01_60/en_303645v020101p.pdf)
- [Compiler Options Hardening Guide for C and C++](https://best.openssf.org/Compiler-Hardening-Guides/Compiler-Options-Hardening-Guide-for-C-and-C++.html)
- [Linux Hardening Guide](https://madaidans-insecurities.github.io/guides/linux-hardening.html)
- [Docker Security – Step-by-Step Hardening](https://reynardsec.com/en/docker-platform-security-step-by-step-hardening/)
- [How To Secure A Linux Server](https://github.com/imthenachoman/How-To-Secure-A-Linux-Server)
---
#### Guidelines and Standards

- [OWASP IoT Top 10](https://owasp.org/www-project-internet-of-things/)
- [IoT Security Verification Standard (ISVS)](https://github.com/OWASP/IoT-Security-Verification-Standard-ISVS)
- [ETSI EN 303 645 - IoT Security Standard](https://www.etsi.org/deliver/etsi_en/303600_303699/303645/02.01.01_60/en_303645v020101p.pdf)
- [NIST IoT Cybersecurity Framework](https://www.nist.gov/programs-projects/nist-cybersecurity-iot-program)

#### Hardening Guides

- [IoT Device Hardening Best Practices](https://www.cisa.gov/sites/default/files/publications/CISA-IoT-Security-Guidance.pdf)
- [Embedded Linux Hardening](https://embeddedsecurity.io/)
- [Zephyr RTOS Security Features](https://docs.zephyrproject.org/latest/security/index.html)

### Incident Response

- [IoT Forensics and Incident Response](https://www.sans.org/white-papers/38505/)
- [Embedded Device Forensics](https://www.sciencedirect.com/science/article/pii/S2666281720300019)

---

## Learning Resources

### Training Platforms

- [OpenSecurityTraining2](https://p.ost2.fyi/courses)
- [Exploit Education](https://exploit.education/)
- [Azeria Labs](https://azeria-labs.com/)
- [cryptopals](https://cryptopals.com)
### Cheatsheets

- [Hardware Hacking Cheatsheet](https://github.com/arunmagesh/hw_hacking_cheatsheet)
- [Nmap Tutorial](https://github.com/gnebbia/nmap_tutorial)
- [Pentest Hardware Handbook](https://github.com/unprovable/PentestHardware)
- [THC's favourite Tips, Tricks & Hacks](https://github.com/hackerschoice/thc-tips-tricks-hacks-cheat-sheet)
- [Cross Cache Attack CheetSheet](https://u1f383.github.io/linux/2025/01/03/cross-cache-attack-cheatsheet.html)
### Vulnerability Guides

- [OWASP IoT Top 10 2018 Mapping](https://scriptingxss.gitbook.io/owasp-iot-top-10-mapping-project/)
- [Reflecting on OWASP IoT Top 10](https://embedi.org/blog/reflecting-upon-owasp-top-10-iot-vulnerabilities/)
- [Hardware Toolkits for IoT Security Analysis](https://defcon-nn.ru/0x0B/Hardware%20toolkits%20for%20IoT%20security%20analysis.pdf)
- [CVE North Stars](https://cve-north-stars.github.io)
- [IoT Vulnerabilities with CVE and PoC](https://github.com/z1r00/IOT_Vul)
- [Linux Privilege Escalation](https://tbhaxor.com/linux-privilege-escalation/)
### Pentesting Guides

- [Shodan Pentesting Guide](https://community.turgensec.com/shodan-pentesting-guide/)
- [OWASP Firmware Security Testing Methodology](https://scriptingxss.gitbook.io/firmware-security-testing-methodology/)
- [Modern Vulnerability Research on Embedded Systems](https://breaking-bits.gitbook.io/breaking-bits/vulnerability-discovery/reverse-engineering/modern-approaches-toward-embedded-research)
- [Awesome Embedded Systems Vulnerability Research](https://github.com/IamAlch3mist/Awesome-Embedded-Systems-Vulnerability-Research)

### YouTube Channels

- [Joe Grand](https://www.youtube.com/@JoeGrand)
- [LiveOverflow](https://www.youtube.com/channel/UClcE-kVhqyiHCcjYwcpfj9w)
- [Binary Adventure](https://www.youtube.com/channel/UCSLlgiYtOXZnYPba_W4bHqQ)
- [EEVBlog](https://www.youtube.com/user/EEVblog)
- [Craig Smith](https://www.youtube.com/channel/UCxC8G4Oeed4N0-GVeDdFoSA)
- [IoTSecurity101](https://www.youtube.com/channel/UCe2mJv2FPRFhYJ7dvNdYR4Q)
- [Besim ALTINOK](https://www.youtube.com/channel/UCnIV7A3kDL4JXJEljpW6TRQ/playlists)
- [Ghidra Ninja](https://www.youtube.com/channel/UC3S8vxwRfqLBdIhgRlDRVzw)
- [Cyber Gibbons](https://www.youtube.com/channel/UC_IYERSoSwdR7AA5P41mYTA)
- [Scanline](https://www.youtube.com/channel/UCaEgw3321ct_PE4PJvdhXEQ)
- [Aaron Christophel](https://www.youtube.com/c/12002230/videos)
- [Valerio Di Giampietro](https://www.youtube.com/c/MakeMeHack)
- [Gamozo Labs - Printer Hacking](https://www.youtube.com/watch?v=2LVtEoQA8Qo)
### Books

#### Hardware Hacking

- [The Hardware Hacking Handbook - Jasper van Woudenberg & Colin O'Flynn (2021)](https://books.google.co.in/books?id=DEqatAEACAAJ)
- [Practical Hardware Pentesting - Jean-Georges Valle (2021)](https://www.packtpub.com/product/practical-hardware-pentesting/9781789619133)
- [Practical Hardware Pentesting 2nd Edition (2023)](https://www.packtpub.com/product/practical-hardware-pentesting-second-edition/9781803249322)
- [Hardware Hacking: Have Fun While Voiding Your Warranty - Joe Grand (2004)](https://www.elsevier.com/books/hardware-hacking/grand/978-1-932266-83-2)
- [Hacking the Xbox - Andrew "bunnie" Huang (2013)](https://www.nostarch.com/xboxfree)
- [The Art of PCB Reverse Engineering - Keng Tiong (2015)](https://www.amazon.in/Art-Pcb-Reverse-Engineering-Unravelling/dp/1499323441)
- [Manual PCB-RE: The Essentials - Keng Tiong (2021)](https://www.amazon.in/Manual-PCB-RE-Essentials-Keng-Tiong/dp/B0974Z3NDS)
- [Hardware Security Training, Hands-on! (2023)](https://link.springer.com/book/10.1007/978-3-031-31034-8)
- [Hardware Security: Challenges and Solutions (2025)](https://www.amazon.in/Hardware-Security-Challenges-Ashutosh-Mishra/dp/3031812123)
- [Mastering Hardware Hacking (2025)](https://www.amazon.in/Hacking-Machine-Engineering-Hardware-Embedded/dp/B0F29WV5HF)
- [Ultimate Hardware Hacking Gear Guide](https://github.com/jcldf/ultimate-hardware-hacking-gear-guide-)
- [Microcontroller Exploits (2024)](https://nostarch.com/microcontroller-exploits)
#### Firmware and Reverse Engineering

- [The Firmware Handbook - Jack Ganssle (2004)](https://www.amazon.com/Firmware-Handbook-Embedded-Technology/dp/075067606X)
- [Learning Linux Binary Analysis - Ryan O'Neill (2016)](https://www.packtpub.com/en-bg/product/learning-linux-binary-analysis-9781782167112)
- [Practical Binary Analysis - Dennis Andriesse (2023)](https://nostarch.com/binaryanalysis)
- [Fuzzing Against the Machine (2023)](https://www.packtpub.com/product/fuzzing-against-the-machine/9781804614976)
- [Ghidra Software Reverse Engineering 2nd Edition (2025)](https://www.amazon.in/Ghidra-Software-Reverse-Engineering-Beginners-Second/dp/B0DJGQ91R5)
- [The Definitive Handbook on Reverse Engineering Tools (2025)](https://www.amazon.in/Definitive-Handbook-Reverse-Engineering-Tools-ebook/dp/B0F29HLW5B)
#### IoT Security

- [Abusing the Internet of Things - Nitesh Dhanjani (2015)](https://www.amazon.in/Abusing-Internet-Things-Blackouts-Freakouts-ebook/dp/B013VQ7N36)
- [IoT Penetration Testing Cookbook - Aaron Guzman & Aditya Gupta (2017)](https://www.packtpub.com/networking-and-servers/iot-penetration-testing-cookbook)
- [Practical IoT Hacking: The Definitive Guide (2021)](https://nostarch.com/practical-iot-hacking)
- [PatrIoT: Practical and Agile Threat Research for IoT (2022)](https://link.springer.com/article/10.1007/s10207-022-00633-3)
---
#### Wireless and RF

- [Inside Radio: An Attack and Defense Guide - Qing Yang, Lin Huang (2018)](https://books.google.co.in/books?id=71NSDwAAQBAJ)
- [Intro to Bluetooth Low Energy - Afaneh (2018)](https://daskalakispiros.com/files/Ebooks/Intro+to+Bluetooth+Low+Energy+v1.1.pdf)
- [Bluetooth LE Security Study Guide (2019)](https://www.bluetooth.com/bluetooth-resources/le-security-study-guide/)
- [Hack the Airwaves: Advanced BLE Exploitation (2023)](https://www.amazon.in/Hack-Airwaves-Exploitation-Techniques-Cybersecurity/dp/B0CFX2S4ZM)

#### Embedded and Mobile

- [Linksys WRT54G Ultimate Hacking - Paul Asadoorian (2007)](https://www.amazon.com/Linksys-WRT54G-Ultimate-Hacking-Asadoorian/dp/1597491667)
- [Android Hacker's Handbook - Joshua Drake (2014)](https://www.amazon.in/Android-Hackers-Handbook-MISL-WILEY-Joshua/dp/812654922X)
- [Embedded Systems Security and TrustZone (2023)](https://embeddedsecurity.io/)

#### NFC/RFID

- [Near Field Communication (NFC): From Theory to Practice (2012)](https://www.amazon.in/Near-Field-Communication-NFC-Practice/dp/1119971098)
- [Security Issues in Mobile NFC Devices - Michael Roland (2024)](https://link.springer.com/book/10.1007/978-3-319-15488-6)

#### Industrial and General Security

- [Applied Cyber Security and the Smart Grid - Eric Knapp & Raj Samani (2013)](https://www.amazon.com/Applied-Cyber-Security-Smart-Grid/dp/1597499986/)
- [Gray Hat Hacking 5th Edition (2018)](https://www.amazon.in/Gray-Hat-Hacking-Ethical-Handbook-ebook/dp/B07D3J9J4H)
- [Black Hat Python 2nd Edition (2021)](https://nostarch.com/black-hat-python-2nd-edition)

#### White Papers and Reports

- [IOActive: State of Silicon Chip Hacking 2025](https://info.ioactive.com/acton/fs/blocks/showLandingPage/a/34793/p/p-009c/t/page/fm/0)

---

### IoT Series

- [IoT Series I-IV](https://www.artresilia.com/iot-series-i-are-people-ready-to-go/)
- [Intro to Embedded RE Series](https://voidstarsec.com/blog/intro-to-embedded-part-1)

## Labs and CTFs

### Vulnerable Applications

- [DVID - Damn Vulnerable IoT Device](https://github.com/Vulcainreo/DVID)
- [IoTGoat - Vulnerable OpenWrt Firmware](https://github.com/scriptingxss/IoTGoat)
- [IoT-vulhub](https://vulntotal-team.github.io/IoT-vulhub/)
- [DVRF - Damn Vulnerable Router Firmware](https://github.com/praetorian-code/DVRF)
- [BLE CTF](https://github.com/hackgnar/ble_ctf)
- [Microcorruption](https://www.microcorruption.com/)
- [ARM-X CTF](https://github.com/therealsaumil/armx)
#### IoT

- [DVID - Damn Vulnerable IoT Device](https://github.com/Vulcainreo/DVID)
- [IoTGoat - Vulnerable OpenWrt Firmware](https://github.com/scriptingxss/IoTGoat)
- [IoT-vulhub](https://vulntotal-team.github.io/IoT-vulhub/)

#### Router/Firmware

- [DVRF - Damn Vulnerable Router Firmware](https://github.com/praetorian-code/DVRF)
- [Damn Vulnerable ARM Router (DVAR)](https://blog.exploitlab.net/2018/01/dvar-damn-vulnerable-arm-router.html)

#### Hardware

- [Hardware Hacking 101](https://github.com/rdomanski/hardware_hacking)
- [Damn Vulnerable Safe](https://insinuator.net/2016/01/damn-vulnerable-safe/)
- [Sticky Fingers DV-Pi](https://whitedome.com.au/re4son/sticky-fingers-dv-pi/)

#### Wireless

- [BLE CTF](https://github.com/hackgnar/ble_ctf)

#### Industrial

- [Damn Vulnerable Chemical Process](https://www.slideshare.net/phdays/damn-vulnerable-chemical-process)
- [Damn Vulnerable SS7 Network](https://www.blackhat.com/asia-17/arsenal.html#damn-vulnerable-ss7-network)

#### VoIP

- [Hacklab VulnVoIP](https://www.vulnhub.com/entry/hacklab-vulnvoip,40/)

### CTF Competitions

- [RHme Series (2015-2017)](https://github.com/Riscure/RHme-2015)
- [IoT Village CTF](https://www.iotvillage.org/)
---
#### Hardware CTFs

- [RHme-2015](https://github.com/Riscure/RHme-2015)
- [RHme-2016](https://github.com/Riscure/Rhme-2016)
- [RHme-2017](https://github.com/Riscure/Rhme-2017)

#### IoT CTFs

- [IoT Village CTF](https://www.iotvillage.org/)
- [IoTSec CTF](https://ctf.iotsec.io/)

#### Embedded/Firmware CTFs

- [Microcorruption](https://www.microcorruption.com/)
- [Emulate to Exploitate](https://exploitthis.ctfd.io)

#### ARM CTFs

- [ARM-X CTF](https://github.com/therealsaumil/armx)
- [Azeria Labs ARM Challenges](https://azeria-labs.com/writing-arm-assembly-part-1/)

### Continuous Learning Platforms

- [Hack The Box](https://www.hackthebox.eu/)
- [Root Me](https://www.root-me.org/)
- [Pwnable.kr](https://pwnable.kr/)
- [CTFtime](https://ctftime.org/)

### Lab Setup

- [IoT Lab Setup Guide](https://github.com/IoT-PTv/IoT-Lab-Setup)
- [Router Analysis Toolkit](https://github.com/0x6d696368/RouterAnalysisToolkit)
- [Webthings Gateway - Raspberry Pi](https://iot.mozilla.org/docs/gateway-getting-started-guide.html)

---

## Research and Community

### Technical Research

- [Dropcam Hacking](https://www.defcon.org/images/defcon-22/dc-22-presentations/Moore-Wardle/DEFCON-22-Colby-Moore-Patrick-Wardle-Synack-DropCam-Updated.pdf)
- [LED Light Hacking](https://youtu.be/Nnb2ct3hc68)
- [PS4 Jailbreak Status](https://wololo.net/ps4-jailbreak-ps4-cfw4dummies/)
- [Lenovo Watch X Privacy Issues](https://www.checkmarx.com/blog/lenovo-watch-watching-you/)
- [Smart Scale Privacy Issues](https://www.checkmarx.com/blog/smart-scale-privacy-issues-iot/)
- [Besder IP Camera Security Analysis](https://github.com/KostasEreksonas/Besder-6024PB-XMA501-ip-camera-security-investigation)
- [Smart Lock Vulnerabilities](http://www.savoringgreens.com/index-3218.html)
- [IoT Vulnerabilities with CVE and PoC](https://github.com/z1r00/IOT_Vul)

### Blogs

- [Team82 Research](https://claroty.com/team82/research)
- [Voidstarsec](https://voidstarsec.com/blog/)
- [wrongbaud](https://wrongbaud.github.io/)
- [Firmware Analysis](https://fwanalysis.blogspot.com/)
- [Exploitee.rs](https://www.exploitee.rs/)
- [Payatu Blog](https://payatu.com/blog/)
- [Raelize Blog](https://raelize.com/blog/)
- [JCJC Dev](http://jcjc-dev.com/)
- [W00tsec](https://w00tsec.blogspot.in/)
- [Devttys0](http://www.devttys0.com/)
- [Embedded Bits](https://embeddedbits.org/)
- [RTL-SDR Blog](https://www.rtl-sdr.com/)
- [Keenlab](https://keenlab.tencent.com/en/)
- [Courk.cc](https://courk.cc/)
- [IoT Security Wiki](https://iotsecuritywiki.com/)
- [Cybergibbons](https://cybergibbons.com/)
- [Firmware.RE](http://firmware.re/)
- [K3170makan](http://blog.k3170makan.com/)
- [Tclaverie](https://blog.tclaverie.eu/)
- [Besimaltinok](http://blog.besimaltinok.com/category/iot-pentest/)
- [Ctrlu](https://ctrlu.net/)
- [IoT Pentest](http://iotpentest.com/)
- [Duo Decipher](https://duo.com/decipher/)
- [Sp3ctr3](http://www.sp3ctr3.me)
- [0x42424242](http://blog.0x42424242.in/)
- [Dantheiotman](https://dantheiotman.com/)
- [Danman](https://blog.danman.eu/)
- [Quentinkaiser](https://quentinkaiser.be/)
- [Quarkslab](https://blog.quarkslab.com)
- [Ice9](https://blog.ice9.us/)
- [F-Secure Labs](https://labs.f-secure.com/)
- [MG.lol](https://mg.lol/blog/)
- [CJHackerz](https://cjhackerz.net/)
- [Bunnie's Blog](https://github.com/sponsors/bunnie/)
- [Synacktiv Publications](https://www.synacktiv.com/publications.html)
- [Cr4.sh](http://blog.cr4.sh/)
- [Ktln2](https://ktln2.org/)
- [Naehrdine](https://naehrdine.blogspot.com/)
- [Limited Results](https://limitedresults.com/)
- [Fail0verflow](https://fail0verflow.com/blog/)
- [Exploit Security](https://www.exploitsecurity.io/blog)
- [Attify Blog](https://blog.attify.com)
- [Jilles.com](https://jilles.com/)
- [Syss Tech Blog](https://blog.syss.com/)
- [HardBreak Wiki](https://www.hardbreak.wiki/)
- [8ksec](https://8ksec.io/)
- [Starlabs](https://starlabs.sg/blog/)
- [boschko.ca](https://boschko.ca/)
- [0xtriboulet](https://steve-s.gitbook.io/0xtriboulet)
- [Nozomi Networks](https://www.nozominetworks.com/blog/)
### Community Platforms

- [IoTSecurity101 Telegram](https://t.me/iotsecurity1011)
- [IoTSecurity101 Reddit](https://www.reddit.com/r/IoTSecurity101/)
- [IoTSecurity101 Discord](https://discord.gg/EH9dxT9)
- [Hardware Hacking Telegram](https://t.me/hardwareHackingBrasil)
- [RFID Discord](https://discord.gg/Z43TrcVyPr)
- [ICS Discord](https://discord.com/invite/CmDDsFK)
### Villages

- [IoT Village](https://www.iotvillage.org/index.html)
- [Car Hacking Village](https://www.carhackingvillage.com/)
- [ICS Village](https://www.icsvillage.com/)
- [Payment Village](https://www.paymentvillage.org/home)
- [RF Hackers](https://rfhackers.com/)
---
### Researchers to Follow

- [Jilles](https://twitter.com/jilles_com)
- [Joe Fitz](https://twitter.com/securelyfitz)
- [Aseem Jakhar](https://twitter.com/aseemjakhar)
- [Cybergibbons](https://twitter.com/cybergibbons)
- [Jasper](https://twitter.com/jzvw)
- [Dave Jones](https://twitter.com/eevblog)
- [bunnie](https://twitter.com/bunniestudios)
- [Ilya Shaposhnikov](https://twitter.com/drakylar)
- [Mark C.](https://twitter.com/LargeCardinal)
- [Aaron Guzman](https://twitter.com/scriptingxss)
- [Yashin Mehaboobe](https://twitter.com/YashinMehaboobe)
- [Arun Magesh](https://www.linkedin.com/in/marunmagesh)
- [Mr-IoT](https://twitter.com/v33riot)
- [QKaiser](https://twitter.com/qkaiser)
- [9lyph](https://twitter.com/9lyph)

---

### Device-Specific Research

#### Cameras

- [ARLO: I'M WATCHING YOU](https://www.synacktiv.com/en/publications/arlo-im-watching-you)
- [Hacking a Tapo TC60 Camera](https://medium.com/@two06/hacking-a-tapo-tc60-camera-e6ce7ca6cad1)
- [Rooting a Hive Camera](https://boredpentester.com/rooting-hive-ip-cameras/)
- [Pwn2Own: Synology BC500 IP Camera](https://claroty.com/team82/research/pivoting-from-wan-to-lan-synology-bc500-ip-camera)
- [Turning Camera Surveillance on its Axis](https://claroty.com/team82/research/turning-camera-surveillance-on-its-axis)
- [Pwn2Own Ireland 2024 – Ubiquiti AI Bullet](https://blog.compass-security.com/2025/06/pwn2own-ireland-2024-ubiquiti-ai-bullet/)

#### Smart Home Devices

- [Hacking a Smart Home Device](https://jmswrnr.com/blog/hacking-a-smart-home-device)
- [The Silent Spy Among Us: Smart Intercom Attacks](https://claroty.com/team82/research/the-silent-spy-among-us-modern-attacks-against-smart-intercoms)
- [Pwnassistant - Home Assistant RCE](https://www.elttam.com/blog/pwnassistant/)
- [Hacking Sonoff Smart Home IoT Device](https://jerinsunny.github.io/blogs/iotsecurity/2025/01/03/sonoff-firmware-extraction.html)

#### Smart Speakers

- [Turning Google smart speakers into wiretaps for $100k](https://downrightnifty.me/blog/2022/12/26/hacking-google-home.html)
- [Smart Speaker Shenanigans: Making the Sonos ONE Sing its Secrets](http://conference.hitb.org/files/hitbsecconf2023ams/materials/D2T1%20-%20Smart%20Speaker%20Shenanigans%20-%20Making%20the%20SONOS%20One%20Sing%20Its%20Secrets%20-%20Peter%20Geissler.pdf)
- [Listen Up: Sonos Over-The-Air Remote Kernel Exploitation and Covert Wiretap](https://www.nccgroup.com/media/uzbp3ttw/bhus24_sonos_whitepaper.pdf)
- [Streaming Zero-Fi Shells to Your Smart Speaker](https://blog.ret2.io/2025/06/11/pwn2own-soho-2024-sonos-exploit/)

#### Printers

- [Pwning a Brother labelmaker, for fun and interop!](https://sdomi.pl/weblog/20-pwning-a-labelmaker/)
- [lexmark printer haxx](https://github.com/blasty/lexmark)
- [Pwn2Own Ireland 2024: Canon imageCLASS MF656Cdw](https://neodyme.io/en/blog/pwn2own-2024_canon_rce/)
- [Print Scan Hacks: Brother devices](https://assets.contentstack.io/v3/assets/blte4f029e766e6b253/blt6495b3c6adf2867f/685aa980a26c5e2b1026969c/vulnerability-disclosure-whitepaper.pdf)

#### Drones

- [DJI Mavic 3 Drone Research: Firmware Analysis](https://www.nozominetworks.com/blog/dji-mavic-3-drone-research-part-1-firmware-analysis)
- [DJI Mavic 3 Drone Research: Vulnerability Analysis](https://www.nozominetworks.com/blog/dji-mavic-3-drone-research-part-2-vulnerability-analysis)
- [DJI - The ART of obfuscation](https://blog.quarkslab.com/dji-the-art-of-obfuscation.html)
- [Local Privilege Escalation on the DJI RM500 Smart Controller](https://icanhack.nl/blog/dji-rm500-privilege-escalation/)

#### Kitchen Appliances

- [Let Me Cook You a Vulnerability: Exploiting the Thermomix TM5](https://www.synacktiv.com/en/publications/let-me-cook-you-a-vulnerability-exploiting-the-thermomix-tm5)

#### NAS Devices

- [A Pain in the NAS: Synology DS920+ Edition](https://claroty.com/team82/research/a-pain-in-the-nas-exploiting-cloud-connectivity-to-pwn-your-nas-synology-ds920-edition)
- [Weekend Destroyer - RCE in Western Digital PR4100 NAS](https://www.flashback.sh/blog/weekend-destroyer-wd-pr4100-rce)
- [Exploiting the Synology TC500 at Pwn2Own Ireland 2024](https://blog.infosectcbr.com.au/2025/08/01/exploiting-the-synology-tc500-at-pwn2own-ireland-2024/)

#### Game Consoles

- [Hacking the Nintendo DSi Browser](https://farlow.dev/2023/03/02/hacking-the-nintendo-dsi-browser)
- [mast1c0re: Exploiting the PS4 and PS5 through a game save](https://mccaulay.co.uk/mast1c0re-introduction-exploiting-the-ps4-and-ps5-through-a-gamesave/)
- [Being Overlord on the Steam Deck with 1 Byte](https://blog.quarkslab.com/being-overlord-on-the-steam-deck-with-1-byte.html)
- [Hacking the XBox 360 Hypervisor](https://icode4.coffee/?p=1047)

#### Phones/Tablets

- [Pixel 6 Bootloader Series](https://eshard.com/posts/pixel6_bootloader)
- [Solo: A Pixel 6 Pro Story](https://starlabs.sg/blog/2025/06-solo-a-pixel-6-pro-story-when-one-bug-is-all-you-need/)
- [Gaining kernel code execution on an MTE-enabled Pixel 8](https://github.blog/2024-03-18-gaining-kernel-code-execution-on-an-mte-enabled-pixel-8/)
- [Bypassing MTE with CVE-2025-0072](https://github.blog/security/vulnerability-research/bypassing-mte-with-cve-2025-0072/)
- [Debugging the Pixel 8 kernel via KGDB](https://xairy.io/articles/pixel-kgdb)
- [A First Glimpse of the Starlink User Terminal](https://www.darknavy.org/blog/a_first_glimpse_of_the_starlink_user_ternimal/)
- [Diving into Starlink's User Terminal Firmware](https://blog.quarkslab.com//starlink.html)

### TrustZone and TEE Research

- [Embedded Systems Security and TrustZone](https://embeddedsecurity.io/)
- [ARM TrustZone: pivoting to the secure world](https://blog.thalium.re/posts/pivoting_to_the_secure_world/)
- [TEE Reversing](https://github.com/enovella/TEE-reversing)
- [A Deep Dive into Samsung's TrustZone - Parts 1-3](https://blog.quarkslab.com/a-deep-dive-into-samsungs-trustzone-part-1.html)
- [Researching Xiaomi's TEE](https://research.checkpoint.com/2022/researching-xiaomis-tee/)
- [Kinibi TEE: Trusted Application Exploitation](https://www.synacktiv.com/en/publications/kinibi-tee-trusted-application-exploitation.html)
- [Reversing Samsung's H-Arx Hypervisor Framework](https://dayzerosec.com/blog/2025/03/08/reversing-samsungs-h-arx-hypervisor-part-1.html)
- [EL3vated Privileges: Glitching Google WiFi Pro from Root to EL3](https://raelize.com/upload/research/2025/Hw_io-USA-2025_EL3vated-Privileges-Glitching-Google-Wifi-Pro-from-Root-to-EL3_v1.0.pdf)

### Pwn2Own Research

- [Your not so "Home Office" - SOHO Hacking at Pwn2Own](http://conference.hitb.org/files/hitbsecconf2023ams/materials/D1T1%20-%20Your%20Not%20So%20Home%20Office%20-%20Soho%20Hacking%20at%20Pwn2Own%20-%20McCaulay%20Hudson%20&%20Alex%20Plaskett.pdf)
- [Pwn2Own Toronto 2023 Series - Parts 1-5](https://blog.compass-security.com/2024/03/pwn2own-toronto-2023-part-1-how-it-all-started/)
- [Pwn2Own: WAN-to-LAN Exploit Showcase](https://claroty.com/team82/research/pwn2own-wan-to-lan-exploit-showcase)
---
## Contributing
Contributions welcome. Submit a PR with new resources following the existing structure.

## License
This collection is provided for educational and research purposes.
