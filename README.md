# Penetration-Testing-an-Embedded-System

# Case Study: Penetration Testing an Embedded Radar System (FOR)

## Overview

This case study applies offensive security techniques to an embedded radar-based system known as the Flying Object Radar (FOR).

The objective was to simulate a black-box adversarial analysis and evaluate:

- Hardware extraction risk
- Firmware reverse engineering feasibility
- GUI exploitation potential
- Network interception vulnerability

---

## System Description

The FOR system is a handheld radar device capable of:

- Detecting airborne objects within a 1-mile radius
- Tracking and classifying birds, drones, and aircraft
- Providing a touchscreen-based GUI for interaction
- Communicating over a local network

The system contains:

- Radar sensor
- Embedded processor
- ROM (non-volatile memory)
- GUI input interface
- Network communication stack

---

## Attack Surface Overview

The reverse engineering effort targeted three primary vectors:

1. Hardware
2. Software (GUI)
3. Network Communications

---

# 1️⃣ Hardware Attack – ROM Extraction

### Objective:
Extract firmware from non-volatile memory.

### Process:

- Disassembled device casing
- Identified ROM chip
- Safely desoldered ROM
- Used ROM programmer to extract binary image
- Began static firmware analysis

### Risk Identified:

If firmware is unencrypted:
- Algorithm exposure
- Key extraction
- Reverse engineering of signal processing logic

---

# 2️⃣ Software Attack – GUI Exploitation

### Attack Types Tested:

- Buffer overflow via long input strings
- SQL injection attempts
- Special character fuzzing
- Script injection attempts

### Observations:

GUI input fields represent:
- Possible memory corruption vectors
- Backend injection risk
- Information disclosure risk

---

# 3️⃣ Network Attack – ARP Poisoning

### Steps Performed:

- Network scanning (Nmap)
- ARP table inspection
- ARP spoofing via Ettercap
- Traffic interception via Wireshark

### Risk Identified:

If traffic is:
- Unencrypted
- Unauthenticated
- Not certificate-pinned

Then:
- Data interception
- Command injection
- Session hijacking

---

# Security Recommendations

- Secure Boot
- Encrypted Firmware
- Encrypted & Authenticated Network Protocols
- Input Validation & Bounds Checking
- Debug Port Lockdown
- Anti-Tamper Mechanisms

---

## Relevance to Mission-Aware Threat Modeling

This case study reinforces the need for:

- Early anti-tamper integration
- CPI partitioning
- Secure update architecture
- Battlefield capture resilience
