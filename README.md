# IR Remote-Controlled Robot 🤖

Control your robot wirelessly using an IR remote! This project demonstrates how to use an IR remote to control the direction of a motorized robot. 🕹️ Perfect for beginners exploring robotics and electronics! 🚀

---

## 📜 Features
- **Wireless Control:** Control your robot's movements (Up, Down, Left, Right) with ease. 
- **Efficient Motor Control:** Manage two motors simultaneously using simple IR commands.
- **Easy Setup:** Minimal components, quick assembly, and simple code.

---

## 🛠️ Components Required

| Component          | Quantity |
|--------------------|----------|
| Arduino UNO/Nano   | 1        |
| IR Receiver Module | 1        |
| DC Motors          | 2        |
| Motor Driver (L293D)| 1        |
| IR Remote          | 1        |
| Jumper Wires       | As needed|
| Breadboard         | 1        |

---

## ⚡ Circuit Diagram

Connect the components as follows:

1. **IR Receiver**:
   - Signal pin -> Pin 3 on Arduino
   - VCC -> 5V
   - GND -> GND

2. **Motor Driver (L293D)**:
   - Motor 1 pins -> Arduino pins 6 and 5
   - Motor 2 pins -> Arduino pins 11 and 10
   - Power and Ground -> 5V and GND

3. **Motors**:
   - Connect two DC motors to the output pins of the L293D motor driver.

---

## 🚀 How to Use

1. **Clone or Download the Repository**:
   ```bash
   git clone https://github.com/yourusername/ir-remote-robot.git
   ```

2. **Upload the Code**:
   - Open the provided `IR_remote_control.ino` file in the Arduino IDE.
   - Select your board and COM port.
   - Upload the code to your Arduino.

3. **Test the IR Remote**:
   - Press the remote buttons corresponding to the movements:
     - **UP** (Move forward)
     - **DOWN** (Move backward)
     - **LEFT** (Turn left)
     - **RIGHT** (Turn right)

4. **Watch Your Robot Move! 🎉**

---

## 🎯 Working Principle
- The **IR receiver module** decodes the signals sent by the IR remote.
- Each button on the remote has a unique code.
- The Arduino reads the code and triggers the corresponding motor actions through the **L293D motor driver**.

---

## 📋 Code Breakdown

### Key Sections:

- **IR Library Setup:**
  ```cpp
  #include <IRremote.h>
  IRrecv irrecv(3);
  decode_results results;
  ```
- **Motor Pins:**
  ```cpp
  #define m11 6
  #define m12 5
  #define m21 11
  #define m22 10
  ```
- **Command Handling:**
  ```cpp
  switch(value)
  {
    case 34935 : // UP
      digitalWrite(m11, HIGH);
      digitalWrite(m12, LOW);
      digitalWrite(m21, HIGH);
      digitalWrite(m22, LOW);
      break;
    ...
  }
  ```

---

## 📸 Demo

*(Include a photo or video of the working robot here)*

---

## 🤔 Future Enhancements
- Add more IR commands for additional functionality.
- Use an LCD to display the received IR codes for debugging.
- Replace IR control with Bluetooth or Wi-Fi for greater range.

---

## 🧑‍💻 Author
Developed with ❤️ by [dharanish](https://github.com/dharanishmadesh). Feel free to connect!

---

## 📄 License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

Happy Building! 🛠️✨
