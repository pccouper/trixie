## Key files

* GRUB 2: bootscreen/grub/grub.png
* Isolinux: bootscreen/isolinux_syslinux/isolinux*.rle
* Syslinux: bootscreen/isolinux_syslinux/syslinux_16bit.png
* Plymouth: bootscreen/plymouth.svg
* Plymouth with script: bootscreen/plymouth/ceratopsian/*

The plymouth theme has five elements: a background, a frill, a glow, password swatches, and the debian logo. Everything except the glow is intended to be static. The glow should have varying opacity.

The "ceratopsian" folder uses the existing Emerald plymouth script and folder structure, patched for the ceratopsian plymouth layout. I made minor changes to the Emerald script for alignment and sizing of the assets. The existing Emerald script and the final versions were added in separate commits if you want to see the diff.

Similarly, there are multiple alternatives for the isolinux rle file, given the limited palette. Two are based on the same design as syslinux (assuming 4bit indexed color is possible, either indexed full-color or indexed greyscale). One is built from the start for 4bit (assuming indexed color is not allowed). Which option should we use? Whatever works technically. The indexed color option is preferable but it might not be technically feasible.

## svg files used for development

grub.svg: no additional elements relative to grub.png, but saved for editing purposes. Similar for isolinux.svg, syslinux.svg, and plymouth.svg.

## export process to ensure that plymouth elements align

Getting the frill and glow to line up can be difficult. The following steps will get the elements to align, but still allow for resizing in the plymouth script.

1. In inkscape, hide all layers except for the frill layer. 
2. Export the entire canvas as a png, using the least compression. This will include a lot of white space. We'll fix that later,
3. Repeat steps 1 and 2 for the glow layer.
4. Open both the frill layer and the glow layer in gimp. They should be two separate layers for the same file.
5. Crop the canvas (not the individual layers) to include both elements, with minimal white space. Crop it to a square format (or close) so that the scale calculations in ceratopsian.script work correctly. The exact size doesn't matter as much as being close to square.
6. Export each layer separately back to png files with maximum compression.

Other elements can be exported directly as png files from inkscape.


## working notes

Converting bmp to rle using netpbm: 

First gimp -> indexed color with 15 colors

```bmptoppm isolinux.bmp > boot.ppm```

```pnmtorle boot.ppm -outfile=boot.rle```
