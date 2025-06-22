# Mega Drive Research

# Online Resources

* [SGDK - A free and open development kit for the Sega Mega Drive](https://github.com/Stephane-D/SGDK?tab=readme-ov-file#mega-drive-technical-info-references)

* [Awesome Mega Drive Development](https://github.com/And-0/awesome-megadrive)

# Technical Details

1. [Hello, Sega Genesis - A post about experimenting with MD dev (includes code examples)](https://log.martinatkins.me/2020/01/20/hello-sega-genesis/)

2. [MegaDrive Development Wiki](https://wiki.megadrive.org/index.php?title=Main_Page)

# The ROM Header


# System Registers
$00A10001


# I/O Area Memory Map

vdp_control     = $C00004
vdp_data        = $C00000

z80_bus_req   = $00A11100
z80_bus_grant = $00A11101
z80_reset     = $00A11200
z80_ram       = $00A00000

# Color Palette

The Genesis capabilities are more modest: 3 bits per channel (512 distinct colors) of which up to 16 can be active at once.

Palettes are kept in a special portion of the video RAM called "color RAM", which is addressed separately from the main video RAM.

6 colors each, over four distinct palettes.

# Disassembles

[ Toejam & Earl Disassembly](https://github.com/bstreiff/tje-disasm)