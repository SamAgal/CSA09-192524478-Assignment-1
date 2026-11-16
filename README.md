# CSA09 — Java Programming: Assignment 1 (CO1)

- **Student Name:** J. Sam Agal
- **Register Number:** 192524478
- **Course:** CSA09 — Java Programming (SIMATS School of Engineering)
- **Java Environment:** OpenJDK 21.0.5 (64-Bit Server VM) on Arch Linux x86_64
- **GitHub Repository:** https://github.com/SamAgal/CSA09-192524478-Assignment-1

---

## Repository Structure

```text
CSA09-192524478-Assignment-1/
├── README.md
├── Task01/ (DomainModelCheck.java, sample_input.txt, task01_output.png)
├── Task02/ (DataRepresentationDemo.java, task02_output.png)
├── Task03/ (ParkingFacility.java, task03_output.png)
├── Task04/ (TicketConstructorDemo.java, task04_output.png)
├── Task05/ (StaticLifecycleDemo.java, task05_output.png)
├── Task06/ (ConstructorTraceDemo.java, task06_uml_diagram.png, task06_output.png)
├── Task07/ (FeeDemo.java, task07_output.png)
├── Task08/ (FeeDemo.java, task08_output.png)
├── Task09/ (FeeDemo.java, task09_output.png)
├── Task10/ (CampusParkingSystem.java, task10_output.png)
├── Task11/ (CampusParkingSystem.java, task11_output.png)
└── Task12/ (ExtensibleParkingRedesign.java, task12_output.png)
```

---

## Compilation & Execution Steps

```bash
# Task 03: Complete the Code — ParkingFacility
cd Task03 && javac ParkingFacility.java && java ParkingFacility

# Task 08: Complete the Code — FeeDemo (Polymorphism & Overriding)
cd Task08 && javac FeeDemo.java && java FeeDemo

# Task 11: Full Campus Smart-Parking System & Boundary Verification
cd Task11 && javac CampusParkingSystem.java && java CampusParkingSystem

# Task 12: Day-4 Design Challenge (Strategy PricingRule & One-Day Pass Redesign)
cd Task12 && javac ExtensibleParkingRedesign.java && java ExtensibleParkingRedesign
```

---

## Summary of Task Results

1. **Task 01–02:** Modeled `Vehicle`, `ParkingSlot`, `ParkingFloor`, `ParkingFacility`, `ParkingTicket`, and `CampusUser` using a jagged `String[][]` floor-slot representation and overflow-safe ceiling arithmetic `(minutes + 59) / 60` to avoid integer division fee truncation.
2. **Task 03 (`ParkingFacility`):** Implemented `allocate()` and `release()` with boundary validation. Verified exact output: `[0, 0]`, `[0, 1]`, `[1, 0]`, `null`, `true false false`, `[0, 1]`.
3. **Task 04–05:** Implemented constructor chaining via `this(...)`, copy constructors for duplicate ticket receipts, and `static` sequence/occupancy counters shared across North and South campus gates.
4. **Task 06–09 (`FeeDemo`):** Designed `Vehicle` abstract base class, `Chargeable` interface, and `TwoWheeler`, `Car`, and `ElectricCar` subclasses. Verified dynamic dispatch output: `TwoWheeler TN01A1 -> Rs 30.0`, `Car TN02B2 -> Rs 90.0`, `ElectricCar TN03C3 -> Rs 210.0`, and `true` for registration equality.
5. **Task 10–11:** Built encapsulated `CampusParkingSystem` and verified normal, boundary (last slot, zero-minute stay, exact 60-minute slab), and invalid cases, matching hand-calculated daily collection of `Rs 240.00`.
6. **Task 12 (Day-4 Design Challenge):** Refactored rigid subclass pricing into a composable `PricingRule` strategy interface and `ParkingPass` abstraction on a 5-floor jagged array (100 slots), adding `E_BIKE` (flat Rs 15), `DELIVERY_VAN` (peak 09:00–17:00 double rate Rs 60/hr), and `OneDayVisitorPass` with zero modifications to `Vehicle`.
