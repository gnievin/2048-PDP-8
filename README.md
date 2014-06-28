"2048 for the PDP-8"

A small  clone of the web-based game by Gabriele Cirulli:

https://github.com/gabrielecirulli/2048


This version is in PDP-8 assembly language, and runs with no OS.

Load the BIN papertape format file into memory, and start
at address 200 octal.  

This code was written and tested using my Spare Time Gizmos SBC-6120,
a PDP-8E compatible system using an HD6120 ("PDP-8 on a chip") CPU.

I believe this should run on any PDP-8.

I've since verified that it runs in the SIMH PDP-8 simulator 

http://simh.trailing-edge.com/

To run in SIMH: (on Debian-based Linux like Ubuntu or Mint)

apt-get install simh

$ pdp8

sim> LOAD 2048.bin

sim> GO 0200


To get a "period feel", up/down/left/right key assignments 
are taken from the Lear Siegler ADM3A, and are familiar to users of vi

https://en.wikipedia.org/wiki/File:KB_Terminal_ADM3A.svg

Fully compatible with Teletype ASR-33

Licensing info:

This code is placed in the public domain by Garrett Nievin

The functions "GetRand" and "Muy" are by Steve Gibson
from his public domain program "Deep Thought"

https://www.grc.com/pdp-8/deepthought-sbc.htm

The function "XDECPRT" is based on document "DIGITAL-8-22-U-SYM",
Unsigned Decimal Print, dated June 7, 1965

Modified by me to space-replace leading insignificant zeros

Original code is all uppercase, my edits are lowercase

The function "xudprnt" is taken from document "DIGITAL-8-24-U-Sym",
Unsigned Decimal Print, Double Precision, dated January 19, 1966

both documents available from:

http://bitsavers.informatik.uni-stuttgart.de/www.computer.museum.uq.edu.au/pdf

The binary produced by this program is tested with 
Steve Gibson's OS/8 Multiboot Sector

https://www.grc.com/pdp-8/os8-multiboot.htm

Fair warning - this was my "Hello world" program in PDP-8 assembly,
after only recently building my SBC-6120.  Learning as I went,
some sections are not pretty, elegant, or idiomatic.
This program was written without reference to any other program,
except for examining the original code to ascertain the probability
of a random "2" or "4" cell being added.


Toolchain used:

Assembler:

"palbart" cross assembler v 2.10 on Linux

http://www.pdp8online.com/ftp/software/palbart/palbart.c

(not the relatively old 2.4 version that is in the Debian repo)

(may or may not assemble with 2.4)

Terminal/Loader during dev:

Modified version of PySerial example "Miniterm" terminal program, mods
include adding a PDP-8 BIN punchtape loader which generates BTS-6120
memory deposit sequences so I didn't need to use the BTS-6120 BIN loader

http://pyserial.sourceforge.net/examples.html

Terminal:

Vince Briel's PockeTerm

http://www.brielcomputers.com/wordpress/?cat=25

Execute/debug:

Spare Time Gizmos SBC-6120/FP-6120, front-panel switches and blinkenlights

http://sparetimegizmos.com/Hardware/SBC6120-1.htm

http://sparetimegizmos.com/Hardware/SBC6120_Front_Panel.htm
