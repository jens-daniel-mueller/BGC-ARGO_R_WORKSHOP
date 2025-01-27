# GO-BGC toolbox for R

## ABOUT

This toolbox contains a variety of functions for accessing, processing, and visualizing [Biogeochemical Argo](https://biogeochemical-argo.org) data. Functions are designed to be maximally efficient, to provide access to the most up-to-date data available, and to allow for downloading and plotting of those data based on numerous user-defined conditions.

## INSTALLATION AND USE

This repository can be cloned using the command line or GitHub Desktop. Or the files can be directly downloaded in zipped format.

Before use, make sure the files are placed in a directory that is in the R search path. Or add the directory where they are located to the search path https://support.rstudio.com/hc/en-us/articles/200711843-Working-Directories-and-Workspaces. Or run it in the directory where the main_workshop script was placed.

For an overview of how to use this toolbox, step through the 'main_workshop' script (launching it in the R Console, or in the Rstudio console using the Run button or Ctrl+Alt+Enter, the Run All shortcut in R studio), a tutorial that was developed for the [2021 GO-BGC Scientific Workshop](https://www.us-ocb.org/joint-gobgc-workshop/) (6/30/21).

## FUNCTIONS

### Main functions (to be called from script or command window):

initialize_argo.R        : defines standard settings and paths and downloads synthetic profile index file<br/>
load_float_data.R        : loads data of one or more specified float(s) into memory<br/>
select_profiles.R        : returns profiles and corresponding floats based on input criteria<br/>
show_profiles.R          : downloads float data and calls plot_profiles to create plot<br/>
show_sections.R          : downloads float data and calls plot_sections to create plot<br/>
show_trajectories.R      : downloads float data and calls plot_trajectories to create plot<br/>
main_workshop.R          : tutorial script for GO-BGC Scientific Workshop (6/30/21)<br/>

### Background functions (primarily called by main functions in background):
calc_auxil.R             : calculates various auxiliary variables from Argo float data<br/>
check_dir.R              : determines if a directory needs to be created and does so if necessary<br/>
depth_interp.R           : interpolates values for BGC-Argo parameters against depth<br/>
do_download.R            : determines if a file should be downloaded or not<br/>
do_pause.R               : pauses execution of main_workshop (if used without desktop)<br/>
download_float.R         : downloads the Sprof NetCDF file for one float<br/>
download_multi_floats.R  : calls download_float to download Sprof NetCDF files for multiple floats<br/>
get_lon_lat_lims.R       : obtains maximum/minimum latitude and longitude values from input data<br/>
get_multi_profile_mean   : calculates the mean profile of multiple profiles<br/>
get_var_name_units.R     : returns the long variable name and units name for a given short parameter name input<br/>
plot_profiles.R          : plots profiles of one or more specified float(s) for the specified variable(s)<br/>
plot_sections.R          : plots sections of one or more specified float(s) for the specified variable(s)<br/>
plot_trajectories.R      : plots trajectories of one or more specified float(s)<br/>
try_download.R           : attempts to download a file from any of the specified GDACs<br/>

You can open the corresponding R script file to check out the description of input and output parameters for individual functions. 
A full description for all the functions is summarized in the document entitled "function description.txt"


## REQUIREMENTS
Rstudio version 1.4 and R version 3.4 (or more recent) are needed to use these functions without modifications.<br/>
An Internet connection is needed to get the latest versions of index and Sprof files; but the repository includes versions of these files so that it can be run offline.
Memory requirements depend on the number of profiles and variables that are simultaneously loaded into memory.


## COMMENTS, BUGS etc.?
Please feel free to use the GitHub Issues and Pull Requests features to report any problems with this code and to suggest bug fixes.

## BGC-ARGO GUIDE
More detailed information about quality control flags, raw and adjusted modes, etc., can be found in
H. C. Bittig et al., Front. Mar. Sci., 2019, https://doi.org/10.3389/fmars.2019.00502

## CITATION

Please cite this toolbox as:

M. Cornec (LOV), Y. Huang (NOAA-PMEL), Q. Jutard (OSU ECCE TERRA), R. Sauzede (IMEV) and C. Schmechtig (OSU ECCE TERRA), 2021.<br/>
BGC-Argo-R: A R toolbox for accessing and visualizing Biogeochemical Argo data. Zenodo. http://doi.org/10.5281/zenodo.5028139 <br/>
(All authors contributed equally to the code.)

Adapted from the BGC-Argo-Mat Toolbox: 
H. Frenzel*, J. Sharp*, A. Fassbender, J. Plant, T. Maurer, Y. Takeshita, D. Nicholson, A. Gray, 2021.<br/> 
BGC-Argo-Mat: A MATLAB toolbox for accessing and visualizing Biogeochemical Argo data. Zenodo. https://doi.org/10.5281/zenodo.4971318.
