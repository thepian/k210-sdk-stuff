Maix Go / K210 stuff
=====================

First, get the Kendryte C toolchain and copy or symlink the contents of the
`src/` folder to a checkout of `https://github.com/sipeed/LicheeDan_K210_examples.git`.

Then to build a certain project do:

```bash
mkdir build && cd build
cmake .. -DPROJ=<ProjectName> -DTOOLCHAIN=/opt/riscv-toolchain/bin && make
```

You will get 2 files, `build/<ProjectName>` and `build/<ProjectName>.bin`. The former
is an ELF executable, the latter a raw binary that can be flashed or written to
0x80000000 in SRAM and directly executed.

Projects
=========

glyph_mapping
-------------

Variation of the `DVP` sample that processes the camera input through a simple
DOS 8×8 font glyph-mapping algorithm and shows it on the display.

dump_otp
--------

Dumps the contents of the OTP (One-Time Programmable memory) of the K210 CPU to
serial output in Intel HEX format.