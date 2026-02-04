# Custom Meshtastic LoRa PCB (ESP32 + RA-01SH)

![Project Status](https://img.shields.io/badge/Status-Prototyping-yellow)
![License](https://img.shields.io/badge/License-Open%20Hardware-blue)
![Meshtastic](https://img.shields.io/badge/Meshtastic-Compatible-green)

A custom-designed, compact PCB for Meshtastic LoRa networking. This board integrates the ESP32-WROOM-32E and Ai-Thinker RA-01SH (SX1262) with native USB-C charging and data support. 

Designed for easy manufacturing via JLCPCB using mostly "Basic" library parts to minimize assembly costs.

![PCB Preview](https://github.com/user-attachments/assets/fb45a827-2ac1-4804-96d0-5a5ca39ca618)


---

## 📺 Project Video
Watch the full design and ordering process here:

[![Watch the Video](https://img.youtube.com/vi/XLY1TtWzttY/0.jpg)](https://www.youtube.com/watch?v=XLY1TtWzttY)

---

## 🌟 Key Features
* **MCU:** ESP32-WROOM-32E (WiFi + Bluetooth).
* **LoRa:** Ai-Thinker RA-01SH (SX1262) for long-range communication (915MHz / 868MHz).
* **Native USB-C:** Supports direct firmware flashing and debugging via CH340C.
* **Power Management:**
    * Integrated Li-Ion Battery Charger (MCP73831) @ 500mA.
    * 3.3V LDO (AP2112K) for stable system power.
    * **Auto-Reset Circuit:** Flashes code automatically without holding buttons.
* **Battery:** JST-PH 2.0mm connector (Standard single-cell LiPo/Li-Ion).

## 🔌 Pin Map / Netlist

| ESP32 Pin | Function | Description |
| :--- | :--- | :--- |
| **GPIO 5** | NSS | LoRa Chip Select |
| **GPIO 18** | SCK | SPI Clock |
| **GPIO 19** | MISO | SPI MISO |
| **GPIO 23** | MOSI | SPI MOSI |
| **GPIO 26** | DIO1 | LoRa Interrupt |
| **GPIO 14** | RESET | LoRa Reset |
| **GPIO 33** | BUSY | LoRa Busy Status |
| **GPIO 0** | BOOT | Boot Button / Auto-Reset |
| **EN** | RESET | System Reset |

## 🛠️ Manufacturing (JLCPCB)

This board was designed using EasyEDA with the LCSC component library in mind.

### 1. Files
* **Gerbers:** Use the `.zip` file in the `/gerber` folder.
* **BOM:** `BOM.csv` (Contains LCSC Part numbers).
* **CPL:** `PickAndPlace.csv` (Component placement data).

### 2. Critical Assembly Notes
* **Battery Connector:** The footprint supports JST-PH 2.0. **WARNING:** There is no standard polarity for JST cables. **Check your battery polarity against the PCB silkscreen (+/-) before plugging it in!**
* **Antenna:** The board uses a 0Ω resistor bridge to a u.FL/IPEX connector. Ensure the ground shielding vias are printed correctly.
* **Cost Optimization:** Most passives (Resistors, Caps) and the CH340C are selected from the JLCPCB "Basic" library to avoid extra loading fees.

## ⚠️ Disclaimer
This is an open-source hardware project. While the design has been checked against standard design rules, it is provided "as is" without warranty. Double-check all connections and battery polarity before powering up.

---

## 📌 Author

Created by [**ar_titumir**](https://github.com/ar-titumir)  
If this tool helps your productivity, please give a ⭐ on GitHub. 

https://github.com/ar-titumir 


**Date:** January 2026
