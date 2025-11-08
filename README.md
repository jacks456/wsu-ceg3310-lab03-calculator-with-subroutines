# LC‑3 Calculator with Subroutines (CEG 3310 — Lab 3)

> **Goal:** Build an interactive calculator in LC‑3 using **modular subroutines** for input, operation selection, computation, and output—without using a full runtime stack.

Based on Wright State University **CEG 3310** Lab 3.

## 🧩 Features (per spec)
- Accepts **two operands** in the range **0–99**
- Supports operations: **+**, **−**, and **\*** (multiplication)
- Displays **signed results** (up to 4 digits)
- Loops to allow **multiple calculations** until user exits
- Organized into subroutines:
  - `GETNUM` — read and validate 0–99 from keyboard (ASCII → integer)
  - `GETOP` — read operator character and validate (+/−/*)
  - `CALC`  — perform the requested operation
  - `DISPLAY` — print signed decimal result

## 🧰 Tools
- LC‑3 simulator (PennSim/lc3tools)
- Keyboard polling (TRAP x20) and console output (TRAP x21)

## ▶️ How to Run
1. Assemble `lab03_calc.asm` to object code
2. Load in LC‑3 simulator
3. Start at `MAIN` and run
4. Enter operand1, operator, operand2 when prompted

**Example session**
```
> 12
> *
> 09
= 108
```

## 🧱 Repo Structure
```
src/
  lab03_calc.asm
docs/
  routine-map.md        # register usage for each routine
  io-format.txt         # input/output prompts & formats
README.md
LICENSE
```

## 🔧 Design Notes
- Uses **register conventions** documented in `routine-map.md`
- Handles ASCII → integer conversion by subtracting `'0'`
- Checks basic input validity; reprompts on invalid op
- Keeps state in registers—**no stack frames** required for this lab

## ✅ Testing
- Unit cases: `GETNUM` with 0, 9, 10, 99, invalid characters
- Ops: 7+5=12, 7−9=−2, 12*9=108, 0*99=0
- Display: verify minus sign and width for 3–4 digit results

## 📚 Academic Integrity
Source includes **only my implementation**. The lab handout is not re‑published here; see your course policy.
