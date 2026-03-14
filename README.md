# Team CTRL Freaks - PSAT PSU PCB

## Overview
This repository contains the design for the Power Supply Unit (PSU) PCB developed by Team CTRL Freaks to power the MCU PCB, Beacon PCB, and the plume mechanism in the PSAT mission.

The PSU PCB provides a robust and configurable power source, capable of switching between buck (step-down) and boost (step-up) conversion modes to deliver the precise voltages and high currents required by the payload.

## Features
- **Regulated 3V3 Output** using **AP3445/L** for MCU, sensors, and Beacon
- **Efficient Conversion Components** rated for **High-Current Capability**: up to **5V @ 10A**
  - Boost: **TPS61088**  
  - Buck: **TPS56A37RPAR**

## Technical Overview

| Function               | Component      | Notes                            |
|------------------------|----------------|----------------------------------|
| 3.3 V regulated output | AP3445/L       | LDO for MCU/sensor logic         |
| Boost converter        | TPS61088       | High-efficiency step-up to 5V    |
| Buck converter         | TPS56A37RPAR   | High-efficiency step-down for 5V |
| Output power (Coil)    | 5V / 10A       | High current for plume mechanism |


## Usage

1. Solder 3V3 Regulator and it's external circuitry required for general MCU/beacon PCB power use.
2. If using the BOOST convertor, solder all components labelled "Boost", and connect 1x JST 3.7V battery to J2.
3. If using the BUCK convertor, solder all components labelled "Buck", and connect 2x JST 3.7V battery in series to J2 and J3.
4. Power the Coil directly using a 3.7V battery to JST J4 header.
5. Verify output voltage and current before connecting the Nichrome wire for plume mechanism.
6. In firmware, enable the BOOST convertor or BUCK convertor by holding a Logic HIGH (3V3) on PINS P3.2 and P3.1 respectively