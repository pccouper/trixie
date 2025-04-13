## Key files

* GRUB 2: bootscreen/grub/grub.png
* Isolinux: bootscreen/isolinux_syslinux/isolinux*.rle
* Syslinux: bootscreen/isolinux_syslinux/syslinux_16bit.png
* Plymouth: bootscreen/plymouth.svg and bootscreen/plymouth2.svg
* Plymouth with script: bootscreen/plymouth/emerald/*

Note that the two plymouth files are alteratives. Each has five elements of the design: a background, a frill, a highlight, password swatches, and the debian swirl. Everything except the highlight is intended to be static. The highlight should have varying opacity.

The "emerald" folder uses the existing Emerald plymouth script and folder structure, badly patched over for ceratopsian v2 plymouth layout. I made minor changes to the Emerald script for alignment and sizing of the assets. The existing Emerald script and the final versions were added in separate commits if you want to see the diff.

Similarly, there are multiple alternatives for isolinux, given the limited palette -- two based on the same design as syslinux and one that is built from the start for 4bit.

## svg files used for development

grub.svg: no additional elements relative to grub.png, but saved for editing purposes. Similar for isolinux.svg and syslinux.svg.

## export process to ensure that elements align

Getting the frill and glow to line up can be difficult. The following steps will get the elements to align, but still allow for resizing in the plymouth script.

1. In inkscape, hide all layers except for the frill layer. 
2. Export the entire canvas as a png, using the least compression. This will include a lot of white space. We'll fix that later,
3. Repeat steps 1 and 2 for the glow layer.
4. Open both the frill layer and the glow layer in gimp. They should be two separate layers for the same file.
5. Crop the canvas (not the individual layers) to include both elements, with minimal white space. Crop it to a square format (or close) so that the scale calculations in ceratopsian.script work correctly. The exact size doesn't matter as much as being close to square.
6. Export each layer separately back to png files with maximum compression.

Other elements can be exported directly as png files from inkscape.
