```
                              __   _ __      _______  _____            __
                             / /  (_) /____ / __/ _ \/ ___/__ ________/ /
                            / /__/ / __/ -_)\ \/ // / /__/ _ `/ __/ _  /
                           /____/_/\__/\__/___/____/\___/\_,_/_/  \_,_/

                               Copyright 2017-2020 / EnjoyDigital
                               Copyright 2017-2018 / LambdaConcept

                            A small footprint and configurable SDCard core
                                     powered by LiteX & Migen
```

[![](https://travis-ci.com/enjoy-digital/litesdcard.svg?branch=master)](https://travis-ci.com/enjoy-digital/litesdcard) ![License](https://img.shields.io/badge/License-BSD%202--Clause-orange.svg)


[> Intro
--------
LiteSDCard is a small footprint and configurable SDCard core.

LiteSDCard is part of LiteX libraries whose aims are to lower entry level of
complex FPGA cores by providing simple, elegant and efficient implementations
of components used in today's SoC such as Ethernet, SATA, PCIe, SDRAM Controller...

Using Migen to describe the HDL allows the core to be highly and easily configurable.

LiteSDCard can be used as LiteX library or can be integrated with your standard
design flow by generating the verilog rtl that you will use as a standard core.

[> Features
-----------
PHY:
  - Xilinx Spartan 6 and 7-Series FPGA
  - optional clock feedback (UHS-I)

Core:
  - Command & Data CRC inserters/checkers
  - Single and multiple blocks write/read
  - Errors detection and reporting
  - Dynamically configurable clock speed

Frontend:
  - Synthetizable BIST
  - 32 <--> 8 bits stream converters

[> Performances
---------------
SD0: Good RAM 8GB (cheap SD Card)
SD1: SanDisk Ultra 32GB
SD2: SanDisk Extreme 128GB

W/R(MB/s) performance vs SD frequency:

| SDCard | 20MHz | 40MHz | 75MHz | 100MHz | 125MHz |
|--------|-------|-------|-------|--------|--------|
|   SD0  |  4/9  | 6/18  |  7/33 |   7/44 |  7/56  |
|   SD1  |  6/9  | 9/18  | 12/33 |  14/44 | 15/56  |
|   SD2  |  9/9  | 18/18 | 33/33 |  43/44 | 54/55  |

[> Possible improvements
------------------------
- add standardized interfaces (AXI, Avalon-ST)
- add vendor agnostic phy for low speeds
- add support for Altera FPGAs.
- add support for Lattice FPGAs.
- add Zynq Linux drivers.
- ... See below Support and consulting :)

If you want to support these features, please contact us.

[> Getting started
------------------
1. Install Python 3.6+ and FPGA vendor's development tools.
2. Install Migen/LiteX and the LiteX's cores:

```sh
$ wget https://raw.githubusercontent.com/enjoy-digital/litex/master/litex_setup.py
$ chmod +x litex_setup.py
$ ./litex_setup.py init install --user (--user to install to user directory)
```
  Later, if you need to update all repositories:
```sh
$ ./litex_setup.py update
```

3. Build and load Nexys4DDR test design:
  go to examples
```sh
$ ./nexys4ddr.py cpu
$ ./nexys4ddr.py cpu
```
4. Connect to the board:
```sh
$ litex_term <your_serial_port>
```

5. Test:
```sh
$  sdclk 10
$  sdinit
$  sdtest 8
```

[> License
----------
LiteSDCard is released under the very permissive two-clause BSD license. Under the
terms of this license, you are authorized to use LiteSDCard for closed-source
proprietary designs.
Even though we do not require you to do so, those things are awesome, so please
do them if possible:
 - tell us that you are using LiteSDCard
 - cite LiteSDCard in publications related to research it has helped
 - send us feedback and suggestions for improvements
 - send us bug reports when something goes wrong
 - send us the modifications and improvements you have done to LiteSDCard.

[> Support and consulting
-------------------------
We love open-source hardware and like sharing our designs with others.

LiteSDCard is developed and maintained by EnjoyDigital & LambdaConcept.

If you would like to know more about LiteSDCard or if you are already a happy user
and would like to extend it for your needs, EnjoyDigital can provide standard
commercial support as well as consulting services.

So feel free to contact us, we'd love to work with you! (and eventually shorten
the list of the possible improvements :)

[> Contact
----------
E-mail:
florent [AT] enjoy-digital.fr
po [AT] lambdaconcept.com
ramtin [AT] lambdaconcept.com
