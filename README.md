# 🧮 8051-Based Visitor Counter Using IR Sensors

## 📖 Overview

This project is designed to automatically count the number of visitors entering and exiting a place (such as a room or hall) using an 8051 microcontroller. It uses two IR sensors to detect movement and a 16x2 LCD to display the current count.

---

## 📦 Components Used

| Component         | Quantity | Description                          |
|------------------|----------|--------------------------------------|
| 8051 Microcontroller | 1    | Controls logic and interfacing       |
| 16x2 LCD Display  | 1        | Displays current visitor count       |
| IR Sensor Modules | 2        | Detect entry and exit movement       |
| 10K Potentiometer | 1        | Adjusts LCD contrast                 |
| 12 MHz Crystal Oscillator | 1 | Clock signal for MCU              |
| 33pF Capacitors   | 2        | Used with crystal oscillator         |
| 10µF Capacitor    | 1        | Used in reset circuit                |
| 10KΩ Resistor     | 1        | Pull-up for reset                    |
| Push Button       | 1        | Manual reset                         |
| 330Ω Resistor     | 1        | LCD backlight current limiter        |
| Power Supply      | 5V DC    | Powers the entire circuit            |
| Connecting Wires  | —        | For hardware interconnection         |

---

## ⚙️ Circuit Connections

### Microcontroller (8051)

| MCU Pin     | Connected To         | Description                     |
|-------------|----------------------|---------------------------------|
| P1.0–P1.7   | LCD D0–D7            | 8-bit data bus to LCD           |
| P3.6        | LCD RS               | Register Select control         |
| P3.7        | LCD E                | Enable control                  |
| P2.0        | IR Sensor 1 OUT      | Detects Entry                   |
| P2.1        | IR Sensor 2 OUT      | Detects Exit                    |
| XTAL1/2     | Crystal + 33pF Caps  | Clock source for MCU            |
| RST         | 10µF Cap, 10KΩ Resistor, Push Button | Reset circuit  |
| Vcc, GND    | +5V, GND             | Power connections               |

### LCD (16x2)

| LCD Pin | Connection              | Description                     |
|---------|--------------------------|---------------------------------|
| VSS     | GND                      | Ground                          |
| VDD     | +5V                      | Power supply                    |
| V0      | Potentiometer middle pin | LCD contrast control            |
| RS      | P3.6                     | Register select                 |
| RW      | GND                      | Write mode only                 |
| E       | P3.7                     | Enable                          |
| D0–D7   | P1.0–P1.7                | Data lines                      |
| A (LED+) | +5V via 330Ω resistor   | Backlight                       |
| K (LED−) | GND                     | Backlight                       |

### IR Sensors

| IR Sensor Pin | Connection  | Description                |
|---------------|------------|----------------------------|
| VCC           | +5V        | Power supply               |
| GND           | GND        | Ground                     |
| OUT (Sensor 1)| P2.0       | Entry detection            |
| OUT (Sensor 2)| P2.1       | Exit detection             |

---

## 🔄 Operation

- When a person **enters** the area, IR Sensor 1 (connected to P2.0) is triggered first, followed by IR Sensor 2 (P2.1). The system recognizes this sequence as an **entry** and increments the count.
  
- When a person **exits**, the reverse happens: IR Sensor 2 (P2.1) is triggered first, followed by IR Sensor 1 (P2.0). The system recognizes this sequence as an **exit** and decrements the count.

- The updated count is continuously displayed on the LCD.

---

## 🚀 Applications

- Automatic Room/Conference Hall Visitor Counter  
- Entry Management in Libraries, Labs, or Offices  
- Smart Home People Tracking  
- Automated Attendance Counting Systems  
- Visitor Logging Systems in Security Booths

---

## 👨‍💻 Developed By
**Konathala Chanikya**  
B.Tech in Electronics and Communication Engineering  
