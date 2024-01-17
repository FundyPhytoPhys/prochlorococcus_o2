# Code

Information about documents added to this folder.
"README.md"

"Import_MetaData.Rmd"

"Import_MCData.Rmd"

"Process_MCData.Rmd"

"Merge_MCGrowthData.Rmd"
This Rmd, "Merge_MCGrowthData", reads in all individually processed MultiCulti runs from the "\Data\ProcessedData\ProcessedMCData" folder and merges the data into 1 data frame. Growth estimate flags are defined based on absolute amplitude change. Growth estimates are set to 0 for models that returned a negative growth estimate and if the absolute amplitude change threshold was not met. For conditions that were replicated, a mean growth estimate was calculated. This single data frame is saved as a .Rds for further analysis called "PICO_Processed_MCGrowthFits.Rds" in the "\Data\CleanData\CleanedMCData" folder.


"Import_JazEmData.Rmd"

"Import_OlisData.Rmd"

"Process_OlisJazEmData.Rmd"

"Merge_GrowthPURData.Rmd"

"PICOgam.Rmd"
This .Rmd produces a Generalized Additive Model (GAM) to examine the relationship between the chlorophyll proxy (ΔOD) growth rate across the blue and red spectral wavebands, photoperiod and PAR levels for each P.marinus ecotype in this study. The gam function from the R package mgcv (Wood, 2022) was used to model the growth rate with smoothing terms to indicate the 90, 50 and 10% quantiles. "PICO_Merged_GrowthFitsPURPAR.Rds" is called in from \Data\CleanData\CleanedMCData folder and generated GAM plots are saved in \Output\Figures folder as .png.

"ManuscriptFigures.Rmd"

