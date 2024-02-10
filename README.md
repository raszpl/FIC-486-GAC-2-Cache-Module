# FIC-486-GAC2-Cache-Module
Reverse Engineering non standard 256K L2 Cache Module for FIC 486-GAC2 (https://theretroweb.com/motherboards/s/fic-486-gac-2)
[<img src="P1220281c.jpg">](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/P1220281.JPG?raw=true)
[<img src="P1220276c.jpg">](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/P1220276.JPG?raw=true)
[<img src="P1220275c.jpg">](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/P1220275.JPG?raw=true)

Related boards with classic L2 Cache DIP SRAM sockets FIC 486-GAC-V, FIC 486-GIO-VP, FIC 486-GIO-VT, FIC 486-GIO-VT2, FIC 486-GT, FIC 486-GVT, FIC 486-GVT-2.

majestyk: "FIC sold two different versions with different pinouts (and the same "VLB"-socket). Only the one in the pictures works on a 486-GAC2 and a few other FIC mainboards."

This project was only possible with help provided by majestyk - owner of this very rare Cache module, and RockstarRunner - FIC 486-GAC2 owner looking for said Cache module. Huge thanks for taking time to capture high resolution pictures and validating progress with measurements.

Kicad diagram and PCB files updated as I go reverse engineering from pictures. Progress:

02/3/2024: Project start. Figuring out how to make edge connector footprint, searching for SOJ-28L footprint.

2/4/2024: Very VIP, only about 50% there at the moment.

2/5/2024: [80% there](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/FIC%20486-GAC-2%20cache%20coast%20VIP%2080%25.png), 0 drc errors, 62 violations. Still bad footprints and I havent gotten around to fixing power/ground pins. Whats left is figuring LS244 address buffering mapping, TAG ram address and output pins to edge mapping, WE/CE/OE mapping to edge.

2/6/2024: [90% there](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/FIC%20486-GAC-2%20cache%20coast%20VIP%2090%25.png), 0 errors 18 warnings. Just a couple tracks left.

2/8/2024: [95% there](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/FIC%20486-GAC-2%20cache%20coast%20VIP%2095%25.png), 0 errors, 7 Warnings. 5 connections missing, 11 guesses and assumptions on U1 U2 and some more on common lines.

2/8/2024: [99% done](https://github.com/raszpl/FIC-486-GAC2-Cache-Module/blob/main/FIC%20486-GAC-2%20cache%20coast%20VIP%2099%25.png), ERC&DRC 0 errors 0 warnings. Footprints should be correct now. Still needs some silkscreen work. Still not 100% sure 64K R2 R4 configuration is a real thing, needs testing.
