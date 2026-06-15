# Digital Logic

Digital systems represent information as discrete levels (0 and 1) and process it with logic gates. They are robust to noise and the foundation of all computing.

## Number Systems

Digital hardware works in binary; hexadecimal is shorthand. Conversions between binary, decimal, and hex, plus **two's complement** for signed integers, are the daily arithmetic of digital design.

## Boolean Algebra

Logic functions obey Boolean algebra:
\\[
A + 0 = A,\quad A\cdot 1 = A,\quad A + \bar{A} = 1,\quad A\cdot\bar{A} = 0,
\\]
with **De Morgan's laws** \\(\overline{A+B} = \bar{A}\bar{B}\\) and \\(\overline{AB} = \bar{A} + \bar{B}\\). These let us simplify and transform logic.

## Logic Gates

| Gate | Function |
|---|---|
| AND | \\(Y = AB\\) |
| OR | \\(Y = A + B\\) |
| NOT | \\(Y = \bar{A}\\) |
| NAND / NOR | universal gates |
| XOR | \\(Y = A\oplus B\\) (sum bit) |

NAND and NOR are **functionally complete** — any logic can be built from either alone.

## Combinational Logic

Outputs depend only on present inputs. Designed via truth tables, simplified with **Karnaugh maps** or Quine–McCluskey, and realized as adders, multiplexers, decoders, and comparators. The full adder is the building block of arithmetic units.

## Sequential Logic

Outputs depend on inputs **and** stored state. The basic memory element is the **flip-flop** (D, JK, T), clocked to update synchronously. Sequential circuits include registers, counters, and **finite state machines (FSMs)**, the model for controllers and protocols.

## Timing and Hazards

Real gates have propagation delay. Setup/hold times constrain clock speed; the maximum clock frequency is set by the longest combinational path between registers (the critical path). Metastability and glitches must be managed in design.

## From Logic to Systems

Modern designs are described in hardware-description languages (Verilog, VHDL) and synthesized to FPGAs or ASICs. CMOS technology realizes gates with complementary MOSFETs, drawing power mainly when switching.

## See Also

- [Semiconductors](semiconductors.md)
- [Z-Transform](../../signals/z-transform.md) — sampled/discrete systems.
