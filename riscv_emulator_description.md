# RISC-V Assembler and Emulator

This project is divided into **5 main segments** for a clearer and more interactive workflow.

## 1. Code Editor
This is the main workspace where users can write and edit RISC-V assembly code.

### Features
- Write and modify assembly programs directly inside the emulator
- Line-by-line editing with line numbering support
- Syntax highlighting for instructions, registers, immediates, labels, and comments
- Execution-line highlighting during program run or step execution
- Drag-and-drop file loading support
- Comment / uncomment selected lines
- Open source files with `.rvx` support
- Save code

## 2. Registers Panel
This segment shows the **Program Counter (PC)** and the **integer register set (`x0` to `x31`)**.

### Features
- View register values in **HEX**, **DEC**, and **BIN**
- Binary values are grouped for better readability
- Real-time register updates during execution
- Program Counter tracking during assembly and execution
- Register role hints for standard RISC-V register usage
- Editable register values for experimentation
- 64-bit value handling in the register display
- `x0` remains fixed as the zero register

## 3. Memory Panel
This segment allows users to inspect emulator memory visually.

### Memory Details
- **Total memory size:** 4096 bytes
- **Text segment:** 2048 bytes
- **Data segment:** 1024 bytes
- **Heap segment:** 256 bytes
- **Stack segment:** remaining 768 bytes

### Features
- Two-column memory view for easier inspection
- Memory display modes: **HEX**, **DEC**, and **BIN**
- Paged navigation through memory
- Search memory addresses in hexadecimal
- Quick jump to the current **stack pointer (SP / x2)**
- Highlighting of active instruction bytes
- Little-endian storage visualization
- Byte-level memory editing support

## 4. Log Panel
This segment displays assembly and execution feedback in a running log.

### Details visible here
- Assembly progress and generated machine code
- Binary and hexadecimal instruction output
- Memory byte storage details
- Executed source line information
- Register update messages
- Memory write activity
- Pause, resume, finish, and reset status messages
- Assembly or execution errors

## 5. Control Panel
This segment contains the main controls used to interact with the emulator.

### Main Controls
- **Open** – load a source file
- **Save** – save the current source code
- **Assemble** – convert assembly code into machine code and place it in memory
- **Run** – execute the program continuously
- **Play / Pause** – pause or resume execution
- **Step** – execute one instruction at a time
- **Reset** – restore the emulator to its initial state

### Extra Buttons
- **Examples** – sample program section
- **Features** – feature overview section
- **About** – project information section

> **Note:** Examples, Features, and About are currently marked as work in progress.

## Supported Instructions

### R-Type
- `add`
- `sub`
- `xor`
- `or`
- `and`
- `sll`
- `srl`
- `mul`
- `div`

### I-Type
- `addi`
- `xori`
- `ori`
- `andi`
- `slli`
- `srli`
- `jalr`

### Load Instructions
- `lb`
- `lbu`
- `lh`
- `lhu`
- `lw`
- `lwu`
- `ld`

### Store Instructions
- `sb`
- `sh`
- `sw`
- `sd`

### Branch Instructions
- `beq`
- `bne`
- `blt`
- `bge`

### U-Type
- `lui`

### UJ-Type
- `jal`

## Opcode Table

| Instruction | Type | Opcode | Funct3 | Funct7 |
|---|---|---|---|---|
| `add`  | R  | `0110011` | `000` | `0000000` |
| `sub`  | R  | `0110011` | `000` | `0100000` |
| `xor`  | R  | `0110011` | `100` | `0000000` |
| `or`   | R  | `0110011` | `110` | `0000000` |
| `and`  | R  | `0110011` | `111` | `0000000` |
| `sll`  | R  | `0110011` | `001` | `0000000` |
| `srl`  | R  | `0110011` | `101` | `0000000` |
| `mul`  | R  | `0110011` | `000` | `0000001` |
| `div`  | R  | `0110011` | `100` | `0000001` |
| `addi` | I  | `0010011` | `000` | — |
| `xori` | I  | `0010011` | `100` | — |
| `ori`  | I  | `0010011` | `110` | — |
| `andi` | I  | `0010011` | `111` | — |
| `slli` | I  | `0010011` | `001` | `0000000` |
| `srli` | I  | `0010011` | `101` | `0000000` |
| `jalr` | I  | `1100111` | `000` | — |
| `lb`   | I  | `0000011` | `000` | — |
| `lh`   | I  | `0000011` | `001` | — |
| `lw`   | I  | `0000011` | `010` | — |
| `ld`   | I  | `0000011` | `011` | — |
| `lbu`  | I  | `0000011` | `100` | — |
| `lhu`  | I  | `0000011` | `101` | — |
| `lwu`  | I  | `0000011` | `110` | — |
| `sb`   | S  | `0100011` | `000` | — |
| `sh`   | S  | `0100011` | `001` | — |
| `sw`   | S  | `0100011` | `010` | — |
| `sd`   | S  | `0100011` | `011` | — |
| `beq`  | SB | `1100011` | `000` | — |
| `bne`  | SB | `1100011` | `001` | — |
| `blt`  | SB | `1100011` | `100` | — |
| `bge`  | SB | `1100011` | `101` | — |
| `lui`  | U  | `0110111` | — | — |
| `jal`  | UJ | `1101111` | — | — |

## Shortcuts
- **Shift + O** or **Ctrl + O** – Open
- **Ctrl + S** – Save
- **Shift + A** – Assemble
- **Shift + R** – Run
- **Shift + P** – Pause
- **Shift + S** – Step
- **Alt + R** – Reset
