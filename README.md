# unrefreshed

https://arivermiglio.github.io/unrefreshed/

tech spec: JavaScript ES6, HTML5, 0 dependencies, 0 generative AI, GPLv3

Dynamic Random-Access Memory (DRAM) stores each bit as a charge in a capacitor. Left alone, that charge leaks to ground, taking the data with it. Because DRAM must be sustained by a refresh controller that recharges it many times a second, digital permanence is a continuous battle against decay. When memory is lost or erased, residual charges, garbage values, and dangling pointers linger in the address space.

In Posthuman Gothic, Anya Heise-von der Lippe argues that modern digital spaces are inherently haunted, dissolving the boundaries between the organic and the technological, life and death. Unrefreshed is an open-source (GPLv3) JavaScript artwork that visualizes this haunted hardware reality, casting it as Gothic architecture resisting - and succumbing to - nature.

Built without external libraries or generative AI, the work runs inside a 36,864-byte Uint8Array split into three 12-kilobyte depth layers whose update frequencies mirror memory hierarchies. Each byte controls one cell: four bits store state (empty, powered stone, unpowered stone, ruin, soil, or plant) and four store architectural form (base, pier, column, capital, arch, flying buttress, tracery, gable, or spire).

Dragging across a hill builds a cloister, abbey, bell tower, or cathedral. To stay intact, blocks must be recharged by a Row Address Strobe (RAS) scanline. When the user builds more than the 260 bytes the scanline can feed, unrefreshed structures decay: marble turns dark and brittle, and briars climb from the soil up, eroding the structure into ash. Only a ruin remains alongside a flickering ghost of the dead structure, which weakens any new stone built over its haunted bytes. 

In this presentation, I demonstrate Unrefreshed, explain its mechanics and metaphor, and examine how software design changes when we treat decay as part of nature.
