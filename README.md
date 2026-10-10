# Snake Game in x86 Assembly

A classic **Snake** game implemented in **x86 Assembly Language (MASM)** using the **Irvine32** library. The project shows low-level programming in practice: drawing graphics by writing directly to the console, reading keyboard input in real time, and managing all game state by hand.

![Assembly](https://img.shields.io/badge/Language-x86%20Assembly-red)
![Library](https://img.shields.io/badge/Library-Irvine32-blue)
![Platform](https://img.shields.io/badge/Platform-Windows%20Console-lightgrey)

---

## Features

- **Console graphics:** the board, snake, food and borders are drawn directly to the console
- **Real-time input:** the snake responds to key presses without waiting for Enter
- **Snake movement:** continuous movement, with the snake growing each time it eats
- **Food generation:** food appears at random positions on the board
- **Score tracking:** the score updates as food is eaten
- **Game-over detection:** the game ends when the snake hits a wall or itself

## Tech Stack

| Item | Details |
| --- | --- |
| Language | x86 Assembly (MASM) |
| Library | `Irvine32.inc` |
| Platform | Windows console |
| Source file | `Project.asm` |

## Getting Started

### Prerequisites

- Windows
- Visual Studio (with the C++ desktop workload) configured for MASM
- The [Irvine32 library](https://github.com/surferkip/asmbook) set up for Visual Studio

### Run it from Visual Studio

1. Open your MASM / Irvine32 project template.
2. Add `Project.asm` to the project.
3. Build and run (**Ctrl + F5**).

### Or build from the command line

Run these from a Visual Studio Developer Command Prompt, in a folder that contains `Irvine32.inc` and `Irvine32.lib`:

```bash
ml /c /coff /Zi Project.asm
link /subsystem:console /debug Project.obj Irvine32.lib kernel32.lib user32.lib
Project.exe
```

## How to Play

- Steer the snake with the keyboard so it eats the food.
- Each piece of food makes the snake longer and increases your score.
- Do not run into the walls or into your own body.

## How It Works

| Part | What it does |
| --- | --- |
| Rendering | Moves the cursor and writes characters to the console to draw the board, snake and food |
| Input | Polls the keyboard each frame so the direction can change in real time |
| Movement | Updates the head position, shifts the body, and removes the old tail unless food was eaten |
| Food | Picks a random board position for the next piece of food |
| Score | Increments on every piece of food and is shown during play |
| Game over | Checks for wall and self collision after every move |

## Project Structure

```
.
├── Project.asm     # Full game source
├── LICENSE
└── README.md
```

## What I Learned

- Working directly with registers, the stack and memory addresses
- Structuring a program with procedures in assembly
- Building a real-time game loop without a high-level framework
- Using the Irvine32 library for console I/O, random numbers and delays

## Author

**Talha Munir Saeed** ([@Talha-Munir-Saeed3](https://github.com/Talha-Munir-Saeed3))

## License

Released under the [MIT License](LICENSE).
