Use the resources in this folder to run WPS with ERA5 .nc files directly from the NCAR research data archive.
The files and information listed in this folder are taken from https://github.com/NCAR/era5_to_int
Go to this GitHub page for more detailed instructions. 

Simple overview:
1) Ensure the following files are in the WPS folder: WPSUtils.py, fortran.io.py, era5_to_int.py, ecmwf_coeffs.txt, batch_py, Vtable.txt
2) Adjust Vtable to desired preferences. I believe the one I have here is taken from the WPS folder on derecho.
3) Adjust batch_py to match the dates and directories you want to include in your simulation. For example, for a simulation ranging from 2020-09-03 03z to 2020-09-09 09z, the last line of the batch script should be as follows:
   - python era5_to_int.py -i 2020-09-03_03 2020-09-09_09
4) note: the "-i" tells the script to use pressure data. To use model data, remove this indicator.
5) run the script by qsub batch_py
6) Again, for more information and detailed readme, visit: https://github.com/NCAR/era5_to_int
