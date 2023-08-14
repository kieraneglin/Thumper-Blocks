# ERCF Thumper Blocks (beta)

**Secure Grip for Seamless Printing**

## NOTE: This is a work-in-progress.

The design has performed very well so far, but it's still going to change as we test and iterate. This project is based off the mature [Triple-Decky][triple-decky] design but some significant changes have been made which may affect the overall performance. Please keep this in mind if you decide to use Thumper.

## Credit:

This is based heavily off the fantastic [Triple-Decky][triple-decky] project. I've made some improvements based on my own experience and needs, but the core design can be traced back to the original. Thumper Blocks would not exist without the work of gneu42 or any of the testers/contributors to that project.

## What is it?

Thumper Blocks are 3-level filament blocks for the ERCF. Their job is threefold:

1. Stop filament from moving in or out of the block when not in use
2. Give solid grip to the gear motor when loading/unloading filament
3. Provide a low-friction path for filament to move through when the main extruder has taken over

## ERCF Requirements

- [Sturdy Bunny][sturdy] ERCF platform
- [Springy][springy] selector cart
- A buffer such as [piKa][pika] is very strongly recommended. This isn't just for Thumper - a buffer will improve your load/unload reliability with any filament block
- [Happy Hare][happy-hare] is very strongly recommended. It's currently in closed beta, but it allows the use of a 3-position servo which is required for Thumper

## Differences compared to Triple-Decky

- Shaves 1.75mm off the width of each block
  - This allows the blocks to fit existing hardware without modification or omitting a filament block
  - If you're already set up for Triple-Decky, it reclaims 10.5mm for every 6 blocks. With this, you can add things like a dedicated bypass block
- Uses an M4 nut for the filament brake instead of a printed part (low friction) or a grub screw (uncommon part)
- Removes the need for supports on all parts except the tophat for less post-processing
- Allows for the use of 1 pair of magnets
- Lets you use N35 magnets instead of N52, but stronger is still better if you have them
- Adds features to help with alignment on the 2020 extrusion
- Streamlines filament path for both initial feeding and endless-spool mode
- Updates block tolerances for easier assembly
- Improves tolerances on the latch mechanism

## What hasn't changed

- Triple-Decky's filament tags will fit in Thumper
- Removes the need for standalone bearing blocks by integrating bearings into filament blocks
- The general look, feel, and assembly is very similar to Triple-Decky

## BOM

**Hardware**

This is per-block unless otherwise noted. I've added (unchanged) to parts that are the same as Triple-Decky.

- 1x ECAS fitting (unchanged)
- 1x M3x12mm SHCS for latch (unchanged)
- 1x BMG driven gear and idler assembly (unchanged)
- 2x 6x3mm magnets (unchanged)
- 1x M3x8mm SHCS and 1x M3 T-nut for fastening to extrusion (unchanged)
- 1x M4 nut for filament brake

Additionally, every 3rd block will need 1x MR85ZZ bearing (unchanged)

**Printed Parts**

- 1x [springy] servo arm for your servo of choice
- 1x every file in the STL folder for each block you want to make
  - NOTE: files are made to be printed in their default orientation and without supports

## Assembly

These instructions are going to be pretty sparse until something closer to the final design is reached. It's not a difficult assembly, but you can refer to a combination of Triple-Decky and the STEP file to fill in any gaps.

**Filament Path**

- Insert the ECAS fitting into the front of the block
- Insert 1x magnet in the hole under the ECAS fitting
  - NOTE: it should oppose the magnet in the base
  - NOTE: there is a slot behind the magnet to help remove it if need be
- Optionally insert filament tag

**Base**

- Insert 1x magnet in the hole in the front of the base
  - NOTE: it should oppose the magnet in the filament path
  - NOTE: there is a hole under the magnet to help remove it if need be
- Press-fit 1x M4 nut into the hole in the back of the base
  - It can help to use an M4 machine screw to help align the nut and press it in
- Attach the latch with 1x M3x12mm SHCS
  - NOTE: the latch should be able to move freely but not be loose
  - NOTE: seriously, use a 12mm machine screw. Using a 6 or 8 will result in the latch breaking its mount
- Push 1x M3x8mm SHCS through the hole beside the M4 nut and attach an M3 T-nut on the other side
- For every 3rd block, insert 1x MR85ZZ bearing into the side hole near where the driven extruder gear will sit
- Optionally insert filament tag

**Tophat**

- Remove support material from hinge and idler path
- Insert the BMG idler gear with bearings into the tophat
- Insert idler rod through holes in tophat and idler assembly
  - NOTE: ensure the flat side of the tophat is on a hard surface and tap the rod in with a hammer

**Final Assembly**

- Place (but don't tighten) the driven BMG gear onto the gear motor shaft of the ERCF
- Slide the base onto the extrusion and slide along the gear-motor shaft until it's in position
  - NOTE: there are features in the base to help align with the extrusion. Some light backward or forward pressure will help ensure squareness
  - NOTE: if your selector cart hits the base, you may need to adjust the position of the base using the _other_ alignment feature
  - NOTE: every 3rd block should have an MR85ZZ bearing in the base
- Tighten the M3x8mm SHCS to secure the base to the extrusion
- Insert the filament path into the base
- Align the driven BMG gear with the filament path and tighten the gear onto the gear motor shaft
- Insert the tophat into the filament path
- Close the latch
- Repeat until satisfied

![Assembled Block](images/full-block.jpg)

[triple-decky]: https://github.com/gneu42/Triple-Decky
[springy]: https://github.com/moggieuk/ERCF-Springy
[sturdy]: https://github.com/sneakytreesnake/SturdyBunnyProject
[pika]: https://github.com/geoffrey-young/pika-filament-buffer
[happy-hare]: https://github.com/moggieuk/Happy-Hare
