# FIC-486-GAC-2 Cache Module reproduction
Reverse Engineered non standard 256K L2 Cache Module for [FIC 486-GAC-2](https://theretroweb.com/motherboards/s/fic-486-gac-2)

Final product: [front <img src="front render c.jpg" width='300'>](/front%20render.png?raw=true) [back <img src="back render c.jpg" width='300'>](/back%20render.png?raw=true)

-----
Original Cache module:

[front <img src="P1220276c.jpg" width='200'>](/P1220276.JPG?raw=true),[back <img src="P1220275c.jpg" width='200'>](/P1220275.JPG?raw=true) [plugged into FIC 486-GAC-2<img src="P1220281c.jpg" width='200'>](/P1220281.JPG?raw=true)

-----
Vogons [FIC 486-GAC-2 and proprietary cache module](https://www.vogons.org/viewtopic.php?f=46&t=94550) thread:
>majestyk: "FIC sold two different versions with different pinouts (and the same "VLB"-socket). Only the one in the pictures works on a 486-GAC2 and a few other FIC mainboards."

This project was only possible with help provided by majestyk - owner of this very rare Cache module, and RockstarRunner - FIC 486-GAC-2 owner looking for said Cache module. Huge thanks for taking time to capture high resolution pictures and validating progress with measurements.

Kicad diagram and PCB files updated as I go reverse engineering from pictures. Progress:

02/3/2024: Project start. Figuring out how to make edge connector footprint, searching for SOJ-28L footprint.

2/4/2024: Very VIP, only about 50% there at the moment.

2/5/2024: [80% there](/FIC%20486-GAC-2%20cache%20coast%20VIP%2080%25.png), 0 drc errors, 62 violations. Still bad footprints and I havent gotten around to fixing power/ground pins. Whats left is figuring LS244 address buffering mapping, TAG ram address and output pins to edge mapping, WE/CE/OE mapping to edge.

2/6/2024: [90% there](/FIC%20486-GAC-2%20cache%20coast%20VIP%2090%25.png), 0 errors 18 warnings. Just a couple tracks left.

2/8/2024: [95% there](/FIC%20486-GAC-2%20cache%20coast%20VIP%2095%25.png), 0 errors, 7 Warnings. 5 connections missing, 11 guesses and assumptions on U1 U2 and some more on common lines.

2/11/2024: [99% done](/FIC%20486-GAC-2%20cache%20coast%20VIP%2099%25.png), ERC&DRC 0 errors 0 warnings. Footprints should be correct now. Still not 100% sure 64K R2 R4 configuration is a real thing, needs testing.
