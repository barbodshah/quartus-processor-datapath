# Quartus processor datapath

A schematic-based course processor with 16-bit instructions and an 8-bit datapath. The two Quartus projects show a multicycle multiply design and a pipelined datapath. The schematics include the register file, ALU, instruction and data memories, and branch control.

| Folder | Project | Top level | Waveform to open |
| --- | --- | --- | --- |
| `multicycle/` | `Q2.qpf` | `Datapath` | `test.vwf` or `test-alu.vwf` |
| `pipeline/` | `Q2.qpf` | `Pipeline` | `Pipeline-test.vwf` |

Open the chosen project in Intel Quartus Prime or a compatible Quartus II environment. Keep the schematics, symbol files, and legacy LPM IP files alongside the project. Run Analysis & Elaboration and use a Quartus-compatible waveform simulator to apply the included stimuli. Program words live in each project's `instructions.mif`. Use the register write data and write enable to follow results. In the pipeline version, start with `IF.bdf`, `ID_RF.bdf`, `Ex.bdf`, and `Mem.bdf`.

The original projects use automatic device selection. For a hardware build, choose a compatible FPGA and supply board-specific pin and clock constraints. The supplied waveforms are simulation inputs.

## Example program

Both projects initialize instruction memory with a Fibonacci loop. In
`multicycle/instructions.mif`, addresses 0–3 initialize the two operands and
loop counters. Address 4 adds the operands, addresses 5–6 move the next pair
into place, and address 7 branches back through the loop. The pipeline
version spaces dependent operations with no-ops. Compare register writes
around those operations when reading the waveforms.
