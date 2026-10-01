
# ⚡ 8051 Simulator

<p align="center">
  <img src="https://img.shields.io/badge/8051-Microcontroller-blue?style=for-the-badge" alt="8051 Microcontroller">
  <img src="https://img.shields.io/badge/Web-Based-Simulator-success?style=for-the-badge" alt="Web Based Simulator">
  <img src="https://img.shields.io/badge/Educational-Tool-orange?style=for-the-badge" alt="Educational Tool">
</p>

<p align="center">
  <strong>A browser-based Intel 8051 microcontroller simulator for learning, experimentation, and instruction-level execution.</strong>
</p>

<p align="center">
  <a href="https://8051simulator-biet.netlify.app/">
    🚀 Launch Simulator
  </a>
</p>

---

## 📖 About

**8051 Simulator** is an interactive web-based environment designed to help students and embedded-systems learners understand the fundamentals of the **Intel 8051 microcontroller**.

Instead of requiring physical hardware for every experiment, the simulator provides a visual environment where users can work with 8051 assembly instructions and observe the internal state of the simulated microcontroller.

The simulator is intended to make low-level microcontroller concepts easier to understand by providing immediate visibility into registers, memory, program execution, and processor state.

---

## 🚀 Live Demo

### [Open 8051 Simulator](https://8051simulator-biet.netlify.app/)

No installation is required to try the simulator online.

---

## ✨ Features

### 🧠 8051 CPU Simulation

Simulate the fundamental components of the 8051 architecture and observe how instructions affect processor state.

The simulator provides visibility into important CPU registers including:

- Accumulator (`A`)
- `B` register
- Program Counter (`PC`)
- Stack Pointer (`SP`)
- Data Pointer (`DPTR`)
- Program Status Word (`PSW`)
- General-purpose registers (`R0` – `R7`)

---

### 🚩 Flag Register

The simulator provides visibility into important 8051 status flags.

| Flag | Description |
|------|-------------|
| `CY` | Carry Flag |
| `AC` | Auxiliary Carry |
| `F0` | User Flag |
| `OV` | Overflow Flag |
| `P` | Parity Flag |

These flags are particularly useful when studying arithmetic, logical operations, branching, and processor state changes.

---

### 🗃️ Register Banks

The 8051 provides four register banks containing `R0` through `R7`.

The simulator makes it possible to observe register values while experimenting with different instructions and register operations.

```text
Register Banks

        Bank 0   Bank 1   Bank 2   Bank 3

R0        00       00       00       00
R1        00       00       00       00
R2        00       00       00       00
R3        00       00       00       00
R4        00       00       00       00
R5        00       00       00       00
R6        00       00       00       00
R7        00       00       00       00
````

---

 ### 💾 Internal RAM

 The simulator provides a visual representation of internal RAM.

 This allows learners to observe how instructions read from and write to memory during execution.

 Memory values can be inspected using hexadecimal representation.

```
Address      Data

0000H        00
0001H        00
0002H        00
0003H        00
...
```

---

 ### 🔌 GPIO / Ports

 The simulator provides a software representation of the 8051 I/O ports.

 The classic 8051 architecture contains four 8-bit ports:

```
P0 ───────── 8-bit I/O Port
P1 ───────── 8-bit I/O Port
P2 ───────── 8-bit I/O Port
P3 ───────── 8-bit I/O Port
```

 This makes it possible to experiment with port manipulation without requiring physical hardware.

---

 ### ▶️ Program Execution

 The simulator supports instruction-level execution workflows.

 Users can:

 - Assemble a program
- Run the program
- Execute instructions step by step
- Reset the simulated processor
- Observe register changes
- Observe memory changes

 The basic workflow is:

```
┌─────────────┐
│ Write Code  │
└──────┬──────┘
       ↓
┌─────────────┐
│   Assemble  │
└──────┬──────┘
       ↓
┌─────────────┐
│     Run     │
└──────┬──────┘
       ↓
┌─────────────┐
│ Observe CPU │
└─────────────┘
```

---

 ## 🧪 Step-by-Step Execution

 The **Step** operation is useful when learning how individual assembly instructions affect the processor.

 For example:

```
MOV A, #05H
MOV R0, #03H
ADD A, R0
```

 The execution can be observed instruction by instruction.

```
Instruction              A        R0

MOV A, #05H              05H      00H
MOV R0, #03H             05H      03H
ADD A, R0                08H      03H
```

 This makes the simulator useful for understanding the relationship between assembly instructions and CPU state.

---

 ## 🔄 Reset

 The **Reset** operation returns the simulated processor to its initial state.

 This allows programs to be executed repeatedly from a clean state without refreshing the entire application.

---

 # 🧩 8051 Architecture

 The simulator is based around the fundamental architecture of the Intel 8051 microcontroller.

```
                    ┌───────────────────────┐
                    │       8051 CPU        │
                    ├───────────────────────┤
                    │                       │
                    │   Accumulator (A)     │
                    │   B Register          │
                    │   PSW                 │
                    │   PC                  │
                    │   SP                  │
                    │   DPTR                │
                    │                       │
                    └───────────┬───────────┘
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
              ▼                 ▼                 ▼
        ┌──────────┐      ┌──────────┐      ┌──────────┐
        │   RAM    │      │ Registers│      │ Program  │
        │          │      │ R0 - R7  │      │ Memory   │
        └──────────┘      └──────────┘      └──────────┘
              │
              ▼
        ┌──────────────┐
        │ GPIO Ports   │
        │ P0 P1 P2 P3  │
        └──────────────┘
```

---

 # 📝 Assembly Programming

 The simulator is designed around **8051 Assembly Language**.

 A simple example:

```
ORG 0000H

MOV A, #05H
MOV R0, #03H
ADD A, R0

END
```

 After execution:

```
A  = 08H
R0 = 03H
```

---

 ## 🔢 Number Representation

 8051 assembly programs commonly work with hexadecimal values.

 Example:

```
MOV A, #25H
MOV R0, #10H
MOV P1, #0FFH
```

 The simulator's visual interface uses hexadecimal values to make register and memory inspection easier.

---

 # 🛠️ Typical Learning Workflow

```
             8051 PROGRAM
                   │
                   ▼
          ┌─────────────────┐
          │ Write Assembly  │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │    Assemble     │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │      Run        │
          └────────┬────────┘
                   │
                   ▼
       ┌───────────┼───────────┐
       │           │           │
       ▼           ▼           ▼
    Registers     RAM        Ports
       │           │           │
       └───────────┼───────────┘
                   ▼
          Understand Result
```

---

 # 🎓 Educational Use

 The simulator is particularly useful for:

 - Microprocessor and microcontroller laboratories
- 8051 assembly language practice
- Embedded systems courses
- Understanding CPU registers
- Learning addressing concepts
- Studying arithmetic operations
- Studying logical operations
- Understanding RAM operations
- Learning GPIO programming
- Debugging assembly programs
- Practicing before working with physical 8051 hardware

---

 # 💡 Example Programs

 ## Addition

```
ORG 0000H

MOV A, #05H
MOV R0, #03H
ADD A, R0

END
```

 ### Expected Result

```
A = 08H
```

---

 ## Subtraction

```
ORG 0000H

MOV A, #09H
MOV R0, #04H
SUBB A, R0

END
```

---

 ## Register Transfer

```
ORG 0000H

MOV A, #55H
MOV R0, A
MOV R1, R0

END
```

 Expected:

```
A  = 55H
R0 = 55H
R1 = 55H
```

---

 ## Port Output

```
ORG 0000H

MOV A, #0FFH
MOV P1, A

END
```

 This demonstrates writing a value to Port 1.

---

 ## Loop Example

```
ORG 0000H

MOV R0, #05H

LOOP:
    DJNZ R0, LOOP

END
```

 This demonstrates a simple decrement-and-jump control-flow operation.

---

 # 🖥️ Interface

 The simulator is organized around the major components of an 8051 development environment.

```
┌─────────────────────────────────────────────────────┐
│                  8051 SIMULATOR                    │
├──────────────────────┬──────────────────────────────┤
│                      │                              │
│   Assembly Editor    │      CPU / Registers        │
│                      │                              │
│   MOV A, #05H        │      A       00H            │
│   MOV R0, #03H       │      B       00H            │
│   ADD A, R0          │      PC      0000H          │
│                      │      SP      07H            │
│                      │      DPTR    0000H          │
│                      │                              │
├──────────────────────┴──────────────────────────────┤
│                    FLAGS                            │
│       CY     AC     OV     P                        │
├─────────────────────────────────────────────────────┤
│                  REGISTER BANKS                     │
├─────────────────────────────────────────────────────┤
│                     RAM                             │
├─────────────────────────────────────────────────────┤
│                  GPIO / PORTS                       │
├─────────────────────────────────────────────────────┤
│       ASSEMBLE       RUN       STEP       RESET     │
└─────────────────────────────────────────────────────┘
```

---

 # ⚙️ Execution Model

 At a high level, program execution follows:

```
Assembly Source
       │
       ▼
   Assembler
       │
       ▼
Instruction Representation
       │
       ▼
Instruction Fetch
       │
       ▼
Instruction Decode
       │
       ▼
Instruction Execute
       │
       ▼
CPU State Update
       │
       ├──────────────┐
       ▼              ▼
   Registers         Memory
       │              │
       └──────┬───────┘
              ▼
         UI Refresh
```

---

 # 🔍 What You Can Observe

 During execution, the simulator allows you to inspect changes to important parts of the processor state.

 ### CPU

```
A
B
PC
SP
DPTR
PSW
```

 ### Registers

```
R0
R1
R2
R3
R4
R5
R6
R7
```

 ### Flags

```
CY
AC
OV
P
```

 ### Ports

```
P0
P1
P2
P3
```

 ### Memory

```
Internal RAM
```

---

 # 🌐 Browser-Based

 One of the main goals of the project is to make 8051 experimentation accessible through a web browser.

```
┌──────────────────┐
│      Browser     │
├──────────────────┤
│                  │
│  8051 Simulator  │
│                  │
└────────┬─────────┘
         │
         ▼
   Simulated 8051
```

 This removes the need to connect a physical microcontroller simply to experiment with basic assembly programs.

---

 # 📚 Why Use a Simulator?

 Learning a microcontroller becomes significantly easier when the internal state can be observed while instructions execute.

 With a simulator, students can directly connect:

```
Instruction
     ↓
CPU Operation
     ↓
Register Change
     ↓
Memory Change
     ↓
Output
```

 This provides a practical way to understand concepts that can otherwise be difficult to visualize.

---

 # 🔧 Future Improvements

 Potential areas for future development include:

 - Expanded instruction-set coverage
- More detailed PSW visualization
- Timer 0 simulation
- Timer 1 simulation
- Interrupt simulation
- Serial communication simulation
- External memory support
- Breakpoints
- Program loading from assembly files
- Intel HEX support
- More GPIO visualization
- Peripheral simulation
- More built-in example programs
- Enhanced debugging tools

---

 # 🎯 Project Goals

 The project focuses on three primary goals:

 ### 1\. Accessibility

 Make 8051 programming accessible from a browser.

 ### 2\. Visualization

 Make internal microcontroller state easier to understand.

 ### 3\. Learning

 Provide students with a practical environment for experimenting with 8051 assembly.

---

 # 👨‍🎓 Intended Audience

 This project is suitable for:

```
Engineering Students
        │
        ├── Electronics
        ├── Electrical
        ├── Computer Science
        └── Embedded Systems
                │
                ▼
          8051 Learners
```

 It can also be useful for educators demonstrating microcontroller concepts during lectures or laboratory sessions.

---

 # 🚀 Getting Started

 The easiest way to use the simulator is through the live deployment:

 **https://8051simulator-biet.netlify.app/**

 Open the application, write an 8051 assembly program, assemble it, and use the execution controls to observe the simulated processor state.

---

 # 🤝 Contributing

 Contributions are welcome.

 If you would like to improve the simulator:

 1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the simulator.
5. Commit your changes.
6. Push your branch.
7. Open a Pull Request.

 Example:

```
git checkout -b feature/new-instruction
```

```
git add .
git commit -m "feat: add new 8051 instruction support"
```

```
git push origin feature/new-instruction
```

---

 # 🐛 Bug Reports

 If you find an issue, please provide:

 - A clear description
- Steps to reproduce the issue
- The assembly program used
- Expected behavior
- Actual behavior
- Screenshots when useful

 This makes debugging and verification much easier.

---

 # 📌 Project Philosophy

 > **See the instruction. Understand the operation. Observe the result.**

 The simulator is built around the idea that microcontroller programming becomes easier to learn when the internal machine state is visible instead of hidden behind a physical device.

---

 # 🔗 Links

 | Resource | Link |
| --- | --- |
| 🚀 Live Simulator | https://8051simulator-biet.netlify.app/ |
| 📦 Deployment | Netlify |
| 🧠 Architecture | Intel 8051 |
| 🎓 Primary Use | Education & Embedded Systems |

---

 \<p align="center"\> ## ⚡ 8051 Simulator

 **Write. Assemble. Execute. Observe. Learn.**

 \<br\> \<a href="https://8051simulator-biet.netlify.app/"\> \<strong\>🚀 Launch the Simulator\</strong\> \</a\> \</p\> 
