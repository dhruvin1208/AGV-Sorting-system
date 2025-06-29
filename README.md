🚦 AGV Sorting System – TIA Portal + WinCC Comfort

This project simulates a fully functional **Automated Warehouse Sorting System** with **AGV (Automated Guided Vehicle)** integration using **Siemens TIA Portal V19** and **WinCC Comfort**.

It includes realistic process logic for sorting products, handling emergency alarms, and displaying data on an HMI screen — just like a real industrial installation.

---


---

## 🧠 Features

| Feature            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `FB_Sorter`        | Sorts products by type (1=A, 2=B, 3=C) and activates diverter gates         |
| `FB_AGV`           | Simulates AGV moving between zones with load/unload cycle                  |
| `FB_AlarmHandler`  | Monitors Emergency Stop, latches faults, halts system                      |
| `OB1`              | Central logic with halt handling and inter-FB coordination                 |
| HMI                | Real-time interaction for simulation, control, and monitoring              |

---

## ⚙️ Technology Stack

- **Siemens TIA Portal V19**
- **Structured Control Language (SCL)**
- **LAD for basic elements**
- **WinCC Comfort for HMI design**
- **PLCSIM Advanced (S7-1500 Simulation)**

---

## 📺 WinCC Comfort Screens

### 🖥️ Main Overview Screen
- Start system simulation (`M0.0`)
- Set product type (`MW10`)
- View diverter and conveyor status
- Display AGV position and sort completion

### 🛻 AGV Transport View
- AGV position flags (`MW20`, `M1.1–1.3`)
- Load/Unload LED indicators
- Target zone display (`MW30`)

### 🚨 Alarm & Safety Screen
- E-Stop button (`M2.1`)
- Reset Fault button (`M2.2`)
- AlarmActive and SystemHalt indicators (`M100.0`, `M100.1`)

### 📊 Statistics View
- Count products sorted per zone
- Count rejected/misrouted items
- (Optional future) Reset counters

---

## 🔌 Address Mapping Summary

| Symbol           | Description                      |
|------------------|----------------------------------|
| `M0.0`           | Product detected sensor          |
| `MW10`           | Product type (1, 2, 3)           |
| `M0.2–M0.4`      | Diverter outputs A, B, C         |
| `M0.5`           | Sort complete flag               |
| `M3.0`           | AGV start trigger (internal)     |
| `MW20`           | AGV current position             |
| `MW30`           | AGV target zone buffer           |
| `M1.4–1.5`       | Load/Unload actions              |
| `M2.1`           | Emergency Stop input             |
| `M2.2`           | Fault Reset input                |
| `M100.0`         | SystemHalt output                |
| `M100.1`         | AlarmActive flag                 |

---

## 🧪 How to Simulate

1. Open project in **TIA Portal V19**
2. Start **PLCSIM Advanced**, load S7-1500 virtual PLC
3. Open WinCC Comfort panel or run simulation
4. Use HMI to:
   - Start product detection (`M0.0`)
   - Select product type (`MW10`)
   - Trigger AGV logic automatically
   - Simulate E-Stop (`M2.1`) and reset (`M2.2`)
   - Observe HMI feedback

---

## 🛡️ EN 60204-1 Safety Design

This project follows a basic model of **EN 60204-1** electrical safety:

- Latching Emergency Stop logic
- Reset required before system resumes
- `SystemHalt` output blocks OB1 logic execution
- All alarms can be visualized via HMI panel

---

## 💡 Expand Ideas

- Add `FB_CounterHandler` to track long-term data
- Add RFID scan simulation for advanced product routing
- Implement actual I/O from real PLC for field testing
- Use **WinCC Alarm Control** for better diagnostics
- Add SQL or CSV export from WinCC Runtime

---

## 👨‍💻 Author

**Dhruvin Antala**  
SPS/Automation Engineer  
📍 Germany  
🔧 Focus: TIA Portal, SCL, EPLAN, Industrial Systems

---

## 📃 License

This project is released under the **MIT License**. 
