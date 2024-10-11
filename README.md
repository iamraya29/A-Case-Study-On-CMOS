# A-Case-Study-On-CMOS

A **CMOS inverter** (Complementary Metal-Oxide-Semiconductor inverter) is one of the most fundamental logic gates in digital electronics. It inverts the input logic signal, producing a high output for a low input and vice versa. The CMOS inverter is composed of two types of MOSFET transistors: PMOS (P-type MOS) and NMOS (N-type MOS). These transistors work in a complementary fashion to switch between logic states with minimal power consumption, which is one of the key reasons CMOS technology is so widely used in modern digital circuits.

## 1. Basic Structure of CMOS Inverter
The CMOS inverter consists of a PMOS transistor connected to the supply voltage (VDD) and an NMOS transistor connected to ground (GND). Both transistors share a common gate, which acts as the input signal (`Vin`), and a common output node (`Vout`).

### Operation:
- When the input voltage (`Vin`) is low (logic 0), the PMOS transistor is ON, and the NMOS is OFF. The output is pulled to VDD, representing a logic 1.
- When the input voltage is high (logic 1), the NMOS transistor turns ON, and the PMOS transistor turns OFF. The output is pulled to GND, representing a logic 0.

![image](https://github.com/user-attachments/assets/9d422f84-8a88-4874-bcae-a17b617a3a52)

(Fig. XSchem )
Now this will be converted to symbol 

![image](https://github.com/user-attachments/assets/a5d308a5-aa0c-41f8-a9f1-7ff288b72a6a)

(Fig. XSchem )

## 2. Operation Regions

### Vin = 0V (Low input):
- The PMOS transistor conducts because its gate voltage is lower than its source voltage. 
- The NMOS is turned off, as its gate-source voltage is below its threshold.
- Output is connected to VDD (logic 1).

### Vin = VDD (High input):
- The NMOS conducts because its gate voltage is higher than its threshold. 
- The PMOS transistor is turned off, and the output is pulled down to GND (logic 0).

![image](https://github.com/user-attachments/assets/55a26246-77e1-4233-bba4-5ea9dea47aad)

(Fig. XSchem : Vin vs Vout )


## 3. Electrical Characteristics

- **Threshold Voltage (Vth):** The voltage at which the MOSFET begins to conduct. For a CMOS inverter, the NMOS has a positive threshold voltage, and the PMOS has a negative threshold voltage.
- **Transfer Characteristics (VTC):** The VTC graph shows the relationship between input and output voltages. The VTC graph includes three regions:
    1. **Region 1:** Low input (NMOS off, PMOS on) → Vout = VDD (logic 1).
    2. **Region 2:** Transition region, where both transistors are partially conducting.
    3. **Region 3:** High input (NMOS on, PMOS off) → Vout = GND (logic 0).

## 4. Noise Margins

- **Noise Margin Low (NML):** Difference between the minimum voltage the inverter recognizes as logic 1 (`VIL`) and the maximum output voltage for logic 0 (`VOL`).
- **Noise Margin High (NMH):** Difference between the minimum voltage the inverter recognizes as a logic 1 (`VIH`) and the minimum output voltage for logic 1 (`VOH`).

![image](https://github.com/user-attachments/assets/9dc30ec8-1e9b-4180-a85a-10e52e8d681c)


## 5. Propagation Delay

The propagation delay (`tP`) of a CMOS inverter is the time it takes for the output to respond to changes in the input. It has two components:
- **tPLH (Low-to-High Delay):** Time for the output to rise from logic 0 to logic 1.
- **tPHL (High-to-Low Delay):** Time for the output to fall from logic 1 to logic 0.

![image](https://github.com/user-attachments/assets/098ae697-c011-45fb-b2f0-71cfe279c415)


## 6. Power Consumption
### Static Power Consumption:
- When the input is stable, one transistor is completely off, resulting in minimal power consumption.

## 7. Layout of CMOS Inverter

The layout design involves creating the physical representation of the CMOS inverter using **Magic VLSI** or other layout design tools. The layout includes:

- **PMOS and NMOS transistors** placed in their respective p-well and n-well regions.
- **Metal Layers**: Used for connecting transistors to form the desired circuit (VDD to PMOS, GND to NMOS, common gate, and common output).
- **Design Rule Checks (DRC)**: Ensure that the layout adheres to manufacturing constraints, provided by the **SKY130 PDK**.

  ![image](https://github.com/user-attachments/assets/8cf01fd9-18f1-407f-9bac-aeaef8d446d5)

(Layout made using MAGIC VLSI)

## 8. SKY130 Process Design Kit (PDK)

**SKY130** is a 130nm technology process provided by **SkyWater Technology**, offering an open-source PDK for academic research and chip prototyping.

---

## Summary

The **CMOS inverter** is a critical component in digital circuits due to its low power consumption, high noise immunity, and fast switching speeds. Engineers can optimize CMOS inverters by understanding its electrical characteristics, noise margins, propagation delay, and power consumption. Designing the layout using tools like **Magic VLSI** and following the **SKY130 PDK** guidelines ensures manufacturability and efficiency in silicon fabrication.

