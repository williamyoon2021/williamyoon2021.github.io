+++
title = "Dynamically Generated AXI Interfaces"
#date = 2023-11-30
#updated = 2023-11-30
weight = 1
description = """In Summer '22 I worked on dynamically generating
AXI interfaces in Verilog for the purpose of interfacting with XRT shells."""


[extra]
+++

#### Overview

<div style="font-size:0.8em" >

I worked on a dynamic AXI generator in Rust that produced Verilog AXI wrappers
that allows lowered Calyx programs (i.e RTL Verilog) to be simulated/executed on FPGAs. This work
would not have been possible without the help of [Rachit Nigam][rachit], [Samuel Thomas][sam], [Andrew Butt][andrew], and [Adrian Sampson][adrian].

</div>

---

Canonical [AXI interfaces](https://developer.arm.com/documentation/ihi0022/latest)
can be complex to implement correctly. So much so that even some of Xilinx's (AMD's FPGA division)
[own examples](https://github.com/jofrfu/tinyTPU/blob/7c9a732dfd1e305fbd86b41a6fb3146ea64693de/src/vhdl/AXI/tinyTPU_v1_0_S00_AXI.vhd#L354-L365)
have bugs in their implementation that allow transactions to be [lost](https://zipcpu.com/formal/2019/04/16/axi-mistakes.html).

AXI interfaces are required to interface with FPGA shells such as Xilinx's [XRT](https://www.xilinx.com/products/design-tools/vitis/xrt.html).
While platforms like [Vitis](https://www.xilinx.com/products/design-tools/vitis.html)
exist that nominally help with AXI generation, the implementations produced have
historically been buggy, as mentioned above. Furthermore, relying on Vitis 
"[wizards](https://xilinx.github.io/xup_compute_acceleration/rtl_kernel_lab.html)"
is clunky and requires more buy-in to Vitis ecosystem than some would like.

This was the case at [Capra](https://capra.cs.cornell.edu/). We had a desire to
be able to run [Calyx](https://calyxir.org/) programs on FPGAs while being coupled
to the Vitis ecosystem as little as possible. While we needed Vitis to be able
to produce [xclbins](https://xilinx.github.io/XRT/master/html/formats.html),
we hoped to avoid opening up a GUI and invoking an
"RTL Kernel Wizard".

To enable easy execution, I worked on a dynamic AXI generator that took in Calyx
programs as input, and output verilog files that contained both the lowered
Calyx program as well as an AXI wrapper that allowed for our RTL design
to interface with XRT.

This [work](https://github.com/cucapra/calyx/tree/master/calyx-backend/src/xilinx)
was done in Rust, and built off of initial generators written by
[Samuel Thomas][sam].
[Andrew Butt][andrew] provided an immense amount of help
in navigating AXI specs correctly, and debugging waveforms of buggy AXI interfaces.
Without either of them, this work couldn't have happened.



[adrian]: https://www.cs.cornell.edu/~asampson/

[rachit]: https://rachit.pl/

[andrew]: https://github.com/andrewb1999

[sam]: https://github.com/sgpthomas








