Images for debian trixie

## Key files

See more detailed readmes in the folders.

**Wallpaper**: 
* wallpaper/wallpaper_1920x1200.svg, 
* wallpaper/wallpaper_small_logo_1920x1200.svg, 
* wallpaper/wallpaper_21x9.svg

**Log-in screen**: 
* login/login_1920x1200.svg 
* login/login_21x9.svg

**Boot screen**:
* GRUB 2: bootscreen/grub/grub.png
* Isolinux: bootscreen/isolinux_syslinux/isolinux*.rle
* Syslinux: bootscreen/isolinux_syslinux/syslinux_16bit.png
* Plymouth: bootscreen/plymouth.svg and bootscreen/plymouth2.svg
* Plymouth with script: bootscreen/plymouth/emerald/*

Note that the two plymouth files are alteratives. Each has five elements of the design: a background, a frill, a highlight, password swatches, and the debian swirl. Everything except the highlight is intended to be static. The highlight should have varying opacity.

The "emerald" folder uses the existing Emerald plymouth script and folder structure, badly patched over for ceratopsian v2 plymouth layout. I made minor changes to the Emerald script for alignment and sizing of the assets. The existing Emerald script and the final versions were added in separate commits if you want to see the diff.

Similarly, there are multiple alternatives for isolinux, given the limited palette -- two based on the same design as syslinux and one that is built from the start for 4bit.

**Installer**: 
* installer/installer_rgb16.png


## SVG files used for development

Several folders include Inkscape svg files (not plain svg) with the additional tag _detailed. These contain additional elements not needed for the final design (e.g. palettes). It is easier to edit these and then save-as to the final file.

grub.svg: no additional elements relative to grub.png, but saved for editing purposes. Similar for isolinux.svg and syslinux.svg.


## components: files used only in developing the composition

These are not required for the final images but may be useful for future work using the same palette and format.

blues_tints.svg and blues_shades.svg: The palette used in the final composition.

test.svg: File to test what filters are available in gnome vs. xfce vs. kde vs. lxqt

viewfinders.svg: Used to check whether the composition works when cropped

## debianstd: templates, used only in developing the composition

These are not required for the final images but may be useful for future work using the same format.


## working notes

Converting bmp to rle using netpbm: 

First gimp -> indexed color with 15 colors

```bmptoppm isolinux.bmp > boot.ppm```

```pnmtorle boot.ppm -outfile=boot.rle```
