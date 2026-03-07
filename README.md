**MINT-V2X (Mobility-Integrated Network Trajectory Dataset for V2X Systems)** is a large-scale dataset designed for research on **vehicle-to-everything (V2X) communication, mobility-aware networking, and intelligent transportation systems (ITS)**.

The dataset integrates **vehicle trajectory dynamics with wireless network measurements**, enabling predictive modeling of **vehicle mobility, network quality, and RSU resource demand**.

Unlike existing datasets that provide either **vehicle trajectories** or **network statistics** independently, **MINT-V2X provides synchronized mobility and communication data**, allowing researchers to study interactions between **vehicle movement, wireless channel quality, and network load**.

---

# Dataset Overview

MINT-V2X contains nearly **10 million synchronized records** generated from a realistic **urban V2X simulation environment**.

| Property | Value |
|--------|------|
| Vehicles | 1,386 |
| Total records | 9,873,977 |
| Simulation duration | 3 hours |
| Sampling rate | 10 Hz (100 ms) |
| Features per record | 29 |
| Spatial coverage | 61.19 km² |
| RSU deployment | 15 roadside units (5×3 grid) |

Each record corresponds to a **vehicle–timestep observation**, capturing both **vehicle mobility state and wireless network conditions**.

---

# Dataset Features

Each data sample includes **29 features** spanning four main categories.

## 1. Vehicle Trajectory
- Position `(x, y, z)`
- Velocity
- Acceleration
- Heading angle
- Lane identifier

## 2. Network State
- RSU association (cell ID)
- Distance to RSU
- Neighbor vehicle count
- Signal-to-Interference-plus-Noise Ratio (SINR)
- Received signal power

## 3. Physical Layer Metrics
- Channel Quality Indicator (CQI)
- Modulation and Coding Scheme (MCS)
- Packet Delivery Ratio (PDR)
- Channel Busy Ratio (CBR)

## 4. Communication Performance
- Throughput
- End-to-end latency
- Handover events

These features enable **joint modeling of vehicle mobility and wireless network performance**.

---

# Dataset Generation Pipeline

The dataset is generated through a **three-layer co-simulation architecture**.

### Traffic Simulation — SUMO
Generates realistic vehicle trajectories using urban traffic models.

### Middleware — Veins
Synchronizes traffic and communication simulators via the TraCI interface.

### Network Simulation — OMNeT++ / Simu5G
Computes wireless metrics such as:

- SINR
- CQI
- PDR
- Throughput
- Latency

All data is recorded at **10 Hz temporal resolution**, ensuring precise synchronization between mobility and network states.

---

# Validation Framework

The dataset was validated using a **14-point validation framework** referencing:

- **3GPP C-V2X standards**
- **ETSI congestion control specifications**
- **Shannon information theory**

Key validations include:

- SINR range: **−5 dB to +25 dB**
- CQI–SINR correlation: **0.993**
- SINR–PDR correlation: **0.946**
- Connectivity ratio: **99.78%**

These tests confirm that the simulated network metrics follow **physically consistent wireless communication behavior**.

---

# Research Applications

MINT-V2X supports research in several areas of **vehicular networking and intelligent transportation systems**, including:

- Vehicle trajectory prediction
- Mobility-aware network traffic prediction
- RSU load forecasting
- Handover optimization
- Proactive resource allocation
- Multi-agent V2X communication modeling
- Mobility-communication co-learning models

The dataset particularly enables **mobility-aware RSU resource prediction**, where future network demand is estimated from predicted vehicle trajectories.

---

# Dataset Structure (Example)
