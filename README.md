# shark-phytoplankton-indicator
#### Repository for R scripts used for calculating HELCOM Seasonal succession of dominating phytoplankton groups indicator from data downloaded from SHARKweb

The HELCOM indicator Seasonal succession of dominating phytoplankton groups is used as part of the status assessment of pelagic habitats in the HELCOM Holistic Assessment of the Baltic Sea. The indicator report with information on indicator concept and results can be found on the [HELCOM website](https://helcom.fi/baltic-sea-trends/indicators/).

This repository use data downloaded from [SHARKweb](https://sharkweb.smhi.se/hamta-data/) to calculate the indicator from the Swedish national or regional phytoplankton monitoring programmes.

To use international data downloaded from ICES, see the following repository:

https://github.com/helcomsecretariat/SeasonalSuccessionOfDominatingPhytoplanktonGroups

## Scripts
This repository includes two scripts for calculation of the Seasonal succession of dominating phytoplankton groups indicator.

The scripts reads a SHARKweb phytoplankton data file (downloaded at https://sharkweb.smhi.se/hamta-data/) and prepares data for the **Helcom candidate indicator script** written by Joanna Calkiewicz & Janina Kownacka according to the document 'Seasonal succession of dominating phytoplankton groups'. The indicator focuses on the phytoplankton groups dinoflagellates (mixotrophic and autotrophic), cyanobacteria, diatoms and the species Mesodinium rubrum. The **Helcom candidate indicator script** is called after data wrangling and identification of reference period.

The script groups taxa based on taxonomic level, and aggregates biomass data (in ug/l or um3/l, choose parameter above) for diatoms, cyanobacteria, autotrophic/mixotrophic dinoflagellates and for the ciliate species <i>Mesodinium rubrum</i>. Monthly means are calculated if the station was sampled multiple times during a month. 

A five year reference period is identified by the lowest moving average of the yearly standard deviation of phytoplankton biomass. 

### shark_phytoplankton_indicator.Rmd
This script reads a phytoplankton data extract from the SHARKweb and prepares the data for the M1-eng.R script, i.e. it groups the data based on the taxonomic information and aggregates biomasses for the groups.

### M1-eng.R
This script calculates the indicator results and produces an indicator assessment.
