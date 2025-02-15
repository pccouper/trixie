Images for debian trixie

## Key files

**Wallpaper**: wallpaper/wallpaper_1920x1200.svg and wallpaper/wallpaper_small_logo_1920x1200.svg
* Plain svg file, no unused elements, two different logo sizes
* This composition is designed to work when *cropped* to any dimensions specified in the requirements. There are visible tangents (solvable if necessary) on the 1280x1024 if it is *scaled and then cropped*.
* *For the additional 21x9 format:* This was added after the initial design was completed. The "small logo" variant is a step in that direction. While there are no problematic tangents, the composition does not work as well with that width. If we expect a lot of users with that format, I'll tweak the design to accommodate it. 
* Note that lxqt will have a hard-edged appearance compared to the other DEs tested (gnome, xfce, kde). Hypothesized root cause: I believe that this is due to the fact that qt versions prior to 6.7 used basic tiny svg, which does not include the blur effect used in the final composition. 6.7+ implemented select effects that are available in svg but not tiny svg (e.g. blur), so it will have the softer edges in trixie's version of KDE but not lxqt or bookworm's KDE. I have't really dug in, though.


**Log-in screen**: login/login_1920x1200.svg is a log-in screen aligned with the original design proposal
* The same notes under "wallpaper" above apply here


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
