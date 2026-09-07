This repository contains all code used for tracking, analysis, and visualization of AEW Surface Flux Sensitivity experiments. 
1) flux_namelists contains the namelist used for each simulation to run the WRF model (5 ensemble sets- fluxon, fluxoff, rst_on24, rst_on36, rst_on48, 9 initialization times- 0300, 0303, 0306, 0309, 0312, 0315, 0318, 0321, 0400)
2) qtrack_resources contains all information and files used to generate AEW tracks for each model simulation. The QTrack tool (Lawton et al, 2022) was used.
3) wps_resources is a collection of files and instructions for how to use NCAR's era5_to_int.py software for using ERA5.nc files from the research data archive for initializing wrf.
4) the notebooks in the main section are for visualization and analysis.
