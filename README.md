🎲 Dice Rolling Game (Python)

This project implements a dice rolling game using Python.
The program finds the minimum cost path from a source cell to a destination cell on a grid, where the cost depends on the top face of a rolling dice.

📌 Description

A dice is placed on a grid.

The dice can move up, down, left, or right.

Each move rolls the dice and changes its orientation.

The cost of each move is the number on the top face of the dice after rolling.

The goal is to reach the destination with the minimum total cost.

🧠 Algorithm (Simple)

Read input values (grid structure, source, destination, dice faces)

Build the grid using given directions

Track dice orientation while moving

Use Dijkstra’s Algorithm to:

Explore all possible paths

Always choose the path with the lowest cost

Stop when the destination is reached

Print the minimum cost

🔄 Dice Rotation Logic

Opposite faces of a dice always add up to 7

Dice orientation changes based on movement direction:

Up

Down

Left

Right

🧪 Input Includes

Number of placements

Directional connections between cells

Source and destination

Initial dice orientation (top, left, front)

📤 Output

Minimum cost to reach the destination

Prints -1 if the destination is unreachable

🚀 Concepts Used

Dice simulation

Grid traversal

Priority Queue (heapq)

Dijkstra’s shortest path algorithm

🎯 Use Cases

Game simulations

Pathfinding problems

Learning Dijkstra’s algorithm

Understanding dice rotation logic
