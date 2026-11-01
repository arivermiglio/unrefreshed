# unrefreshed

https://arivermiglio.github.io/unrefreshed/

tech spec: JavaScript ES6, HTML5, 0 dependencies, 0 generative AI, GPLv3

Dynamic Random-Access Memory (DRAM) stores data as charge inside a capacitor, which will leak the charge and erase the
data if not being constantly recharged by a refresh controller. Digital permanence is therefore a continuous battle against decay.
In Posthuman Gothic (2017), Anya Heise-von der Lippe argues that modern digital spaces are inherently haunted, dissolving the
boundary between the organic and the technological, life and death. Unrefreshed is an open-source (GPLv3) software artwork
that casts memory allocation as Gothic architecture resisting - and ultimately succumbing - to botanical reclamation and data
remanence. It is written in JavaScript with no external dependencies or generative AI.

The simulation runs inside a 36,864-byte heap (Uint8Array) partitioned into three 12,288-byte (128 × 96) depth layers. To
mirror memory hierarchies, the closest layer updates at 60Hz, the middle on a /2 divider (30Hz), and the far layer on a /3 divider
(20Hz). Each byte in the array governs one grid cell on the canvas by splitting the 8-bit integer into two nibbles. The upper four
(0xF0) store the cell’s state: empty (0x0), powered stone (0x1), unpowered stone (0x2), ruin (0x3), soil (0x4), or plant (0x5).
The lower four (0x0F) store the Gothic archetectural form: base, pier, column, capital, arch, flying buttress, tracery, gable, or
spire.

The user clicks and drags to build a structure. The code measures the aspect ratio of the bounding box to create a Gothic
structure: wide spans make cloisters, medium spans make abbeys, narrow spans make bell towers, and square spans make
cathedrals. 5% of the base blocks are permanent (FLAG_KEEP). To remain structurally intact ("powered"), blocks must be
recharged by a simulated Row Address Strobe (RAS) scanline that sweeps at 60Hz. Because it can only recharge 260 bytes per
pass, the current exhausts itself half-way if there are many structures on the screen. Bytes that miss the current "lose their
charge."
Once a cell loses power, briars climb up the walls (using a double-buffered growth array to ensure they don’t jump rows). When
briar coverage on a cell exceeds 45 percent, crimson roots appear, making the structure brittle. Every frame verifies that each
cell has a path to the earth. Crumbling cells tumble down while releasing shimmering ash flakes,(0x0) until only a ruin remains
(at zero refresh cost).


In physical RAM, erased capacitors retain imprints of past charges. Using a parallel remanence buffer (ghostPart), when a cell
crumbles and frees its byte to 0x0, the address retains a ghostly wireframe, which, if the user draws over, will cause the new
structure to have only 68% of initial strength, facilitating a new crumbling along the haunted lines of the old.
