+++
title = "Calyx"
description = "Calyx is a compiler infrastructure for languages that targets hardware accelerators."
weight = 0

[extra]
local_image = "projects/calyx/calyx-project.png"
+++



<div style="font-size:0.8em" >

For more in depth explanations on some of the work I've done for Calyx, see
my [research](../../research).

</div>

---

[Calyx](https://calyxir.org) is a shared compiler infrastructure accelerating the development
of specialized hardware accelerators. Calyx simplifies the encoding of high-level semantics
and automatically optimizes programs when being lowered to synthesizable designs.
Calyx is written in Rust, and utilizes tools built in Python, Bash, and Verilog.

I've worked with [Rachit Nigam][rachit] and [Adrian Sampson][adrian] approaching on two years now,
to show that complex communication protocols can be implemented in
Calyx. Implementing such protocols in a high-level language such as Calyx helps
reason about implementations, and avoids common bugs that exist even in
vendors' own examples.

{% resize_image(path="bug.png", width=800, height=481, op="fit") %}
A bug found in Xilinx example cores. Taken from <a href="https://zipcpu.com/formal/2019/04/16/axi-mistakes.html">ZipCPU</a>.
{% end %}

My current work is on creating push-button workflows that enables executing programs
on FPGAs via Calyx transformations and AXI-wrappers.

#### [View Calyx on GitHub](https://github.com/cucapra/calyx) {.centered-text}

## Contributions

- [**AXI Wrapper generator**](../../research/axi-interface) dynamically produces wrappers for arbitrary calyx programs
that allows these programs to be run on Xilinx FPGAs.
- **Cocotb testbenches** verify the correctness of said AXI wrappers and are
incorporated in Calyx's CI suite. The custom testbench simulates AXI transactions
with dynamically generated AXI wrappers and outputs are compared with expected
baseline results.
- [**fud**](../../research/fud) is a Calyx toolchain driver that pipelines compilation execution stages.
Fud includes a number of pipelines that assist with executing programs on FPGAs
utilizing tools such as [Vitis](https://www.xilinx.com/products/design-tools/vitis.html) and
[XRT](https://www.xilinx.com/products/design-tools/vitis/xrt.html).



[adrian]: https://www.cs.cornell.edu/~asampson/
[rachit]: https://rachit.pl/
