# A_star# A* Pathfinding with LED Matrix & LCD Display

This project implements the **A* algorithm** to find the shortest path between locations in **Imphal**, visualizing the path on an **LED matrix** and displaying the total cost on an **LCD screen** using **Arduino**.

## 🛠️ Setup Instructions

### 1️⃣ **Upload Arduino Code**
- Upload `LED_matrix.ino` to the Arduino controlling the **LED matrix**.
- Upload `LCD_display.ino` to the second Arduino controlling the **LCD display**.

### 2️⃣ **Compile and Run C++ Program**
Compile the C++ program using **MinGW** or any compatible compiler:
```bash
g++ astar.cpp -o astar.exe
Run the executable:
astar.exe
This executes the A algorithm* and sends data to Arduino via COM7 (LEDs) and COM8 (LCD).

## Features

- **A* Algorithm Implementation:** Efficient pathfinding using the A* algorithm with real-time latitude and longitude for heuristic calculation.
- **Dual Arduino Setup:** Two Arduino boards communicate via serial ports, one controlling the LED matrix (COM7) and the other controlling the LCD (COM8).
- **LED Path Visualization:** LEDs light up sequentially along the path found by the A* algorithm, with a delay between each LED for visual effect.
- **LCD Cost Display:** The total cost of the path is shown on a 16x2 LCD display.
- **Real-Time Heuristic Calculation:** Straight-line distances between nodes (locations in Imphal) are calculated using actual geographical coordinates.

---

## Hardware Components

- **Arduino Uno (x2):** One for controlling the LED matrix and another for controlling the LCD.
- **LED Matrix:** Displays the nodes in the city and lights up to show the shortest path.
- **16x2 LCD Display:** Shows the total cost of the shortest path.
- **Shift Register:** Used to control the LED matrix with fewer GPIO pins.
- **Connecting Wires, Breadboard, Power Supply.**

---

## Software Components

- **C++ Program:** Implements the A* algorithm and communicates with the Arduino boards over serial communication (COM7 and COM8).
- **Arduino Code (x2):**
  - **COM7:** Controls the LED matrix based on the path data received from C++.
  - **COM8:** Displays the path cost on the LCD.

- **Libraries:**
  - Arduino `LiquidCrystal` library for LCD control.
  - Custom C++ code for serial communication using the Win32 API.

---

## System Design

The project follows a modular design to separate software and hardware components:

1. **A* Algorithm:**
   - Computes the shortest path between 20 key locations in Imphal, Manipur.
   - Uses real-time latitude and longitude to calculate heuristic values (`h(n)`).
   
2. **Serial Communication:**
   - C++ sends path data to Arduino via COM7 for LED matrix control.
   - Simultaneously, the path cost is sent to Arduino via COM8 for LCD display.

3. **LED Matrix:**
   - Controlled via a shift register connected to Arduino.
   - Lights up sequentially to show the nodes in the path.

4. **LCD Display:**
   - Displays the total path cost calculated by the A* algorithm.

---


###3️⃣ **Circuit Configuration**
Connect the LED matrix to the first Arduino using a shift register.
Connect the LCD display to the second Arduino.
Ensure the wiring follows the pin mappings in LED_matrix.ino and LCD_display.ino.
🚀 How It Works
The user selects a start and destination node (out of 20 locations).
The A algorithm* computes the shortest path.
The LED matrix lights up LEDs sequentially to visualize the path.
The LCD displays the total path cost (g(n) + h(n)).
###🔄 System Architecture
1️⃣ A Algorithm* – Computes the optimal path using heuristics and costs.
2️⃣ Serial Communication – Sends path data to COM7 (LED matrix) and COM8 (LCD).
3️⃣ LED Matrix Visualization – Lights up LEDs one by one to indicate the shortest path.
4️⃣ LCD Display – Shows the total path cost dynamically.
5️⃣ Microcontroller (Arduino) – Controls LED and LCD modules.
6️⃣ Shift Register – Manages LED matrix efficiently using fewer pins.

###🔧 Troubleshooting
❌ Incorrect LED Sequence?
Check the Arduino connections and ensure COM7 is active.
Verify if the A algorithm output* is correctly formatted.
❌ No LCD Output?
Ensure Arduino COM8 is properly connected.
Check the baud rate in both C++ and Arduino code.
❌ No Path Data Displayed?
Check serial communication settings in astar.cpp.
Ensure the Win32 API is correctly configured for COM7 & COM8.
❌ COM Port Issues?
Ensure both Arduino boards are detected by your system.
Use Arduino Serial Monitor to check COM7 and COM8 output.
###🚀 Future Improvements
Expand the Graph → Add more locations for better coverage.
Real-Time GPS Integration → Improve navigation accuracy dynamically.
Optimize Data Transfer → Improve speed & visualization effects.
Smart City Integration → Use for real-time traffic & route planning.
🛠 Built with:

Arduino ATmega 2560
C++ (MinGW Compiler)
LED Matrix & Shift Register
16x2 LCD Display
