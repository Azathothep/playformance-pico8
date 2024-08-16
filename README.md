# PICO-8 Playformance particle system
A particule simulation system on pico8 for a playformance held in 2024

This is a pico8 program designed for a playformance I originally gave in lyon in 2024 (more info on www.felix-belthoise.com)

Instructions :

-> left mouse button = add an electron

-> right mouse button = add a proton

-> middle mouse button = add a muon

-> when an electron and a proton are fusing, they create a neutron

-> when a muon collides with a neutron, it breaks back into an electron and a proton

-> use x to clear the screen and reset the cartridge memory

----

The idea was to make a simple particle simulation system inspired by elementary particles interactions: protons and electrons attracting and repulsing each other (as defined by coulomb's law), particles fusion and fission.

I chose to use pico8 because of its simple design (this is supposed to be projected to a large public, so you don't want to have a 20-windows software that would be difficult to understand for non-programers), and show that even a very limited engine such as this one can still create beautiful evolving systems on screen.

The main challenge was, well, its limitations.

Pico8 has only 64kb of RAM, and keeping track of multiple moving particles influencing each other quickly impacted performances.

At first, with a non-optimized system, I couldn't render more than 30 particles without the program heavily slowing down. After some rework, it can now render up to 500.

To accelerate execution, i decided to go for a structure- of-arrays data layout and reduce lots of unnecessary divisions. i also used approximations for some calculations (for example, instead of checking the exact distance between two particles, I only check the difference between their coordinates).

Don't hesitate to take a look at the code!
