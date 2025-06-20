# Mega Drive Rom Hacking

## 3 (VDP) Visual Display Processor

VRAM -  Video RAM
VSRAM - Video scroll RAM
CRAM -  Color RAM.

Although the physical CRAM is 64 9-bit words, the VDP memory access port maps that to a 16-bit word with additional "don't care" bits to ensure that each of the color channels sits in a separate 4-bit portion, and so the color values are expressed in hex rather than octal:

???? BBB? GGG? RRR?

The color value $EE0 above, then, is 0000 1110 1110 0000 in binary, and thus 100% blue and green but 0% red, giving cyan.

## Loading Patterns

A pattern is a re-usable 8x8-pixel graphics block, where each pixel is populated with one of the colors from a selected color palette.