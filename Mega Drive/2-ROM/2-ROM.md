# Mega Drive Rom Hacking

## The ROM Header

The ROM Header is at the start.

The M68000 CPU expects to find its initial stack pointer address, initial program counter address, and the interrupt vector table.

[M68000 CPU - rom_header](rom_header.asm)

## Memory mapped I/O base addresses

vdp_control     = $C00004
vdp_data        = $C00000
z80_bus_req     = $00A11100
z80_bus_grant   = $00A11101
z80_reset       = $00A11200
z80_ram         = $00A00000
hw_revision     = $00A10001
tmss_write      = $00A14000
jp1ctrl         = $00A10009
jp2ctrl         = $00A1000B
extctrl         = $00A1000D

; VDP RAM operations and Registers
VDP_VRAM_WRITE  = %000001
VDP_CRAM_WRITE  = %000011
VDP_VSRAM_WRITE = %000101
VDP_VRAM_READ   = %000000
VDP_CRAM_READ   = %001000
VDP_VSRAM_READ  = %000100
VDP_REG_AUTOINC = 15        ; RAM access address auto-increment

## Trademark Security System

move.b  $00A10001,d0   ; Move Megadrive hardware ver. to d0

## System registers

REGS:00A10000 ; System registers
REGS:00A10000                 extern IO_PCBVER        ; DATA XREF: init+17C↑r
REGS:00A10002                 extern IO_CT1_DATA
REGS:00A10004                 extern IO_CT2_DATA
REGS:00A10006                 extern IO_EXT_DATA
REGS:00A10008                 extern IO_CT1_CTRL      ; DATA XREF: init+18↑r
REGS:00A10008                                         ; init:loc_374↑r ...
REGS:00A1000A                 extern IO_CT2_CTRL      ; DATA XREF: sub_1D28+8↑w
REGS:00A1000C                 extern IO_EXT_CTRL      ; DATA XREF: init+22↑r
REGS:00A1000C                                         ; init+174↑r
REGS:00A1000E                 extern IO_CT1_RX
REGS:00A10010                 extern IO_CT1_TX
REGS:00A10012                 extern IO_CT1_SMODE
REGS:00A10014                 extern IO_CT2_RX
REGS:00A10016                 extern IO_CT2_TX
REGS:00A10018                 extern IO_CT2_SMODE
REGS:00A1001A                 extern IO_EXT_RX
REGS:00A1001C                 extern IO_EXT_TX
REGS:00A1001E                 extern IO_EXT_SMODE

## Z80 Initialization

z80_bus_req   = $00A11100
z80_bus_grant = $00A11101
z80_reset     = $00A11200
z80_ram       = $00A00000