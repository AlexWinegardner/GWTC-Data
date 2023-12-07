# GWTC-Data

Updates to the Gravitational-wave Transient Catalog (GWTC) csv data file.


Below is an outline of the steps taken to clean the original dataset:

Steps:

- Removed auxiliary and marginal detections from the catalog (3 in total)
- Updated all source properties for detection events, using data from the GWTC-2.1 release
- Updated the ‘catalog.shortName’ and ‘reference’ columns to reflect these changes
- Deleted the columns: [‘chirp_mass’, ‘chirp_mass_lower’, ‘chirp_mass_upper’] – these were empty and seemed to have been unnecessarily created – all actual chirp mass values are in the ‘chirp_mass_source’ columns.
- Deleted the columns: [‘far_lower’, ‘far_upper’, ‘p_astro_lower’, ‘p_astro_upper’] – these were also empty and don’t seem to be used. 
- Added the columns: [‘final_spin’, ‘final_spin_lower’, ‘final_spin_upper’, ‘sky_area_(deg^2)’] – these were missing from the original file but are probably useful to include.

Notes: 
- GW170817 was not updated in the GWTC-2.1 release so we kept the original values, however we did estimate the total mass by simply adding the individual values for primary and secondary masses. 
- GW190425 has missing source properties for final mass and final spin – maybe because it is the only event not to have Mixed samples (as explained here: https://zenodo.org/records/6513631) 
- The JSON flies and URLs still need to be updated.