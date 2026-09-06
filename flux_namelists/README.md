Though each ensemble member begins at different times, all end on the 9th at 12z
5 ensemble sets within each ensemble member:
- Fluxon- Control. Fluxes set to on for the entirety of simulation. 
- Fluxoff- Completely decoupled. Fluxes set to off for the entirety of the simulation (isfflx=0)
- rst_on24- Sensitivity. Takes the restart file from the fluxoff simulation and restarts the simulation at this point with fluxes turned on. for example, rst_on24 for init0300z. Finds restart file wrfrst0400z from fluxoff, then initializes the simulation with this file. isfflx=1
- rst_on36- Sensitivity. Takes the restart file from 36 hours into fluxoff simulation.
- rst_on48- Sensitivity. Takes the restart file from 48 hours into fluxoff simulation.
