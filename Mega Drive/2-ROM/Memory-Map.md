# Mega Drive Rom Hacking

## Memory Map

[Sega Mega Drive/Memory map](https://segaretro.org/Sega_Mega_Drive/Memory_map)

## Motorola 68K Area - @ 7.6 MHz

| Start     | End       | Size  | Description                                                    |
|-----------|-----------|-------|----------------------------------------------------------------|
| $0x000000 | $0x3FFFFF | 4MiB  | [Vector table, ROM Cartridge](./rom_header.asm)                |
| $0x400000 | $0x7FFFFF | 4MiB  | Reserved (used by the Mega-CD and 32X)                         |
| $0x800000 | $0x9FFFFF | 4MiB  | Reserved (used by the 32X)                                     |
| $0xA00000 | $0xA0FFFF | 64KiB | [Z80 Area](./Memory-Map.md#zilog-z80-area----358-mhz)          |
| $0xA10000 | $0xA10FFF |       | [I/O Area - Registers](./Memory-Map.md#io-area---registers)    |
| $0xA11000 | $0xA11FFF |       | Z80 Control (IO_RAMMODE)                                       |
| $0xC00000 | $0xDFFFFF |       | [VDP Area](Memory-Map.md#visual-display-processor---vdp-area) |
| $0xFF0000 | $0xFFFFFF |       | 68000 RAM                                                      |

### Zilog Z80 Area - @ 3.58 MHz

| Start   | End     | Size | Description        |
|---------|---------|------|--------------------|
| $0xA00000 | $0xA01FFF | 4KiB | Sound RAM          |
| $0xA02000 | $0xA03FFF | 4KiB | Sound RAM (mirror) |
| $0xA04000 | $0xA04003 |      | Sound Chip (Z80_YM2612)        |
| $0xA04004 | $0xA05FFF |      | Prohibited         |
| $0xA06000 | $0xA06001 |      | Bank Register      |

### I/O Area - Registers

### Visual Display Processor - VDP Area

