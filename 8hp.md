---
layout: page
title: "ZF 8HP TCU"
permalink: /8hp/
---

The 8HP is the new auto transmission to swap, providing almost DCT-like shifting while retaining daily-driver refinement. See [8hp.info](https://8hp.info/) for a good overview of 8HP transmissions. The goal of this project is to lower the barrier of entry to 8HP swaps by providing a cheap, open-source alternative to fantastic, but ridiculously expensive 8HP TCUs such as [Turbolamik](https://www.turbolamik.us/tcu-accessories/tcu-turbolamik-full-kit/) or [CanTCU](https://www.canformance.net/product/cantcu-transmission-controller/).

The architecture of the TCU isn't too complex, but as a MechE I'm learning a lot about embedded systems and PCB design as I lock down my scope and learn more technicals. The hardware roughly consists of:
- Logic stage: STM32F4 MCU
- Power stage: gate drivers, low-side MOSFETs, flyback diodes
- Communication: MCP2515 CAN transiever
- Analog input stage w/ RC filters
- 12V-tolerant digital inputs & outputs

While I have rough KiCAD schematics for the hardware, I'm currently focused on learning the STM32 HAL and C++ since that's what I know the least. So far, I've successfully made an LED turn on/off with a button (woo-hoo!). Next step is to control LED dimness with a potentiometer to learn PWM/timers and reading analog inputs.