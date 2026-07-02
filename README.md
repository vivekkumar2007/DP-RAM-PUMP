# 💧 Low-Cost DIY Hydraulic Ram Pump — CAD Model

> A zero-electricity, water-powered pump designed for sustainable water lifting in mountainous regions.  
> A project of the **Design Practicum course at IIT Mandi**

---

## 📌 Overview

People living in mountainous regions often rely on rivers at lower altitudes for their water supply — making it a daily challenge to carry water uphill. Electrical pumps are costly to install and run. This project presents a **Hydraulic Ram Pump** — a fully mechanical, self-operating pump that uses only the kinetic energy of flowing water to lift a portion of it to a much greater height, with **zero operating cost**.

This repository contains the **SolidWorks CAD model** of the prototype built and tested at IIT Mandi.

---

## ⚙️ How It Works

A Ram Pump exploits the **water hammer effect**:

1. Water flows down the drive pipe, gaining kinetic energy from the supply head.
2. The **waste valve** (open by default due to its own weight) allows water to flow out until the rush of water forces it shut.
3. The sudden valve closure creates a **pressure spike** (water hammer) that travels through the pump body.
4. This spike opens the **check valve** and pushes water into the **air chamber**, where compressed air smoothens the pulsation and forces water steadily up the delivery pipe.
5. Once the pressure drops, the waste valve opens again — and the cycle repeats automatically.

```
Water Source → Drive Pipe → Waste Valve → Check Valve → Air Chamber → Delivery Pipe → Storage
```

---

## 📐 Design Specifications

| Parameter | Value |
|---|---|
| Supply / Drive Head (Hs) | 1.4 m |
| Max Lift Height | 10 m (flow diminishes at max lift) |
| Measured Lift (tested) | ~6 m |
| Drive Pipe | 32 mm (1¼ inch) CPVC SDR11, 25 ft |
| Delivery Pipe | 19 mm (¾ inch) CPVC |
| Pressure Chamber | 110 mm cap, 42 cm length |
| Waste Valve | 1 inch brass waste valve |
| Check Valve | 1.25 inch brass spring check valve |
| Inlet Flow Rate (both pumps) | 0.2 L/s |
| Delivery Flow Rate | 0.0238 L/s |
| Pump Efficiency | ~51% (improvable with larger delivery pipe) |
| Configuration | 2 Ram Pumps in Parallel |
| Material | CPVC pipes, brass valves, steel mesh |
| Prototype Cost | ₹22,000 |

---

## 🧮 Key Equations

**Input Power:**
```
P_in = ρ × g × Q_in × H_s
```

**Head Loss (Darcy-Weisbach):**
```
H_f = f × (L/D) × (V² / 2g)
```

**Water Hammer Pressure (Joukowsky):**
```
ΔP = ρ × c × ΔV
```
Where `c` ≈ 1200 m/s (wave speed in CPVC), giving a hammer pressure of ~2.64 × 10⁶ Pa — far exceeding the delivery pressure of 58,800 Pa needed to lift water 6 m.

**Efficiency:**
```
η = P_out / P_in = (ρ × g × Q_out × H_d) / (ρ × g × Q_in × H_s)
```
Current prototype efficiency: **~51%** (can be improved by increasing delivery pipe diameter to 1 inch)

---

## 🧩 Components List

| Component | Specification |
|---|---|
| Drive Pipe | CPVC SDR11, 32 mm, 25 ft (×2 for parallel pumps) |
| Pressure Chamber | 110 mm CPVC pipe, 42 cm length + 4-inch cap |
| Waste Valve | 1 inch brass waste valve |
| Check Valve (Spring) | 1.25 inch brass spring check valve |
| Delivery Pipe | CPVC, ¾ inch (1 inch recommended for less friction) |
| Inlet Filter | Steel wire mesh on storage tank |
| Storage Tank | With 2 bottom outlets for parallel pump setup |
| Fittings | T-connectors, elbows, union fittings, reducers, tank nipples |
| Sensors (optional) | DN32 Water Flow Sensor, Pressure Transducer |
| Microcontroller (optional) | ESP32 for monitoring |

---

## 🧾 Bill of Materials

| Part | Price (INR) |
|---|---|
| CPVC Ball Valve 1.25 inch / 32 mm | ₹423.74 |
| CPVC No Return Valve 1 inch | ₹480 |
| CPVC Tank Nipple 32 mm | ₹160 |
| CPVC FTA 32 mm | ₹370 |
| CPVC Pipe 32 mm SDR11 (per 3 m) | ₹700 |
| Reducer 1.25 inch – 1 inch | ₹370 |
| Union Fittings 32 mm | ₹160 |
| G.I Nipple 32 mm | ₹20 |
| CPVC Elbow 32 mm | ₹70 |
| CPVC Tee 32 mm | ₹90 |
| Wire Mesh | ₹22/sq |
| CPVC MTA 32 mm | ₹470.01 |
| CPVC Reducer Bush | ₹186 |
| ESP32 (optional) | ₹651 |
| DN32 Water Flow Sensor (optional) | ₹1,299 |
| Pressure Transducer (optional) | ₹922.50 |
| 4-Channel 5V Relay Module (optional) | ₹599 |
| Step-Down Converter 6V–40V to 5V (optional) | ₹299 |

---

## 🗂️ Repository Structure

```
DP-RAM-PUMP/
├── ram pump final/       ← All SolidWorks part & assembly files
│   ├── final assembly.SLDASM
|   ├── final assembly.step
│   ├── bb pipe.SLDPRT
│   └── ...
├── render/               ← Rendered images of the CAD model
├── galvanized.jpg
└── README.md
```

> 📝 Open the `final assembly.SLDASM` assembly file from the `ram pump final/` folder in SolidWorks — keep all files in the same folder so part references resolve correctly.

---

## 🖥️ Software Used

- **CAD Software:** SolidWorks 2021
- **Neutral formats available:** STEP / STL (add if exported)
- All part and assembly files are in a single folder — keep them together so SolidWorks can resolve all references.

---

## 🔧 Build Instructions (Summary)

1. Cut two 25 ft lengths of 32 mm CPVC SDR11 pipe — these are the drive pipes for the two parallel pumps.
2. Prepare a storage tank with two outlets at the bottom and cover the opening with steel mesh for filtration.
3. Install a ball valve on each drive pipe to open/close the pumps independently.
4. At the far end of each drive pipe, connect the **1 inch brass waste valve** using a T-connector.
5. Connect the **1.25 inch brass spring check valve** after the waste valve — this allows flow only into the air chamber.
6. Build the **pressure chamber**: cut a 4-inch CPVC pipe to 42 cm, cap one end, and attach a reducer bush and threaded socket at the other end.
7. Connect both pump outputs via T-connectors into a single delivery channel. Run the delivery pipe to the desired height.
8. For river installation: drill holes in the intake pipe, wrap with mesh, and submerge in the river.

---

## ▶️ Operation Instructions

1. Fill the storage tank (or place the mesh-covered inlet pipe in a flowing river).
2. Open the ball valves on both drive pipes.
3. Once the waste valves cycle shut for the first time, the pump should start self-cycling. If not, manually open and close the waste valve a few times to purge trapped air.
4. Check all joints for leaks. Ensure the drive pipes have no bends.
5. Open the delivery pipe ball valve — water will reach the outlet height within a short time and develop a steady flow.
6. Periodically clean the valves and pipes to prevent sediment build-up.

**Troubleshooting:** If the waste valve is not cycling, ensure the delivery pipe outlet is above the pump height to build sufficient back pressure.

---

## 📊 Performance Comparison

| Parameter | Ram Pump | Electrical Motor |
|---|---|---|
| Initial Cost | ₹4,000 – ₹12,000 | ₹18,000 – ₹60,000 |
| Operating Cost | ₹0 | ₹500 – ₹3,000/month |
| Power Requirement | None (gravity-fed, min. 0.7–2 m head) | Electricity required |
| Maintenance Cost | ₹0 – ₹500 (valve cleaning) | ₹1,000 – ₹6,000 |
| Installation Time | Hours | 1–2 days |
| Skill Required | Very low | Electrician + pump technician |
| Water Wastage | Very low (waste returns to natural stream) | None |

---

## 📚 References

- [Comprehensive Guide to RAM Pumps — Valves Online](https://www.valvesonline.com.au/blog/comprehensive-guide-to-ram-pumps/)
- [Optimizing Hydraulic Ram Pump Performance — Indian Journal of Science & Technology](https://indjst.org/articles/optimizing-hydraulic-ram-pump-performance-experimental-insights-on-waste-valve-height-and-uncertainty-analysis)
- [Effect of Waste Valve Tuning on Hydraulic Ram Pump Efficiency — SciTePress](https://www.scitepress.org/publishedPapers/2021/109430/pdf/index.html)
- [DIY Hydraulic Ram Pump — Instructables](https://www.instructables.com/Hydraulic-Ram-Pump/)
- [Efficiency of a Working Hydraulic Ram Pump System — ISROSET](https://www.isroset.org/pub_paper/WAJES/7-ISROSET-WAJES-04993.pdf)

---

*A Design Practicum project at IIT Mandi — because water should flow uphill too. 💧*
