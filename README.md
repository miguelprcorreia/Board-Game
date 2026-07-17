<div align="center">

# 🧩 Board-Game

**Puzzle solver game built in C** — project for *Laboratórios de Informática II* @ University of Minho

![C](https://img.shields.io/badge/-C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)
![Makefile](https://img.shields.io/badge/-Makefile-427819?style=for-the-badge&logo=gnu&logoColor=white)
![CUnit](https://img.shields.io/badge/-CUnit-orange?style=for-the-badge)

</div>

---

## 📖 About

This **Board-Game** is a C implementation of a logic puzzle developed for *Laboratórios de Informática II* at the University of Minho. The game is played on a grid where each cell holds a symbol, and the goal is to mark cells as either **kept** (uppercase) or **crossed out** (`#`), following these rules:

- Each row and column may contain **only one** kept instance of a given symbol — every other occurrence of that symbol must be crossed out.
- Crossed-out cells cannot be orthogonally adjacent to each other.
- All kept cells must form a **single connected region**, reachable through orthogonal paths.

The program runs as a **REPL** (read–execute–print–loop), letting the player select cells, mark/cross them, undo moves, save/load game state, get hints, or ask the solver to finish the puzzle automatically.

### 🎮 Commands

| Command | Action |
|---|---|
| `g jogo` | Save the current game state to a file |
| `l jogo` | Load a game state from a file |
| `<coord>` | Select a cell (format: `<lowercase letter><number>` → column/row) |
| `b <coord>` | Mark the selected cell as kept (uppercase) |
| `r <coord>` | Cross out the selected cell (`#`) |
| `v` | Verify the board and list violated constraints |
| `a` | Auto-infer one step of deducible moves |
| `A` | Repeat `a` until no more changes can be inferred |
| `R` | Solve the puzzle automatically |
| `d` | Undo the last command |
| `s` | Exit the program |

### 💾 Save file format

```
<rows> <columns>
<row 1 symbols>
<row 2 symbols>
...
```

Example:
```
5 5
ecadc
dcdec
bddce
cdeeb
accbb
```

---

## 🚀 Getting Started

Build and run the game:

```bash
make jogo
./jogo
```

## 🧪 Testing

Run the test suite (built with **CUnit**):

```bash
make testar
```

Compilation uses strict flags for safety and correctness:

```
-Wall -Wextra -pedantic -O1 -fsanitize=address -fno-omit-frame-pointer -g
```

---

## 🗂️ Project Structure

```
Board-Game/
├── lib/            # Core game logic
├── testes/         # CUnit test suite
├── Makefile        # Build targets: jogo, testar
├── j1.txt … j5.txt # Sample puzzle boards
└── stackSave.txt   # Undo history save file
```

---

<div align="center">

🔗 [github.com/miguelprcorreia/Board-Game](https://github.com/miguelprcorreia/Board-Game)

</div>
