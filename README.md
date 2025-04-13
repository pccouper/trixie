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
* Plymouth: bootscreen/plymouth.svg
* Plymouth with script: bootscreen/plymouth/certopsian/*


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


