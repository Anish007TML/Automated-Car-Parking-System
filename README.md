# Automated-Parking-System
This project simulates a real-time automated parking system using basic digital ICs. It is designed to manage vehicle entries and exits, keep track of the number of vehicles in a parking lot, record the time of entry using memory modules, and calculate the parking fee based on the time spent. The implementation uses decade counters, binary adders, up/down counters, memory modules, comparators, and logic gates. The entire system is hardware-based and simulated using Multisim.

## Complete Overview

<img width="1590" height="1308" alt="image" src="https://github.com/user-attachments/assets/9d876910-0274-446d-b898-69030af7df45" />


## Components Used

| Component                    | Description                                      |
|------------------------------|--------------------------------------------------|
| 74LS90N                      | Decade counter for master clock                  |
| 74LS83N                      | 4-bit binary adder used in the fee calculator    |
| 2K8RAM                       | Memory element that stores vehicle entry time    |
| 4510BD_10V                   | BCD Up/Down counter to track vehicle count       |
| 74LS85N                      | 4-bit magnitude comparator for vacancy check     |
| 7-Segment Displays           | Displays time, car count, and fee                |
| AND, OR, NOT, NOR Gates      | Basic logic functions                            |
| SPDT Switches                | Input for car numbers and operations             |
| Digital Clock (10Hz)         | Drives the master clock                          |
| Voltage Sources              | VCC (5V) and GND for logic levels                |
| Connecting Wires             | For circuit interconnections                     |

## Subsystem Modules

### 1. **Master Clock**
- Uses two decade counters to generate time from 00 to 99.
- Drives entry time recording and fee calculation.

### 2. **Memory Element (2K8RAM)**
- 12-bit address from car number.
- Stores entry time on car arrival.
- Retrieves entry time on car exit.

### 3. **Car Counter**
- BCD Up/Down counter tracks the number of vehicles.
- Comparator ensures cars can only enter if space is available.

### 4. **Parking Fee Calculator**
- Uses binary adders as BCD subtractors.
- Calculates fee as difference between current and stored time.

##  Methodology

1. **Car Enters**:
   - Entry time stored in RAM.
   - Car count is incremented.
   - Gate opens only if space is available.

2. **Car Leaves**:
   - Entry time fetched from RAM.
   - Duration calculated and used to compute fee.
   - Car count is decremented.

##  Conclusion

This project shows how digital logic can be used to build a simple and effective automated parking system. It handles car entry, exit, time tracking, and fee calculation using Multisim. While there are a few limitations, like handling one car at a time and a limited clock range, the system works well for small to medium parking areas. With some improvements, it could easily be scaled up for real-world use.
