# Conway's Game of Life in C

A lightweight, efficient implementation of Conway's Game of Life written in C. This version features a toroidal (wrapping) grid and uses VT100 escape sequences for smooth terminal rendering.

## Features
- **Toroidal Grid**: The world wraps around both horizontally and vertically, meaning cells on the edges interact with those on the opposite side.
- **VT100 Rendering**: Utilizes terminal escape sequences to refresh the screen without flickering.
- **Double Buffering**: Uses two grid states to ensure the "next generation" is calculated based solely on the current state, preventing race conditions during computation.
- **Zero Dependencies**: Requires only standard C libraries (`stdio.h`, `unistd.h`).

## How it Works
The simulation follows the standard B3/S23 rules:
1. **Birth**: A dead cell with exactly 3 live neighbors becomes alive.
2. **Survival**: A live cell with 2 or 3 live neighbors stays alive.
3. **Death**: In all other cases, a cell dies (overpopulation or isolation).

## How to Run
To compile and run the project, use a C compiler (like `gcc`):

```bash
gcc main.c -o game_of_life
./game_of_life
