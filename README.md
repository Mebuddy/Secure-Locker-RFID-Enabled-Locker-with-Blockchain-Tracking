# RFID-Based Control System

This repository contains the code and documentation for an RFID-based control system built around an Arduino UNO microcontroller. The system includes an RFID-RC522 module, LEDs, a piezo buzzer, a pushbutton, a solenoid, a relay module, and a 12V battery. It provides visual and audible feedback, manual reset capabilities, and solenoid control for locking/unlocking mechanisms.

## Components

| Sl. No. | Component                | Remarks                                             |
|---------|--------------------------|-----------------------------------------------------|
| 1       | Arduino UNO              | Microcontroller board based on the ATmega328P       |
| 2       | RFID-RC522               | RFID reader/writer module, operates at 3.3V         |
| 3       | LED: Two Pin (green)     | Green indicator LED, requires current-limiting resistor |
| 4       | LED: Two Pin (red)       | Red indicator LED, requires current-limiting resistor   |
| 5       | Piezo Buzzer             | Emits sound when powered                            |
| 6       | Pushbutton               | Momentary tactile switch                            |
| 7       | Solenoid                 | Electromechanical device                            |
| 8       | 1 Channel 5V Relay Module | Electrically operated switch                         |
| 9       | 12V Battery (mini)       | Power source providing 12V supply                   |

## Wiring Details

### Arduino UNO
- **D13** connected to the anode of the green LED
- **GND** connected to:
  - Cathodes of green and red LEDs
  - Pushbutton
  - Piezo buzzer
  - RFID-RC522
  - GND of the relay module
- **Reset** connected to one terminal of the pushbutton
- **D12** connected to one terminal of the piezo buzzer
- **D11** connected to the anode of the red LED
- **Vin** connected to the positive terminal of the 12V battery
- **3.3V** connected to the 3.3V of the RFID-RC522
- **D9 to D5** connected to IRQ, MISO, MOSI, SCK, and SDA of the RFID-RC522 respectively
- **D10** connected to the IN pin of the relay module

### RFID-RC522
- **SDA, SCK, MOSI, MISO, IRQ** connected to corresponding pins on the Arduino UNO
- **GND** connected to Arduino UNO GND
- **RST** connected to Arduino UNO Reset via pushbutton
- **3.3V** connected to Arduino UNO 3.3V

### LED: Two Pin (green)
- **Anode** connected to Arduino UNO D13
- **Cathode** connected to Arduino UNO GND

### LED: Two Pin (red)
- **Anode** connected to Arduino UNO D11
- **Cathode** connected to Arduino UNO GND

### Piezo Buzzer
- **Pin 1** connected to Arduino UNO D12
- **Pin 2** connected to Arduino UNO GND

### Pushbutton
- **Pin 1** connected to Arduino UNO Reset
- **Pin 2** connected to Arduino UNO GND

### Solenoid
- **Pin1** connected to COM of the relay module
- **Pin2** connected to N.O. of the relay module

### 1 Channel 5V Relay Module
- **VCC+** connected to the positive terminal of the 12V battery
- **VCC- (GND)** connected to Arduino UNO GND
- **IN** connected to Arduino UNO D10
- **COM** connected to one terminal of the solenoid
- **N.O.** connected to the other terminal of the solenoid

### 12V Battery (mini)
- **+** connected to VCC+ of the relay module and Arduino UNO Vin
- **-** connected to VCC- (GND) of the relay module and Arduino UNO GND


## Getting Started

### Prerequisites
- Arduino IDE
- Arduino UNO
- Necessary components as listed above

### Installation
1. **Clone the repository**
   ```sh
   git clone https://github.com/your-username/rfid-control-system.git
   ```
2. **Open the project in Arduino IDE**
   Open the `.ino` file in the Arduino IDE.

3. **Upload the code**
   Connect your Arduino UNO to your computer and upload the code.

## Usage
1. **Power the circuit**
   Connect the 12V battery to power the system.

2. **Test the components**
   Ensure the LEDs, piezo buzzer, RFID module, pushbutton, relay, and solenoid are functioning correctly.

3. **Use the RFID tags**
   Present RFID tags to the RFID-RC522 module to trigger the system. The LEDs and buzzer will provide feedback, and the solenoid will be controlled via the relay module.
