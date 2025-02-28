# gimp-colortemp
(not to be confused with [gimp-whitebalance](https://github.com/Hierosoft/gimp-colortemp)

## Documentation
> **colortemp** is a [Gimp](https://web.archive.org/web/20120307072519/http://spip.dealfaro.com/home/code/www.gimp.org) script for changing the color temperature of an image. It can be used to correct the red color cast of photos taken under incandescent light with the camera on daylight setting, or to correct the blue cast of outdoor photos taken in overcast conditions. The color conversions are based on black-body colors at various temperatures, and are performed in the sRGB color space. In Gimp 2.4, more colorspaces are supported, but the plugin has not yet been adapted to work with general colorspaces.
> 
> Once installed, the script is available from the menu item Filters/Colors/Convert Color Temperature.
> 
> ### Download and Installation  
> 
> -   Download **colortemp.scm** for Gimp 2.2, 2.4, and 2.6 from the attachments section at the bottom of this page.  
> -   To install, put the script in the appropriate directory, then click on the menu Filters / Script-Fu / Refresh Filters.  On the Mac, the appropriate directory is Library/Application Support/Gimp/scripts/  
>     
> 
> ### Usage
> 
> You can specify the color temperature of the original image, and the desired color temperature of the result, as well as a light intensity correction factor. There are two ways of specifying the color temperature of the original image:
> 
> 1.  (Option: 'From slider below') You can use a slider to specify the color temperature of the original.
> 2.  (Option: 'From foreground color')  Point the color picker tool at something that was white in the photo (example: snow, clouds, a white T-shirt, white paper), and select its color as foreground color.  Colortemp will compute the color temperature of the light when the photo was taken, and it will use that color temperature as the source temperature.  (Details: the script will use as the original temperature the temperature at which a black body is of color closest to the foreground color.)
> 
> The first method can be used when you know the color temperature of the source, and does not require the image to contain a white or grey object. For example, to convert from from incandescent to daylight, select 'From slider below', choose 2800K as temperature of the original, and 6500K as the target color temperature.
> 
> To use the second method, use the color picker tool to pick the color from a gray or white object in the scene.
> 
> The Intensity slider is used to modify the intensity of the image; this can be useful to avoid clipping of channels. The saturation slider can be used to modify the saturation of the image. Sometimes, when performing a large change in color temperature, the effect is more natural if the image is desaturated a little bit.
> 
> If you wish to make the foreground color white, you should consider using the [whitebalance](https://web.archive.org/web/20120307072519/http://luca.dealfaro.org/Whitebalance) or grey-point script-fu's.
> 
> The color transformation of this color script is performed in the linear, rather than gamma-corrected, color space (as it should, for modifying color temperature). The gamma-corrected color space is the usual one, where a color pixel can have a value from 0 to 255. If x is the value of a pixel in this gamma-corrected space, the value of the pixel in the linear space is approximately (x / 255)^2.2 (the actual conversion is slightly more involved).
> 
> The color conversion performed by this script is based on the color of a black body, in the sRGB color space, as a function of temperature. The calculations are correct only for the official sRGB color space, with D65 (6500 K) as white point, and with the sRGB gamma, which is approximately equal to 2.2. As the conversion is based on black-body temperature, it does not necessarily work well for non-black-body light sources, such as mercury lamps, fluorescent lamps, and so forth.

-<https://web.archive.org/web/20120307072519/http://luca.dealfaro.org/Colortemp>

Further explanation:
- <https://web.archive.org/web/20120307102053/http://luca.dealfaro.org/color-casts-in-digital-photography>

## Contributors
- (original author, script for Gimp 2.2, 2.4, and 2.6 available on this repo under release 2.6-1)
- rich2005 (updated for gimp 2.9.5)
- Poikilos (committed versions to git and made releases)


## Related Projects
- [gimp-whitebalance](https://github.com/Hierosoft/gimp-whitebalance)
  - based on script by same author: https://web.archive.org/web/20120307072519/http://luca.dealfaro.org/Whitebalance
- [GIMP Plugin Registry Revived](https://dodoledev.github.io/registry.gimp.org_revived)
  - [whitebalance](https://dodoledev.github.io/registry.gimp.org_revived/node/72.html) (original GIMP 2.2-2.6 version, available as GIMP 2.6-1 release here)
- GIMP itself has black, gray, and white color choosers now. In GIMP 3.0 it is under Colors, Levels.
  - Whether this is technically valid (operates in correct colorspace to consistently change Kelvin-based color temperature across all colors and brightness levels in the image, or whatever else) is unknown
- (original version) https://web.archive.org/web/20120224005511/http://luca.dealfaro.org/Colortemp


## Discussions Leading up to this repo
- 2017-02-21 [Script for Image color Temperature](https://www.gimp-forum.net/Thread-Script-for-Image-color-Temperature?pid=1304#pid1304)
  - Has GIMP 2.9.5 update (included as release 2.9.5-1 in this repo) edited by rich2005.
- 2018-12-06 [Color Temperature](https://www.gimp-forum.net/Thread-Color-Temperature) on GIMP Forum
- 2019-05-30 [color temperature - make more clear what the two Color Temperature sliders actually do](https://gitlab.gnome.org/GNOME/gimp/-/issues/3440) GIMP issue
  - Related documentation: <https://docs.gimp.org/2.10/en/gimp-filter-color-temperature.html>

