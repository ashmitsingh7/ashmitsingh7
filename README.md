<div align="center">

# Ashmit Singh

**Robotics & Embedded Systems** · Electronics Engineering @ VIT Vellore

[![LinkedIn](https://img.shields.io/badge/LinkedIn-ashmitsingh7-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ashmitsingh7)
[![Gmail](https://img.shields.io/badge/Email-ashmitsingh719%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:ashmitsingh719@gmail.com)
[![GitHub followers](https://img.shields.io/github/followers/ashmitsingh7?style=flat-square&label=Follow&color=181717&logo=github)](https://github.com/ashmitsingh7)

</div>

<br/>

## About

I build robots and the embedded/software stacks underneath them — sensors, firmware, control loops, perception, and the plumbing that connects them. Currently an Electronics Engineering undergrad at VIT Vellore, spending most of my time in **robotics, embedded systems, and computer vision.**

I care more about complete, working systems than isolated demos. If something breaks in the field, I'd rather understand *why* than just patch around it.

<br/>

## Currently Building

**Industrial Dimensioning, Weighing & Scanning (DWS) System** — *Internship @ Delhivery*
A production warehouse perception pipeline that scans a parcel, captures its depth image, measures dimensions, reads the barcode, and logs the weight — no human input required. Multi-sensor capture stack (Intel RealSense D455, digital scale, barcode scanner) feeding a classical CV measurement pipeline, orchestrated by a finite-state machine, with a local-first data layer and live dashboard.

`ROS2-style architecture` `RealSense D455` `RANSAC / PCA` `FastAPI` `SQLite (WAL)` `WebSocket HMI`

> Codebase is private under company confidentiality — architecture and role are described here, code isn't shared.

<br/>

## Projects

| | | |
|---|---|---|
| **[Team Vyadh — Mars Rover Manipulator](https://github.com/ashmitsingh7/Team-Vyadh-Robotic-Arm)** | 5-DOF robotic arm for the International Rover Challenge. Owned embedded control — encoder feedback, closed-loop PID, power distribution — contributing to a 17th-place international finish (IRC 2026). | `C++` `ESP32` `Encoder feedback` `PID` |
| **[Gesture-Controlled Robotic Arm](https://github.com/ashmitsingh7/robotic-arm-vision-control)** | Full perception-to-actuation chain: webcam → MediaPipe hand pose → gesture classification → TCP → ESP32 → servos. Built to understand where latency actually accumulates across a real-time control pipeline. | `Python` `OpenCV` `MediaPipe` `ESP32` |
| **[PID Hardware Accelerator](https://github.com/ashmitsingh7/PID_Hardware_Accelerator)** | RTL implementation of a PID controller in Verilog — fixed-point arithmetic, pipelined stages — exploring whether hardware can genuinely beat software on latency. Work in progress. | `Verilog` `FPGA` `RTL` `ModelSim` |

**Also exploring:** a small RISC-V / ReRAM in-memory-compute SoC project on the hardware side — early stage, more on that as it matures.

<br/>

## Tech Stack

**Languages**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=white)
![Verilog](https://img.shields.io/badge/Verilog-black?style=flat-square)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**Robotics & Control**
![ROS2](https://img.shields.io/badge/ROS2-22314E?style=flat-square&logo=ros&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat-square&logo=espressif&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=flat-square&logo=raspberrypi&logoColor=white)

**Computer Vision**
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![Intel RealSense](https://img.shields.io/badge/Intel%20RealSense-0071C5?style=flat-square&logo=intel&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white)

**Backend & Tools**
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**Hardware / VLSI** *(secondary focus)*
![Verilog](https://img.shields.io/badge/RTL%20Design-black?style=flat-square)
![Quartus](https://img.shields.io/badge/Quartus-6699CC?style=flat-square)
![Altium](https://img.shields.io/badge/Altium%20Designer-A5CD50?style=flat-square)

<br/>

## GitHub Stats

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=ashmitsingh7&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ashmitsingh7&layout=compact&theme=tokyonight&hide_border=true" />

<img src="https://github-readme-streak-stats.herokuapp.com/?user=ashmitsingh7&theme=tokyonight&hide_border=true" />

</div>

<br/>

## How I Think About Building

```
01  Build systems, not features — the interesting problems live at the interfaces.
02  Hardware failure teaches you things software testing never will.
03  Understand it before you automate it.
04  Documentation is part of the build, not an afterthought.
```

<br/>

<div align="center">

`ashmitsingh7` · open to interesting problems · learning in public

</div>
