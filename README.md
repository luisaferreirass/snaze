# 🐍 Snaze — A Snake Trapped in a Maze

Snaze is a text-mode simulation of the classic **Snake** game, with a twist: the snake is trapped inside a **maze**.  
The project was developed in **C++** as part of the **Programming I (DIM0176)** course at the **Federal University of Rio Grande do Norte (UFRN)**.

The main goal is to implement an **artificial intelligence** capable of safely guiding the snake to the food, avoiding collisions with the walls and with its own body.

---

## 🎮 Features

- Loads levels from text files
- Supports multiple levels in a single file
- Lives and scoring system
- Random food spawning at valid positions
- Two types of snake control:
  - **Random** (random movement)
  - **Backtracking** (search-based AI)
- Real-time simulation in the terminal
- Game status messages:
  - Collision
  - Level complete
  - Victory
  - Defeat

---

## 🧠 Artificial Intelligence

The **backtracking** mode uses a search strategy to find a valid sequence of moves that takes the snake to the food, taking into account:

- The maze walls
- The invisible walls
- The snake's own body
- The simulation of the body's movement during the search

If no valid path to the food is found, the system automatically falls back to suggesting random moves.

---

## 📥 Input

The game levels are defined in `.txt` files.  
Each level contains:

- Board dimensions
- `#` → wall
- `.` → invisible wall
- `&` → snake starting position

A file can contain **one or more levels**, which are played in sequence.

---

## 📤 Output

During execution, the program displays in the terminal:

- A text representation of the maze
- The position of the snake and the food
- Number of lives left
- Current score
- Amount of food left
- Current level

Additional messages are displayed when:
- The snake collides
- A level is completed
- The game is won or lost

## ⚙️ How to run

### Build
```bash
make
./build/snaze
```

### Command-line options

| Option | Description | Default |
|-------|-----------|--------|
| `--help` | Shows the program help | - |
| `--fps <value>` | Sets the frames per second | 24 |
| `--lives <value>` | Number of snake lives | 5 |
| `--food <value>` | Total amount of food in the game | 10 |
| `--playertype <type>` | AI type: `random` or `backtracking` | random |

### Usage examples
```bash
# Run with default settings
./build/snaze

# Run with the backtracking AI and 3 lives
./build/snaze --playertype backtracking --lives 3

# Run at 60 FPS with 20 food items
./build/snaze --fps 60 --food 20
```

---

## 📁 Project structure
```
snaze/
├── src/              # Implementation files (.cpp)
├── include/          # Header files (.h)
├── data/             # Level configuration files
├── build/            # Compiled executable
├── Makefile          # Build script
├── README.md         # Main documentation
└── author.md         # Author information
```

