![Uploading Screenshot 2026-10-16 at 11.24.50 PM.png…]()
![Uploading Screenshot 2026-10-16 at 11.24.49 PM.png…]()
<img width="1296" height="823" alt="Screenshot 2026-10-18 at 11 32 48 AM" src="https://github.com/user-attachments/assets/d001bb95-af95-4127-b3b5-ccf4337f02bd" />
[Uploading Screenshot 2026-10-18 at 11.32.48 AM.png…]()
# 🤖 Self-Balancing Robot Chassis (CAD v1.0)

A compact, monocoque chassis for a two-wheeled inverted pendulum (self-balancing) robot. Designed from scratch in **Autodesk Fusion 360**, this enclosure integrates an open-access electronics bay, recessed acrylic display window, low-slung battery compartment, panel-mount power ports, and precision motor brackets.

## 📌 Project Overview

Self-balancing robots rely heavily on dynamic mass distribution and a low center of gravity ($CoG$) to maintain equilibrium via PID or LQR control loops.

This chassis was engineered to solve common prototyping challenges:

* **Compartmentalization:** Separates high-current power components (battery, motors) from sensitive electronics (IMU, MCU, drivers).
* **Serviceability:** Features a recessed front faceplate opening for viewing telemetry/status LEDs and easy wire access.
* **Clean Cable Management:** Dedicated internal routing from the lower battery bay to the rear switch and DC barrel jack.
* **FDM Printability:** Utilizes bottom chamfers and angled transitions to minimize support material requirements.

## 🛠️ Step-by-Step Design Progression

The entire CAD workflow follows an iterative design-for-manufacturing (DFM) approach:

```
[ Concept Sketch ] ➔ [ Base 2D Sketch ] ➔ [ Solid Extrude ] ➔ [ Fillets & Chamfers ]
                                                                       │
[ Motor Mounts & Export ] ⬅ [ Power & Port Cutouts ] ⬅ [ Shell & Battery Bay ] ⬅
```

1. **Step 1: Rough Paper Ideation**
   * Mapped out geometric footprint, motor stance width, center of gravity balance line, and component clearances on paper.

2. **Step 2: Base 2D Parametric Sketch**
   * Transferred conceptual dimensions into Fusion 360 using fully constrained parametric sketches and symmetry reference axes.

3. **Step 3: Extrusion, Edge Filleting & Faceplate Recess**
   * Extruded the main body silhouette. Applied rounded edge fillets to eliminate stress concentration points and improve impact durability during balance tuning.
   * Sketched and cut a recessed flange on the front face to seat a clear acrylic/glass protection window.

4. **Step 4: Electronics Cavity Cutout & Body Shelling**
   * Extruded the front cavity inward to create the control board bay.
   * Applied the **Shell** feature to hollow out the chassis with uniform wall thickness, opening up a dedicated lower compartment for heavy LiPo/Li-ion battery cells.

5. **Step 5: Power Interface Integration**
   * Modeled precision cutouts for:
     * 3D Rocker/Toggle master power switch
     * Female DC barrel jack for charging/bench testing
     * Battery charger access port

6. **Step 6: Motor Mounts & Final CAD Lock**
   * Cut lower motor axle pass-throughs and concentric bolt mounting holes.
   * Verified mechanical clearances and finalized version 1.0.

## 📐 Chassis Specifications

| Parameter | Specification |
| :--- | :--- |
| **CAD Software** | Autodesk Fusion 360 |
| **Model Type** | Monocoque Unibody Enclosure |
| **Primary Material** | PLA / PETG / ABS |
| **Electronics Bay** | Front recessed chamber with acrylic faceplate rim |
| **Power Compartment** | Lower internal bay (optimized for low center of gravity) |
| **Port Provisions** | DC barrel jack, Rocker switch, Onboard charger cutout |
| **Drive System** | Dual DC geared / stepper motors with bottom chassis mount |
| **File Formats Provided** | `.f3d` (Parametric source), `.step`, `.stl` |

## 🖨️ 3D Printing & Manufacturing Guidelines

For best structural strength and layer adhesion during dynamic robot movement:

* **Material:** PETG or PLA+ recommended for drop resistance; ABS/ASA for outdoor use.
* **Infill:** $20\% - 30\%$ (Gyroid or Grid recommended for torsional stiffness).
* **Perimeters / Wall Loops:** $3 - 4$ minimum to ensure solid tap threads and durable switch detents.
* **Supports:** Required only for steep overhangs and horizontal port openings; chamfered base prints cleanly directly on the build plate.
* **Orientation:** Print standing upright on its bottom face for maximum vertical strength.




## 🛒 Bill of Materials (BOM) & Buying Links

| Part / Material | Specification | Quantity | Unit Price (USD) | Buying Link |
| :--- | :--- | :---: | :---: | :--- |
| **MPU-6050 Module** | 6-DOF Gyroscope + Accelerometer (GY-521) | 1 | $1.40 | [AliExpress / Amazon](https://www.aliexpress.com/item/32344795748.html) |
| **Dual Geared BO Motor + Wheel** | Yellow TT motor (3–6V, ~1:48 ratio) + 65mm wheel | 2 | $1.20 | [AliExpress / Amazon](https://www.aliexpress.com/item/32832865766.html) |
| **18650 Li-ion Battery** | 3.7V 2000–2600mAh rechargeable cell | 2 | $3.50 | [18650 Battery Store](https://www.18650batterystore.com/) |
| **DC Power Jack (Female)** | 5.5mm × 2.1mm panel-mount barrel jack | 1 | $0.35 | [LCSC Electronics](https://www.lcsc.com/) |
| **Mini SPST Switch** | 2-pin latching rocker / toggle switch (KCD11) | 1 | $0.25 | [LCSC Electronics](https://www.lcsc.com/) |
| **22 AWG Flexible Silicone Wire** | Red & Black stranded hookup wire (1m) | 1 | $0.80 | [Amazon](https://www.amazon.com/dp/B07G724S5Q) |
| **L298N Mini Motor Driver** | Dual H-bridge DC motor driver (MX1508) | 1 | $0.90 | [AliExpress](https://www.aliexpress.com/item/32828691507.html) |
| **Arduino Nano / Microcontroller** | ATmega328P CH340 board (5V / 16MHz) | 1 | $2.80 | [AliExpress](https://www.aliexpress.com/item/32868739265.html) |


## 🚀 Getting Started

1. **Clone this repository:**
   ```bash
   git clone https://github.com/<your-username>/self-balancing-robot-cad.git
   ```

2. **Open in Fusion 360:**
   * Launch Autodesk Fusion 360.
   * Click `File` > `Open...` and select `cad/self_balancing_robot_v1.f3d`.

3. **Slice & Print:**
   * Import `cad/stl/chassis_main_body.stl` into your slicer of choice (Bambu Studio, PrusaSlicer, Cura, OrcaSlicer).
   * Apply recommended print parameters and slice.

## 📄 License

This project is open-source hardware licensed under the [MIT License](LICENSE).
