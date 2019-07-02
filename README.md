# mpl-kaleidagraph

matplotlib style file created to mimic Kaleidagraph line/scatter plots.


## Sample Kaleidagraph plot

<img src="https://github.com/bskinn/mpl-kaleidagraph/raw/master/images/kal.png" alt="Sample Kaleidagraph plot" width="500px">


## matplotlib Replica

*(artificial datasets constructed to resemble the original)*

<img src="https://github.com/bskinn/mpl-kaleidagraph/raw/master/images/mpl.png" alt="matplotlib Replica" width="500px">


## Jupyter Code

```
from pathlib import Path
from random import random

import numpy as np

%matplotlib inline
import matplotlib.pyplot as plt
from matplotlib.ticker import MultipleLocator


plt.style.use(str(Path('C:\\') / ... / 'kaleida.mplstyle'))


xdata1 = np.arange(0, 193, 7)
ydata1 = 250 * np.exp(-0.15 * (xdata1 / 60))
ydata1_noisy = np.array([(0.99 + 0.02 * random()) * _ for _ in ydata1])

xdata2 = np.arange(0, 160, 7)
ydata2 = 250 * np.exp(-0.55 * (xdata2 / 60))
ydata2_noisy = np.array([(0.99 + 0.03 * random()) * _ for _ in ydata2])


plt.plot(xdata1, ydata1)
plt.plot(xdata1, ydata1_noisy, 'o', label="Base")

plt.plot(xdata2, ydata2)
plt.plot(xdata2, ydata2_noisy, 's', label="Tubing")

plt.xlabel('Time (min)')
plt.ylabel('O$_2$ Concentration ($\mathrm{\mu}$M)')

plt.text(120, 195, "Base", size='large')
plt.text(115, 100, "Tubing", size='large')

ax = plt.gca()

ax.set_xlim([0, 200])
ax.set_xticks(list(range(0, 210, 30)))
ax.xaxis.set_minor_locator(MultipleLocator(5))

ax.set_ylim([0, 280])
ax.set_yticks(list(range(0, 300, 50)))
ax.yaxis.set_minor_locator(MultipleLocator(10))
```

-----

Copyright (c) Brian Skinn 2019

Style file is licensed under the [MIT License](https://github.com/bskinn/mpl-kaleidagraph/blob/master/LICENSE.txt).  
Images are licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a> &nbsp; <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /></a>.
