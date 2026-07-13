<div align="center">

# Ashmit Singh

**Robotics & Embedded Systems** · Electronics Engineering (VLSI Design & Technology) @ VIT Vellore

Building robots, embedded systems, and other things that probably should've worked the first time.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-ashmitsingh7-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ashmitsingh7)
[![Email](https://img.shields.io/badge/Email-ashmitsingh719%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:ashmitsingh719@gmail.com)

</div>

<br/>

## About

I'm an electronics engineering undergrad at VIT Vellore, spending most of my time on **robotics, embedded systems, and computer vision** — not because I've mastered them, but because they keep surprising me with how much there is left to learn.

I care about building **complete systems**, not just isolated scripts. That usually means moving across the whole stack on a project: sensor selection and signal integrity, firmware and real-time control, perception algorithms, and the software layer that ties it all together for a human to actually use. On the hardware side, I'm going deeper into **VLSI and digital design** — RTL, FPGA implementation, and increasingly RISC-V — which is closer to what my degree is actually in, even if most of my project time still goes to robotics.

<br/>
<hr/>

## Currently Building

### Industrial Dimensioning, Weighing & Scanning System (DWS)
`Internship — Delhivery Limited` · May – Jul 2026 · `repository private — company confidentiality`

An 8-node ROS2 perception system built for a live warehouse induction line, replacing manual volumetric measurement and sustaining roughly one parcel every six seconds. The brief was simple to state and hard to build: scan a parcel, capture its depth image, measure its dimensions, read the barcode, log the weight — all without an operator touching it.

**Technical implementation**
- Integrated a multi-sensor capture stack — an Essae digital weighing scale over serial, a USB barcode scanner, and a vision path that moved from an initial Cognex camera to an Intel RealSense D455 depth sensor — into one synchronized pipeline
- Built a 12-stage classical computer vision pipeline on the depth stream: RANSAC-based floor-plane segmentation followed by PCA-based oriented bounding-box fitting to recover parcel dimensions
- Designed an orchestrator finite-state machine that gates the vision pipeline on scale-stability, eliminating false triggers from operator hands or trolleys crossing the sensor's field of view
- Built a local-first data layer on SQLite (write-ahead logging) behind a FastAPI backend, with a live WebSocket dashboard for floor operators
- Prototyped an AI-assisted segmentation approach for separating parcels from a cluttered conveyor surface — it handled messy point clouds better than the classical method alone, but the added inference latency didn't fit the pipeline's timing budget, so production runs a geometry-first hybrid with the learned model as a fallback path rather than the primary one

**Skills demonstrated:** end-to-end systems architecture across sensors, firmware, and software · ROS2 node design and pub/sub messaging · classical computer vision (RANSAC, PCA, oriented bounding boxes) · finite-state machine design for real-time gating logic · REST/WebSocket backend design · embedded data reliability patterns (WAL, watchdogs, recovery) · debugging distributed systems under hard latency budgets

`ROS2` `RealSense D455` `Point Clouds` `FastAPI` `SQLite (WAL)` `WebSocket HMI` `Python`

<br/>
<hr/>

## Projects

### 1 · [Team Vyadh — Mars Rover Manipulator](https://github.com/ashmitsingh7/Team-Vyadh-Robotic-Arm)

As a senior core member of the robotic-arm domain on VIT's Martian rover team, I worked on the 5-DOF manipulator built for the International Rover Challenge — a system rated for roughly 1000–1500 kgf·cm of joint torque under planetary terrain-sampling loads, where every gram and every volt matters because the whole arm has to survive a rover chassis moving over rough ground.

**Technical implementation**
- Designed a cascaded power distribution system — 12V for actuators, 6V for logic — with isolated grounding between the two domains to keep noisy motor currents from corrupting sensor and control signals under dynamic loading
- Fabricated precision 3D-printed mounts for AS5600 magnetic joint encoders, which needed to hold tight alignment under vibration to keep feedback accurate
- Tuned closed-loop PID control on the encoder feedback to get joint positioning accuracy under 1°, which is what actually made terrain-sampling maneuvers repeatable
- Spent the most time on the differential wrist mechanism — the one subsystem where mechanical coupling between two joints made naive control tuning fail, and getting it stable took several competition-cycle iterations

**Skills demonstrated:** power system design (cascaded voltage domains, isolated grounding) · closed-loop PID control · encoder-based feedback (AS5600) · mechanical-electrical integration under vibration and load · debugging under competition time pressure

`C++` `ESP32` `Encoder Feedback` `Differential Wrist Mechanism` `Closed-Loop PID`

**Result:** 17th place overall, International Rover Challenge (IRC) 2026

---

### 2 · [Gesture-Controlled Robotic Arm](https://github.com/ashmitsingh7/robotic-arm-vision-control)

A personal project built specifically to understand a full perception-to-actuation chain end to end — not just one layer of it. A laptop webcam feeds MediaPipe's hand-pose model, which gets translated into discrete gesture classes, sent as a joint command over a lightweight TCP protocol, and executed on an ESP32/Arduino Nano pipeline driving the physical servos.

**Technical implementation**
- Built real-time hand-pose estimation and gesture classification on top of MediaPipe, running on live webcam input rather than pre-recorded frames
- Designed a lightweight TCP messaging protocol to carry joint commands from the host PC to the embedded controller with minimal framing overhead
- Mapped classified gestures to coordinated multi-joint servo actuation on the ESP32/Arduino Nano side
- The core engineering problem wasn't any single stage — it was the cumulative latency budget across capture, inference, network transport, and actuation, and being deliberate about where each millisecond was allowed to go

```
Camera → MediaPipe → Gesture Classification → TCP → ESP32 → Servo Control
```

**Skills demonstrated:** real-time computer vision (MediaPipe hand tracking) · low-latency network protocol design (TCP) · embedded actuation and servo control (ESP32/Arduino) · end-to-end latency budgeting across a perception-to-actuation pipeline

`Python` `OpenCV` `MediaPipe` `ESP32` `TCP/IP`

---

### 3 · [PID Hardware Accelerator](https://github.com/ashmitsingh7/PID_Hardware_Accelerator)

A deliberate bridge project between the control-systems work from robotics and the VLSI side of my degree — the question being whether a PID controller implemented directly in hardware can genuinely outperform the same control loop running in software.

**Technical implementation**
- Implementing the controller as synthesizable RTL in Verilog rather than a behavioral model, with fixed-point arithmetic replacing floating-point to keep the datapath hardware-realistic
- Structuring the design as a pipelined datapath to keep throughput high without serializing every multiply-accumulate step
- Working through timing closure in ModelSim, where simulated timing doesn't always match intuition built from software control-loop design — this is the part still in progress, since FPGA implementations tend to surface edge cases that don't show up until you're looking at actual waveforms

**Skills demonstrated:** RTL design in Verilog/SystemVerilog · fixed-point arithmetic implementation for control hardware · pipelined digital datapath design · timing analysis and simulation (ModelSim) · Quartus synthesis flow

`Verilog` `SystemVerilog` `Quartus` `ModelSim` `RTL Design` `Fixed-Point Arithmetic`

*Status: work in progress*

---

### 4 · [RISC-V ReRAM In-Memory Computing SoC](https://github.com/ashmitsingh7/RISCV-ReRAM-IMC-SOC)

The most direct expression of the VLSI Design and Technology side of my degree — an exploration of in-memory computing built around ReRAM alongside a RISC-V core, sitting apart from the robotics work but feeding the same underlying interest in how compute actually happens at the hardware level rather than treating the chip as a black box beneath the software.

**Skills demonstrated:** RISC-V core-level architecture · in-memory computing concepts · ReRAM-based memory/compute design · RTL implementation in Verilog

`Verilog` `RISC-V` `In-Memory Computing` `VLSI`

*Status: early stage*

<br/>
<hr/>

## Tech Stack

**Languages** `Python` `C` `C++` `Verilog` `SystemVerilog` `Java` `SQL`

**Robotics** `ROS2` `Forward/Inverse Kinematics` `Trajectory Planning` `Workspace Analysis`

**Computer Vision** `OpenCV` `MediaPipe` `Open3D` `Intel RealSense` `Point-Cloud Processing`

**Control Systems** `Closed-Loop PID` `Encoder-Based Feedback` `Finite State Machines`

**Embedded** `ESP32` `STM32` `8051 (MCS-51)` `Arduino` `Raspberry Pi` `UART` `SPI` `I2C` `PWM`

**Digital Hardware** `RTL Design` `FPGA` `Quartus` `ModelSim` `RISC-V`

**Tools / Backend** `FastAPI` `WebSockets` `SQLite (WAL)` `Fusion 360` `Altium Designer` `MATLAB` `Git`

<br/>
<hr/>

## Where I've Been · Where I'm Going

```
2024   ✓  Embedded robotics
       ✓  Competition robotics (Team Vyadh)
       ✓  Control systems

2025   ✓  Computer vision
       ✓  ROS2
       ✓  Industrial automation (DWS internship)

2026   ●  FPGA accelerators
       ●  RISC-V / VLSI exploration
       ●  Deeper into ROS2 ecosystem

Soon   ○  SLAM
       ○  Robot navigation
       ○  Autonomous manipulation
```

<br/>

<div align="center">

`ashmitsingh7` · open to interesting problems · learning in public

</div>
