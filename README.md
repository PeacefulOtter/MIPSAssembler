

Works with most MIPS instructions (see list below) and supports all formats (I, R, J).
Supports for new instructions can be easily added by editing ParserSelection.scala

## How to Use

### From List

```scala
val lines = List("MY_INSTRUCTION_1", "MY_INSTRUCTION_2", ...)
val bin = Assembler.parseToBin(lines) // For binary string output
val hex = Assembler.parseToHex(lines) // For hex string output
```

### From File

 - Write MIPS commands in a file under the `res` folder.
 - Scala code:
```scala
Assembler.parseFile("MY_FILE.txt", "output.txt")
```

In this case, you would find the output file under `res/output.txt`.

## Support

#### List of supported instructions

 - `nop`
 - `addi`
 - `addiu`
 - `andi`
 - `ori`
 - `xori`
 - `slti`
 - `sltiu`
 - `beq`
 - `bne`
 - `blt`
 - `bge`
 - `add`
 - `addu`
 - `sub`
 - `subu`
 - `and`
 - `or`
 - `xor`
 - `sllv`
 - `srlv`
 - `slt`
 - `sltu`
 - `srav`
 - `sll`
 - `srl`
 - `sra`
 - `lw`
 - `sw`
 - `j`
 - `jal`

#### List of supported formats

 - Registers: `t`, `r` and `zero` (ex: `t1`, `r6`)
 - Immediate: `int` and `hex` (ex: `42`, `0x666`)
 - LW and SW commands are used the same way as any I-instructions, it does NOT support the following format:
   - `lw/sw t2 0x4(zero)`
   - Instead use: `lw/sw t2 0x4` (immediate = base + offset)
