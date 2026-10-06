# GHDL installation guide
Hello, tutor here.
I'm writing this guide because I was told that every year students have problems with VHDL and waveform generation.
> Note: as this guide is new, I may not have accounted for all problems. In case you have any, email me at [francesco.bogni@studenti.unitn.it](francesco.bogni@studenti.unitn.it)

## What is GHDL?
GHDL is an open-source tool used to analyse, elaborate and run simulations on your VHDL code. It is technically **not** a compiler as it is not transforming your code into instructions, it is transorming it into eventually implementable hardware.
When running testbenches you may want to look at the resulting waveform, i.e. the simulated value of a **signal** as time passes.

## How to install ghdl
### Windows
Go to the official [releases page](https://github.com/ghdl/ghdl/releases/tag/v6.0.0).
As of today, version 6.0.0 is the latest-stable version. Download the `mccode` standalone. Unzip it in a known folder, say `C:\ghdl`. For confirmation check that `ghdl.exe` is present in `C:\ghdl\bin`. Then add it to the ENVIRONMENT varaibles. 
Restart your terminal if you had it open and check installation using `ghdl --version`. 
### Linux
#### Ubuntu / Debian
`sudo apt update && sudo apt install ghdl`.

Then verify using `ghdl --version`.
#### Arch
I'm pretty sure you don't need this guide
### Mac
`brew install ghdl`

Then verify using `ghdl --version`.
> I have never used any macOS machine; if there are any problems refer to the mail above.

## Use on VScode
#### Common commands
For analysis of VHDL code along with a testbench run:
```
ghdl -a my_design.vhd my_tb.vhd
```
This allows GHDL to verify your code and allow elaboration.

---

Then elaborate:
```
ghdl -e my_tb
```
where `my_tb` is the entity name of the testbench. 
It allows GHDL to transform code into a runnable tree, starting from the top entity.

---
Finally, run
```
ghdl -r my_tb --vcd=my_chosen_name.vcd
```
At this point GHDL should generate the waveform.
You can click on it and view it on the editor. VScode will prompt you to download an extension to view it.
If that doesn't happen you can download a very common one called [WaveTrace](https://marketplace.visualstudio.com/items?itemName=wavetrace.wavetrace).

---

Have fun!

