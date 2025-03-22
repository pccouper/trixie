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
* Plymouth: bootscreen/plymouth*.svg
* Plymouth with script: bootscreen/plymouth/emerald*

The three plymouth*.svg files are alteratives. 
* bootscreen/plymouth.svg and bootscreen/plymouth2.svg have five elements of the design: a background, a frill, a highlight, password swatches, and the debian swirl. Everything except the highlight is intended to be static. The highlight should have varying opacity.
* bootscreen/plymouth3.svg uses a similar design to the grub file. There are six elements: a background, three frills, password swatches, and the logo (with version). The opacity is constant, but the frills rotate. Note that the layout in the svg file is not the layout that you will see in practice; the _preview file shows an approximate layout. *This is currently less polished. The contrasts are too harsh, and it has pretty bad banding. These are fixable if we decide that this concept works.* It is also pretty simple to add varying opacity back into the design.

The "emerald2" folder uses the existing Emerald plymouth script and folder structure, badly patched over for ceratopsian v2 plymouth layout. I made minor changes to the Emerald script for alignment and sizing of the assets. The existing Emerald script and the final versions were added in separate commits if you want to see the diff. This desperately needs a clean-up.

The "emerald3" folder is similar, except based on the assets in bootscreen/plymouth3.svg.

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
