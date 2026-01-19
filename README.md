# 🎲 Dice Rolling Path Finder

This project simulates rolling a dice across a connected grid and calculates the **minimum cost** required to move the dice from a starting block to a destination block. The cost depends on the **top face value of the dice after each move**.

The solution uses **Dijkstra’s algorithm** to find the most efficient path while tracking the dice’s orientation at every step.

---

## 📌 Problem Overview

* Each block is connected to another block in one of four directions: `up`, `down`, `left`, or `right`.
* A dice is placed on the starting block with a given orientation.
* Every time the dice rolls, its faces change based on the direction of movement.
* The cost of moving to a new block is equal to the **top face value** of the dice after the roll.
* The goal is to reach the destination block with the **minimum total cost**.

---

## ⚙️ How It Works

### 1. Dice Rotation

The dice orientation is updated whenever it rolls in a direction. The logic ensures correct face changes using opposite face rules (sum of opposite faces = 7).

### 2. Grid Construction

The blocks and their relative positions are built into a 2D grid based on the input connections.

### 3. Shortest Path Search

Dijkstra’s algorithm is used to:

* Explore all valid paths
* Track dice orientation at each position
* Always choose the path with the lowest cost so far

---

## 🧠 Algorithm Used

* **Dijkstra’s Algorithm**
* **Priority Queue (Heap)**
* **State Tracking** (position + dice orientation)

This guarantees the shortest path while handling changing dice values.

---

## 📥 Input Format

1. Number of connections `n`
2. `n` lines of connections:

   ```
   a b direction
   ```
3. Source block and destination block:

   ```
   src dst
   ```
4. Initial dice orientation:

   ```
   top left front
   ```

---

## 📤 Output

* A single integer representing the **minimum cost** to reach the destination.
* Returns `-1` if the destination cannot be reached.

---

## ▶️ How to Run

```bash
python dice_rolling_game.py
```

Then provide input as described above.

---

## 📂 Example Use Case

This project is useful for:

* Algorithm practice (graphs and pathfinding)
* Understanding state-based search problems
* Simulating real-world rolling mechanics in games or puzzles

---

## 🚀 Future Improvements

* Add visualization of dice movement
* Support larger grids
* Convert to a GUI-based simulation

---

Created as a **Python mini project** to practice algorithms, data structures, and logical problem-solving.

Feel free to fork, improve, and share! 😊

