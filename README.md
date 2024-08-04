A workflow for laser cutting Eurorack synthesiser front panels from panel designs made in KiCad

Key points:
- Our panel files are designed in KiCad using the footprints from the 4ms Faceplate library
- We use a Trotec laser cutter
- The basic workflow is: Plot from KiCad, colourise and set stroke width in Inkscape, do final print to Trotec's RayJet Manager software from Illustrator (can't print directly from Inkscape)

# In KiCad

Open your panel file - EXAMPLE?
Go to `Plot -> SVG`, choose the follwing options:
- Include layers -> F.Silkscreen
- Plot on all layers -> Edge.Cuts
- Drill Marks -> actual size
- Untick "Plot Drawing Sheet"

see `KicadExportSettings.png` for full settings (embed here)

Note: output won't downsize to board size but that's ok

# In Inkscape

Open the file you exported from KiCad
Green lines will represent our cuts
Red lines will represent out engraving - we won't raster engrave them, but just cut with less power
(We avoid black lines because they rasterise by default in Trotec's software - confusing!!)

## Cuts (Holes)

At first the holes will not be visible, but Select All will let you see them
Once you see them, deselect everything then and select just one hole
Then choose Edit -> Select Same -> Fill & Stroke (all holes should now be selected)
Shift-select the board edge
Shift-select the oval mounting holes (if not already selected)
In Fill & Stroke
	- remove fill (x)
	- add Stroke Paint, R 0 G 255 B 0 (pure green)
	- in Stroke Style choose width of 0.01mm (this will make the lines hard to see unless we're zoomed in, but that's the way it is!)

## Engravings (Text)

Click on an item of text
All text will be grouped, so right click and select ungroup
Click on an item of text again
Watch out, there are also text boxes on top of the text - these may need to be deleted first
Then choose Edit -> Select Same -> Stroke (all text should now be selected)
In Fill & Stroke
	- remove fill (x) - although there shouldn't be any
	- add Stroke Paint of R 255 G 0 B 0 (pure red) - it might already be this way
	- in Stroke Style choose width of 0.01mm (this will make the lines hard to see unless we're zoomed in, but that's the way it is!)


Select all, ungroup everything so there are no layers (does this help?)
Save the file



