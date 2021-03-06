# quasar-wind-grid

Repository of grid results for the 2015 Quasar wind models

page is live at http://jhmatthews.github.io/quasar-wind-grid/

filenames are as follows (this is the fiducial model):
run42_thmin70_rmin50_a0p5_rv1e19_f0p01.spec

where the variables are as defined in the paper, i.e.

* f- volume filling factor, 0.1 (0p1) or 0.01 (0p01)
* thmin - minimum wind angle, 70 or 55.
* rmin - minimum launch radius, 10,30,or 50
* a - alpha, acceleration exponent, 0.5,0.6, or 1
* rv - acceleration length, 1e18 or 1e19

### Directory Structure

Spectra are split into two grids, depending on clumping factor, and in folders
* synthetic_spectra_f0p1/
* synthetic_spectra_f0p01/

### Processing Output Files

The output spectrum files follow the astropy conventions with the format

Freq.        Lambda  Created  Emitted   CenSrc  Disk     Wind     HitSurf Scattered A20 
4.002830e+14 7489.514     0.177    0.149   0.0217    0.127  0.00031    0.029        0    0.307   

And thus can be read into a table with the commands

```Python
from astropy.io import ascii
data = ascii.read(filename)
```

You could then make an Flambda flux density plot with wavelength at 20 degrees by doing

```Python
import pylab as plt
plt.plot(data["Lambda"], data["A20"])
```

Any questions, email me at jm8g08 [at] soton.ac.uk. 
