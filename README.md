# quasar-wind-grid

Repository of grid results for the 2015 Quasar wind models

page is live at http://jhmatthews.github.io/quasar-wind-grid/


### Directory Structure

* synthetic_spectra: folder containing the output spectra from the radiative transfer simulations
* scripts: useful python scripts for reading in and plotting spectra
* plots: Ready made plots and visualisations

### Processing Output Files

The output spectrum files follow the astropy conventions with the format

Freq.        Lambda  Created  Emitted   CenSrc  Disk     Wind     HitSurf Scattered A20P0.50 
4.002830e+14 7489.514     0.177    0.149   0.0217    0.127  0.00031    0.029        0    0.307   

And thus can be read into a table with the commands

```Python
from astropy.io import ascii
data = ascii.read(filename)
```

You could then make an Flambda flux density plot with wavelength at 20 degrees by doing

```Python
import pylab as plt
plt.plot(data["Lambda"], data["A20P0.50"])
```


