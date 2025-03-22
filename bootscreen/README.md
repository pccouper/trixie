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
