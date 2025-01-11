Images for debian trixie

## Key files

**Wallpaper**: wallpaper/wallpaper_1920x1200.svg
* Plain svg file, no unused elements
* This composition is designed to work when *cropped* to any dimensions specified in the requirements. There are visible tangents (solvable if necessary) on the 1280x1024 if it is *scaled and then cropped*.
* Note that lxqt will have a hard-edged appearance compared to the other DEs tested (gnome, xfce, kde). Hypothesized root cause: I believe that this is due to the fact that qt versions prior to 6.7 used basic tiny svg, which does not include the blur effect used in the final composition. 6.7+ implemented select effects that are available in svg but not tiny svg (e.g. blur), so it will have the softer edges in trixie's version of KDE but not lxqt or bookworm's KDE. I have't really dug in, though.


**Log-in screen**: login/login_1920x1200.svg is a log-in screen aligned with the original design proposal
* The same notes under "wallpaper" above apply here


**Boot screen**:
* GRUB 2: bootscreen/grub/grub.png
* Isolinux: bootscreen/isolinux_syslinux/isolinux*.rle
* Syslinux: bootscreen/isolinux_syslinux/syslinux_16bit.png
* Plymouth: bootscreen/plymouth.svg and bootscreen/plymouth2.svg

Note that the two plymouth files are alteratives. Each has four elements of the design: a background, a frill, a highlight, and the debian swirl. Everything except the highlight is intended to be static. The highlight should have varying opacity.

Similarly, there are multiple alternatives for isolinux, given the limited palette -- two based on the same design as syslinux and one that is built from the start for 4bit.

**Installer**: installer/installer_rgb16.png


## SVG files used for development

These contain additional elments not needed for the final design (e.g. palettes). It is easier to edit these and then save-as to the final file.

wallpaper/wallpaper_detailed_1920x1200.svg: Same visible image as wallpaper_1920x1200.svg. This is an Inkscape svg file and includes (1) viewfinders for testing the cropped composition, (2) full palettes for the image, and (3) other composition checks. These are useful for making the design but are not necessary for the final image.

login/login_detailed_1920x1200.svg: Same visible image as login_1920x1200.svg. This is an Inkscape svg file and includes (1) an alternative logo with the swirl stacked above the word "debian." (2) viewfinders for testing the cropped composition, (3) full palettes for the image, and (4) other composition checks. These are useful for making the design but are not necessary for the final image.

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

```bmptoppm isolinux.bmp > boot.ppm
pnmtorle boot.ppm -outfile=boot.rle```
