# FPGA Ping Pong Game (VHDL – Spartan-3E FPGA)

A fully hardware-implemented Ping Pong game built using **VHDL**, designed for the **Xilinx Spartan-3E FPGA**.  
All game logic, VGA rendering, player movement, ball physics, and timing control are implemented in RTL without a CPU.

This project was developed as part of **COE758 — Digital Systems Engineering** and demonstrates strong skills in:
- Digital design (FSMs, pipelines, counters, timing logic)
- VHDL development & structural hierarchy
- Hardware debugging & simulation
- VGA display systems
- FPGA synthesis, implementation, and constraints management

---

## 🎮 **Game Features**
- **Real-time VGA output** at 640×480 @ 60 Hz  
- **Hardware ball physics** (reflection, velocity, boundaries)
- **Paddle control** via FPGA input switches/buttons  
- **Rendering pipeline** built entirely in combinational + sequential logic  
- **Top-level SoC-style integration** connecting all subsystems

---

## 🧩 **Project Architecture**

## 🧩 Project Architecture

fpga-ping-pong-game/
│
├── src/                     # Synthesizable RTL (core VHDL design)
│   ├── pong_top.vhd
│   ├── ball_physics.vhd
│   ├── player_movement.vhd
│   ├── field_renderer.vhd
│   ├── refresh_divider.vhd
│   └── vga_timing.vhd
│
├── sim/                     # Testbench / simulation files
│   └── pong_top.vhd
│
├── docs/                    # Reports, logs, generated tool output
│   ├── PINGPONG.gise
│   ├── PINGPONG.xise
│   ├── default_waveform1.pdf
│   ├── pong_top_guide.ncd
│   ├── pong_top_pad.csv
│   ├── pong_top_summary.html
│   └── pong_top_usage.xml
│
└── README.md
---

## 🧠 **Module Overview**

### **`pong_top.vhd`**
Top-level integration module connecting:
- VGA timing generator  
- Player controls  
- Physics engine  
- Rendering pipeline  

### **`vga_timing.vhd`**
Generates all VGA timing signals:
- HSYNC / VSYNC  
- Active video region  
- Pixel clocks  
- Horizontal/vertical counters  

### **`ball_physics.vhd`**
Implements:
- Ball velocity
- Collision detection
- Boundary reflection logic

### **`player_movement.vhd`**
Reads paddle inputs and enforces boundary rules.

### **`field_renderer.vhd`**
Draws:
- Ball  
- Paddles  
- Midline  
- Background video signal  

### **`refresh_divider.vhd`**
Clock divider used to control animation speed and debounce movement.

---

## 🛠️ **Development Tools**
- **Xilinx ISE Design Suite**  
- **ModelSim / ISim** for simulation  
- **VGA display** for output  
- **Spartan-3E FPGA development board**

---

## 🚀 **How to Build & Run**
1. Open the project in **Xilinx ISE**  
2. Add all VHDL files inside `src/`  
3. Set `pong_top.vhd` as the top module  
4. Generate the bitstream  
5. Program the Spartan-3E FPGA  
6. Connect VGA output to a monitor  
7. Play!

---

## 📌 **Future Improvements**
- Scoreboard display  
- AI opponent  
- Sound generation (PWM)  
- Moving background / animations  

---

## 📄 License
This project is for educational & portfolio purposes.
