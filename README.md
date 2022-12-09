MMM-Py README
-------------

The National Oceanic and Atmospheric Administration (NOAA) regularly produces
national 3D radar reflectivity mosaics via its Multi-Radar/Multi-Sensor (MRMS)
system. These mosaics are wonderful for storm and precipitation analysis and research,
but they are distributed in odd formats that NOAA is ever changing. Sometimes you
just want to read a file and make a plot! 

This is what MMM-Py is for. With it, you can read any version of the MRMS radar mosaics,
past or present, and you can analyze, plot, subsection, and output custom mosaics of your 
own, which MMM-Py can ingest later. MMM-Py is free and open source. It is capable of 
producing publication-ready figures and analyses, but it also can do quicklook plots so 
you can check out the cool storm that just happened.

For more info about the latest version of MRMS, see [here.](https://docs.google.com/document/d/1LeVcn_taIXZgzZb5JgWqaVr0xVs7GmA6RpHcb8ZGiwk/edit)


MMM-Py Installation
-------------------

MMM-Py works under Python 2.7 and 3.4-3.6 on most Mac/Linux setups. Windows installation is currently untested.

Put `mmmpy.py` in your `PYTHONPATH`.

You'll need the following Python packages. Most are easily obtained or already installed
with common Python frameworks such as [Anaconda](http://continuum.io/downloads):
`numpy`, `matplotlib`, `six`, `netCDF4`, `os`, `Basemap`, `struct`, `time`, `calendar`, `gzip`, `datetime`

You may also want to install `pygrib` from [here](https://pypi.python.org/pypi/pygrib). This is an optional dependency.

Get MRMS-modified wgrib2 package and installation info from ftp://ftp.nssl.noaa.gov/projects/MRMS/GRIB2_DECODERS/MRMS_modified_wgrib2_v2.0.1-selectfiles.tgz

Install `wgrib2` and note the path to it. Modify the `BASE_PATH`, `TMPDIR`, `WGRIB2_PATH`, and `WGRIB2_NAME` 
global variables in `mmmpy.py` as necessary. `TMPDIR` is where intermediate netCDFs created by `wgrib2`
will go.

Without `wgrib2` or `pygrib`, MMM-Py can still read legacy MRMS binaries and netCDFs. The `pygrib` module will obviate the need to install `wgrib2`, as it enables direct ingest of the grib2 files without converting to netCDF.


Using MMM-Py
------------

To access everything:
```
import mmmpy
```
To see MMM-Py in action, check out the IPython notebooks provided in this distribution.

This [conference presentation](https://ams.confex.com/ams/95Annual/webprogram/Paper262779.html) discusses MMM-Py (among other modules).

MMM-Py was developed at the NASA Marshall Space Flight Center by Timothy Lang (timothy.j.lang@nasa.gov)

See LICENSE file for NASA open source license information.
