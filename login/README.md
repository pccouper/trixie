## Key files

**Log-in screen**: login/login_1920x1200.svg and login/login_21x9 are log-in screens.
* Plain svg file, no unused elements
* These use some of the same core elements as the wallpaper, but with harder edges and higher contrast. It is intended to transition to the more muted wallpaper.
* The 1920x1200 composition is designed to work when *cropped* to any dimensions specified in the requirements. There are visible tangents (solvable if necessary) on the 1280x1024 if it is *scaled and then cropped*.
* The 21x9 composition has not been tested for cropping

**Note:** This does not have the logo turned on. This is so that the element does not interfere with any elements from the individual DE's lock/login screen (e.g. in KDE, the clock on lock screen and the swirl and password field in the login screen). The logo element can be turned back on through the _detailed files below. 

## Used in development only

login/login_detailed_1920x1200.svg: Same visible image as login_1920x1200.svg. This is an Inkscape svg file and includes (1) viewfinders for testing the cropped composition, (2) full palettes for the image, (3) other composition checks, and (4) the logo. These are useful for making the design but are not necessary for the final image.

login/login_detailed_21x9.svg is similar.
