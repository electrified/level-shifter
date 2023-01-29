## Board to interface 3.3v FPGA board with RC2014

## BOM

5x SN74LVCC3245ADW

LD1117S33TR

100nF 0805 capacitors

10μF 0805 capacitors


OE low = enable
dir rc ->fpga

objcopy -Iihex -Obinary nascom32k_hexloadr.hex out.bin

sigrok-cli --driver saleae-logic16 --config samplerate=20Mhz --channels 0=D0,1=D1,2=D2,3=D3,4=D4,5=D5,6=D6,7=D7,9=RD,10=WR,11=MREQ,13=M1 --samples 1M --output-file z80-fpga

Silkscreen blunders

On the fpga connector, silkscreen for M1 and RD should be swapped

## License

Copyright Ed Brindley 2020.

This source describes Open Hardware and is licensed under the CERN-OHL-P v2
You may redistribute and modify this documentation and make products using it under the terms of the CERN-OHL-P v2 (https:/cern.ch/cern-ohl). This documentation is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. Please see the CERN-OHL-P v2 for applicable conditions