Within this directory is all code used to generate African easterly wave tracks from a WRF simulation, using the QTrack tool (Lawton et al, 2022).
For more detailed instructions, see Quinton's repository: https://github.com/qlawton/QTrack

1) first open a terminal in the conda environment being used, and install qtrack. conda activate npl-2025b. pip install qtrack.
2) Ensure the following files are located within the directory you are running the tracker in: AEW_module.py,
3) Prep data before running the tracker using the following:
   - Run era5_regrid.ipynb for desired dates before simulation. QTrack software suggests at least one week prior to the model simulation is necessary for accurate spinup of the tracker.
      - This will result in one wind_season_lowres_700_2020_B1-6hr.nc file. This file will be merged with a single WRF u and v file using wind_combine.ipynb.
      - 1x1 degree, 6hrly
   - Run regrid_wrfout.ipynb to match the format of the ERA5 data
      - This will result in one wrfout_regrid_'+save_name+'.nc' file. This file will be merged with the above file using wind_combine.ipynb
      - 'save_name' is the ensemble set and initialization time. 
      - 1x1 degree, 6hrly
   - Run wind_combine.ipynb (Lawton et al, 2022) to generate on single wind file to run the tracker on
      - This will result in one wind_for_tracking_'save_name'.nc
      - for example, a fluxoff simulation initialized at 12z on the 3rd: wind_for_tracking_fluxoff_0312.nc
      - There should be one of these merged files for each simulation.
4) Now there should be trackable files for each simulation. Run qtrack.ipynb (Lawton et al, 2022) for each simulation
5) Now, we have wave tracks for every detectable wave in our simulations. Because we are focusing on the waves that lead to Hurricane Paulette and Tropical Storm Rene, we go into these tracks, grab each of these waves, and save them separately. To do so, use save_wave_tracks_for_wrfout.ipynb
   - This code will require some guessing and checking. It's helpful to look at the Hovmollers output by the tracker to determine the approximate longitude of the wave you want to track. Rene ends around 40W, Paulette ends around 55W. 
    
     
