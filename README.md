# 1084SAdapter
Universal 1084S Monitor Adapter – DIN ↔ DE9 RGB Adapter/Monitor for Amiga, Tandy, and analog/digital RGB 1980's computers

**Philips DIN ↔ Daewoo DE9 Converter and signal debugger/monitor**

This board adapts between different 1084S monitor standards—commonly found in Philips and Daewoo variants—and allows flexible signal routing for Amiga, CGA-based PCs, and other retro systems.

---

## 🌟 Key Features & Use Cases

This board supports multiple configurations on a 1084S monitor (Magnavox, Philips, etc) from the 1980s and early 1990s:

1. **Philips (DIN-based) to Amiga (DE9)**  
   Use this to connect a DIN-based 1084 monitor (typically Philips) to an Amiga that outputs via DE9.

2. **Daewoo (DE9-based) to Amiga (DIN)**  
   Use this to connect a DE9-based 1084 monitor (typically Daewoo) to an Amiga that outputs via DIN.

3. **Cross-compatibility**  
   Adapt any other computer using these connectors, including hybrid setups.

4. **CGA (Tandy 1000) to Philips 1084S (DIN)**  
   Use this board to connect CGA-based PCs to a digital DIN-based monitor like the Philips 1084.

5. **Real-time signal troubleshooting**  
   Connect two boards back-to-back to test sync and RGB lines without format conversion:  
   ```
   Monitor (Analog RGB input) 
     <-> DIN6 male-male cable 
     <-> Adapter Board 
     <-> DE9 male-male cable 
     <-> Adapter Board 
     <-> DIN6 male (Amiga cable/Amiga)
   ```

6. **Signal analysis and custom monitor adapter testing**  
   Use an oscilloscope with this board while designing new adapters or troubleshooting pinouts by experimenting with sync jumper configurations.

---

## ⚠️ Warning

This board gives you *a lot* of flexibility—but with that comes responsibility.  
Incorrect jumper settings, especially for sync signals, can **damage your monitor**. Be **absolutely certain** you understand what you're doing when adjusting jumper settings (J4–J9). You assume all risk for damage caused by improper usage.

---

## 🔧 Default Configuration

Out of the box, the board routes Horizontal and Vertical Sync directly:

- **J4 (HSYNC)**: Enabled → Position **1–2**  
- **J7 (VSYNC)**: Enabled → Position **1–2**

---

## 🧩 Jumper Reference (Sync Routing)

Use these jumpers to customize how sync signals are routed:

| Jumper | Routes From (J1/J2) | To (J3 - DE9)      | Notes               |
|--------|---------------------|---------------------|---------------------|
| **J4** | HSYNC               | HSYNC              | **Default ON** (1–2) |
| **J5** | HSYNC               | VSYNC              | Optional             |
| **J6** | HSYNC               | CSYNC              | Optional             |
| **J7** | VSYNC               | VSYNC              | **Default ON** (1–2) |
| **J8** | VSYNC               | HSYNC              | Optional             |
| **J9** | VSYNC               | CSYNC              | Optional             |

**Note:** Only enable the jumpers that suit your configuration. Never enable conflicting signals unless you're absolutely sure.

### Example (Hypothetical Scenario):
You have a monitor that **only accepts CSYNC**, but your system provides separate HSYNC and VSYNC via DIN.  
You might try:
- Enable **J9**: VSYNC → CSYNC  
- Optionally enable **J6**: HSYNC → CSYNC  
⚠️ This is theoretical; test carefully and monitor your signals.

---

## 🛒 Bill of Materials (BOM)

| Designator | Part Number / Description                                |
|------------|----------------------------------------------------------|
| **J1**     | TE Connectivity 5211511-1 (DIN-8) or equivalent           |
| **J2**     | TE Connectivity 9-211509-0 (DIN-6) or equivalent          |
| **J3**     | DE9 Female, Right Angle, 2.77×2.84 mm pins, 7.48 mm offset |
| **J4–J9**  | 3-pin standard 2.54 mm headers (6 × 3 = 18 pins total)    |
| **TP1–TP8**| Test points (fit standard 2.54 mm header holes)           |

---

## 📌 Connector Pinouts

These are the relevant pinouts for the **Commodore 1084S** monitor. Understanding these is critical for properly wiring and configuring sync routing via jumpers (J4–J9).

---

### 🔌 J1 – Digital RGB Input (DIN-8, typically Philips models)

| Pin | Name   | Description        |
|-----|--------|--------------------|
| 1   | n/c    | Not connected      |
| 2   | R      | Red                |
| 3   | G      | Green              |
| 4   | B      | Blue               |
| 5   | I      | Intensity          |
| 6   | GND    | Ground             |
| 7   | HSYNC  | Horizontal Sync    |
| 8   | VSYNC  | Vertical Sync      |

---

### 🎨 J2 – Analog RGB Input (DIN-6, typically for Amiga or other analog video sources)

| Pin | Name   | Description        |
|-----|--------|--------------------|
| 1   | G      | Green              |
| 2   | HSYNC  | Horizontal Sync    |
| 3   | GND    | Ground             |
| 4   | R      | Red                |
| 5   | B      | Blue               |
| 6   | VSYNC  | Vertical Sync      |

---

### 🖥️ J3 – DE9 Video Connector (Female, at Monitor)

This connector supports **both analog and digital RGB**, combining signals from the DIN connectors internally.

| Pin | Name   | Analog Mode         | Digital Mode        |
|-----|--------|---------------------|----------------------|
| 1   | GND    | Ground              | Ground               |
| 2   | GND    | Ground              | Ground               |
| 3   | R      | Red                 | Red                  |
| 4   | G      | Green               | Green                |
| 5   | B      | Blue                | Blue                 |
| 6   | I      | *Not Connected*     | Intensity            |
| 7   | CSYNC  | Composite Sync      | *Not Connected*      |
| 8   | HSYNC  | *Not Connected*     | Horizontal Sync      |
| 9   | VSYNC  | *Not Connected*     | Vertical Sync        |

📝 **Note:** The 1084S DE9 connector internally combines analog and digital signals from the two DIN connectors. That’s why this board can act as a bidirectional adapter between Philips-style and Daewoo-style 1084S monitors.

---

## 📷 Diagrams & Visuals

Pinout diagrams (DIN-6, DIN-8, and DE9) coming soon!

[View Interactive Diagrams Here (Link Placeholder)](https://your-diagram-link-here)

---
