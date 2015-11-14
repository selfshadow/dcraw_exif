# dcraw_exif
This project is not part of UnrealEngine but it was used for the UnrealEngine Kite demo. See:
  https://www.youtube.com/watch?v=_zVddsYKZnw
  https://www.youtube.com/watch?v=clakekAHQx0

The code was tested with multiple Canon cameras using the CR2 (raw) format as input.

Typical commandline:
  dcraw -4 -w -o 1 -T -Z -n 100 MyPath/MyImage.CR2

* -4 => Linear 16-bit
* -w => use camera white balance
* -o 1 => sRGB (?? is that right?)
* -T => Write TIFF
* -Z => crop the borders like Canon would do it to get the same sized image
* -n 100 => fixes noise in the darks

Compile with Visual Studio 2012:
* Create new console application
* add dcraw.c
* compile (some warnings are not fixed yet)

History:
* 11/14/2015 SH Canon crop parameters are now retrieved from the CR2 file
* 09/30/2015 SH Integrated DCRAW 9.26
* 09/30/2015 SH Fixed compilation on OSX
* 04/22/2015 MM Started with original from: https://www.cybercom.net/~dcoffin/dcraw/dcraw.c
* 04/22/2015 MM Updated with changes from Rob Sumner: https://users.soe.ucsc.edu/~rcsumner/rawguide/dcraw_win.c
* 04/22/2015 MM added new features: crop and downsample
* 04/22/2015 MM pass EXIF data (FocalPlaneXResolution, FocalPlaneYResolution, FocalPlaneResolutionUnit) from input to TIFF


