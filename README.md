# FIC-486-GAC-2 Cache Module reproduction
[<img src="front render c.jpg" width='300'>](/front%20render.png?raw=true) [<img src="back render c.jpg" width='300'>](/back%20render.png?raw=true)

Reverse Engineered non standard 256K L2 Cache Module for use in:

- AT&T GLOBALYST 510 = NCR 3228 = [FIC 486-GAC-2](https://theretroweb.com/motherboards/s/fic-486-gac-2)
- AT&T GLOBALYST 515 = NCR 3232 = [FIC 486-GAC-2](https://theretroweb.com/motherboards/s/fic-486-gac-2)

Potentially also:
- AT&T Globalyst 520 = NCR 3238 = FIC 486-PAK-3 needs confirmation
- NCR 3231 ?
- AT&T Globalyst 525 = NCR 3253 ?

Incompatible despite also using VLB slot for Cache:
- [AT&T Globalyst 550 = NCR 3246](https://theretroweb.com/motherboards/s/atandt,-inc.-at-and-t,-inc.-globalyst-550-c) uses [517-0002811](/not%20compatible%20proprietary%20vlb%20cache%20modules/ATT-Globalyst_550_575.jpg)
- AT&T Globalyst 575 = NCR 3347 uses [517-0002811](/not%20compatible%20proprietary%20vlb%20cache%20modules/ATT-Globalyst_550_575.jpg)
- [HP Vectra VE 4](https://theretroweb.com/motherboards/s/hp-vectra-ve-4-xxx-d3501) uses 256KB D2465A/IDT 7MP6190 [front](/not%20compatible%20proprietary%20vlb%20cache%20modules/HP%20Vectra%20VE%204%20256%20KB%20Cache%20D2465A.webp?raw=true) [back](/not%20compatible%20proprietary%20vlb%20cache%20modules/HP%20Vectra%20VE%204%20256%20KB%20Cache%20D2465A%20back.webp?raw=true)
- [Siemens Nixdorf FD200 D882](https://theretroweb.com/motherboards/s/siemens-nixdorf-system-board-d882) uses 256KB cym9252pb [front](/not%20compatible%20proprietary%20vlb%20cache%20modules/Siemens%20Nixdorf%20FD200%20D882%20cym9252pb.JPG?raw=true) [back](/not%20compatible%20proprietary%20vlb%20cache%20modules/Siemens%20Nixdorf%20FD200%20D882%20cym9252pb%20back.JPG?raw=true) and unknown 128KB one.

-----
Original DOC: 13630 ASSY: 008-0078204 A Cache module:

rev 2.2 [front <img src="P1220276c.jpg" width='200'>](/P1220276.JPG?raw=true), [back <img src="P1220275c.jpg" width='200'>](/P1220275.JPG?raw=true), earlier rev 2 [front <img src="DOC13630c.jpg" width='200'>](/DOC13630.jpg?raw=true)

[plugged into FIC 486-GAC-2<img src="P1220281c.jpg" width='200'>](/P1220281.JPG?raw=true)

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

2/11/2024: [99% done](/FIC%20486-GAC-2%20cache%20coast%20VIP%2099%25.png), ERC&DRC 0 errors 0 warnings. Footprints should be correct now. Gerbers sent for manufacturing.
