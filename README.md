# GWTC-Data

Updates to the [Gravitational-wave Transient Catalog (GWTC)](https://gwosc.org/eventapi/html/GWTC/) csv data file.


Below is an outline of the steps taken to clean the original dataset:

### Steps:

- Removed auxiliary and marginal detections from the catalog (3 in total)
- Updated all source properties for GWTC-1 BBH events, using data from the [GWTC-2.1 release](https://dcc.ligo.org/LIGO-P2100063/public)
- Updated the ‘catalog.shortName’ and ‘reference’ columns to reflect these changes
- Deleted the columns: [‘chirp_mass’, ‘chirp_mass_lower’, ‘chirp_mass_upper’] – these were empty and seemed to have been unnecessarily created – all actual chirp mass values are in the ‘chirp_mass_source’ columns.
- Deleted the columns: [‘far_lower’, ‘far_upper’, ‘p_astro_lower’, ‘p_astro_upper’] – these were also empty and don’t seem to be used. 
- Added the columns: [‘final_spin’, ‘final_spin_lower’, ‘final_spin_upper’, ‘sky_area_(deg^2)’] – these were missing from the original file but are probably useful to include.

### Notes: 

- GW170817 was not updated in the GWTC-2.1 release so we kept the original values, however we did estimate the total mass by simply adding the individual values for primary and secondary masses. 
- GW190425 has missing source properties for final mass and final spin – maybe because it is the only event not to have Mixed samples (as explained here: https://zenodo.org/records/6513631) 
- The JSON flies and URLs still need to be updated.

## Acknowledgments 

- R. Abbott et al. (LIGO Scientific Collaboration, Virgo Collaboration and KAGRA Collaboration), “Open data from the third observing run of LIGO, Virgo, KAGRA and GEO”, ApJS 267 29 (2023) -- INSPIRE
- R. Abbott et al. (LIGO Scientific Collaboration and Virgo Collaboration), “Open data from the first and second observing runs of Advanced LIGO and Advanced Virgo”, SoftwareX 13 (2021) 100658 -- INSPIRE

“This research has made use of data or software obtained from the Gravitational Wave Open Science Center (gwosc.org), a service of the LIGO Scientific Collaboration, the Virgo Collaboration, and KAGRA. This material is based upon work supported by NSF’s LIGO Laboratory which is a major facility fully funded by the National Science Foundation, as well as the Science and Technology Facilities Council (STFC) of the United Kingdom, the Max-Planck-Society (MPS), and the State of Niedersachsen/Germany for support of the construction of Advanced LIGO and construction and operation of the GEO600 detector. Additional support for Advanced LIGO was provided by the Australian Research Council. Virgo is funded, through the European Gravitational Observatory (EGO), by the French Centre National de Recherche Scientifique (CNRS), the Italian Istituto Nazionale di Fisica Nucleare (INFN) and the Dutch Nikhef, with contributions by institutions from Belgium, Germany, Greece, Hungary, Ireland, Japan, Monaco, Poland, Portugal, Spain. KAGRA is supported by Ministry of Education, Culture, Sports, Science and Technology (MEXT), Japan Society for the Promotion of Science (JSPS) in Japan; National Research Foundation (NRF) and Ministry of Science and ICT (MSIT) in Korea; Academia Sinica (AS) and National Science and Technology Council (NSTC) in Taiwan.”