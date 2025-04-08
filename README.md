# ReflexRush 🕹️
Reaction Time Testing Game

## 🎯 Overview

**Reflex Rush** is a fast-paced reaction game developed for the **DE10-Lite FPGA**. Designed using Verilog HDL, the game challenges one or two players to react to signals as quickly and accurately as possible. It combines real-time inputs, LED/Switch logic, 7-segment displays, VGA output, and FSM-based control to deliver a full hardware-based experience.

---

## 🎮 Game Modes

### 🧍 Single Player (SP)
- Wait for a random LED to light up and react as quickly as possible.
- The system measures your reaction time in milliseconds.
- Best reaction time is tracked across all trials.

### 👥 Multiplayer (MP)
- Players take turns matching switches to lit LEDs as fast and accurately as they can, and have to flick up the corresponding switch.
- Scoring is based on who reacts faster and correctly.
- Best time and corresponding player number (i.e. either P1 or P2 is displayed on the 7-segment display) are tracked across all trials.

---

## ⚙️ Features

- **Random Delay Generator**  
  12-bit LFSR creates a randomized wait time before the LED triggers.

- **24-bit Reaction Timer**  
  Measures reaction time with high precision using chained modulo counters.

- **High Score Tracking**  
  Records the best score for both SP and MP modes.

- **FSM-Based Control**  
  Ensures synchronized gameplay and proper validation of inputs.

- **Edge Detection**  
  Cleans button presses to prevent false triggers.

- **Switch-to-LED Matching Logic**  
  Validates player inputs in multiplayer mode.

- **7-Segment HEX Display**  
  Shows current reaction time and high scores.

- **VGA Output**  
  - Displays “HOLD” during wait phase.  
  - Shows “GO” when it's time to react.

- **Clock Dividers**  
  Generate 1 kHz and 25 MHz clocks from the 50 MHz system clock.

---

## 👨‍💻 Contributors

- **Harmandeep Arneja** 

- **Umer Shaikh** Github Link: https://github.com/TAShaikhh

Both collaborated on testing, verification, and debugging.

---

## 🧠 Inspiration & Purpose

This project demonstrates practical applications of digital logic design, FSMs, VGA protocols, and FPGA development. It highlights how embedded systems can support real-time, interactive experiences entirely in hardware. It incorporates combinational logic to handle signal selection, timing control, and real-time validation using multiplexers, arithmetic units, and logic gates. Sequential logic components such as D flip-flops, shift registers, and finite state machines are used to store reaction data, manage game states, and accurately measure reaction durations across trials using counters and timers.

---

## 🗂️ Module Overview

| Modules            | Description                          |
|--------------------|--------------------------------------|
| `reflex_rush_top.v`| Top-level integration module         |
| `vga_controller.v` | VGA screen logic for game UI         |
| `reaction_mode_1.v`| Single player game logic             |
| `reaction_mode_2.v`| Multiplayer game logic               |
| `high_score.v`     | Tracks and displays best scores      |
| `counter_mod.v`    | Modular counters for timing          |
| `fsm_z_control.v`  | FSM control unit                     |

| Individual File    | Description                          |
|--------------------|--------------------------------------|
| `png_to_mem.py`    | Image converter for ROM visuals      |

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

## 🚀 Run the Game

To deploy the design:

1. Open Quartus Prime.
2. Load all corresponding files. Set `reflex_rush_top.v` as the top-level entity.
3. Compile and do PIN ASSIGNMENTS (for VGA also) for the DE10-Lite board. Open Device Programmer and press Start.
4. Connect the VGA monitor and interact using switches, LEDs, and keys.

---

## 💬 Feedback & Contributions

Feel free to fork, contribute, or suggest improvements! This project is open-source and made for learning and fun.


