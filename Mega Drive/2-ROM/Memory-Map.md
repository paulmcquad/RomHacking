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
| $0xA11000 | $0xA11FFF |       | [Z80 Control](./Memory-Map.md#z80-control-area)                |
| $0xA14000 | $0xA14003 |       | [TMSS "SEGA"](https://segaretro.org/TradeMark_Security_System) |
| $0xC00000 | $0xDFFFFF |       | [VDP Ports](Memory-Map.md#visual-display-processor---vdp-area) |
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

| Start   | End     | Description                             |
|---------|---------|-----------------------------------------|
| $0xA10000 | $0xA10001 | Version register (read-only word-long)  |
| $0xA10002 | $0xA10003 | Controller 1 data                       |
| $0xA10004 | $0xA10005 | Controller 2 data                       |
| $0xA10006 | $0xA10007 | Expansion port data                     |
| $0xA10008 | $0xA10009 | Controller 1 control                    |
| $0xA1000A | $0xA1000B | Controller 2 control                    |
| $0xA1000C | $0xA1000D | Expansion port control                  |
| $0xA1000E | $0xA1000F | Controller 1 serial transmit            |
| $0xA10010 | $0xA10011 | Controller 1 serial receive             |
| $0xA10012 | $0xA10013 | Controller 1 serial control             |
| $0xA10014 | $0xA10015 | Controller 2 serial transmit            |
| $0xA10016 | $0xA10017 | Controller 2 serial receive             |
| $0xA10018 | $0xA10019 | Controller 2 serial control             |
| $0xA1001A | $0xA1001B | Expansion port serial transmit          |
| $0xA1001C | $0xA1001D | Expansion port serial receive           |
| $0xA1001E | $0xA1001F | Expansion port serial control           |
| $0xA10020 | $0xA10FFF | Reserved                                |

### Z80 Control Area

| Start    | End     | Description           |
|----------|---------|-----------------------|
| $0xA11000  |           | Memory mode register  |
| $0xA11002  | $0xA110FF | Reserved              |
| $0xA11100  | $0xA11101 | Z80 bus request       |
| $0xA11102  | $0xA111FF | Reserved              |
| $0xA11200  | $0xA11201 | Z80 reset             |
| $0xA11202  | $0xA13FFF | Reserved              |


### Visual Display Processor - VDP Area

| Start    | End      | Description              |
|----------|----------|--------------------------|
| $0xC00000  | $0xC00001  | VDP data                 |
| $0xC00002  | $0xC00003  | VDP data (mirror)        |
| $0xC00004  | $0xC00005  | VDP control              |
| $0xC00006  | $0xC00007  | VDP control (mirror)     |
| $0xC00008  | $0xC00009  | VDP HV counter           |
| $0xC0000A  | $0xC00010  | Reserved                 |
| $0xC00011  |            | PSG output               |
| $0xC00013  | $0xC00017  | PSG output (mirror)      |
| $0xC0001C  | $0xC0001D  | Debug register           |
| $0xC0001E  | $0xC0001F  | Debug register (mirror)  |
| $0xC00012  | $0xFEFFFF  | Reserved                 |