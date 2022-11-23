
# Step 1: Submit Inquiry

Submit your data contribution inquiry as [a new issue on Github](https://github.com/maestro-opacities/submit-data/issues/new/choose). This should be **really simple** and is designed just to make sure we are starting a conversation. It is specifically helpful for making us aware of community efforts so there is no repeated effort. Please provide:

1. A description of the opacity data you wish to contribute. Include at least: 1) molecule and/or isotopologues, 2) wavelength range, 3) pressure-temperatures, 4) broadening mixture, 5) line list database used
2. A brief (1-3 sentence) motivation for why the data would be a valuable addition to the MAESTRO database. Common motivation might include: 1) line list update, 2) line width update, 3) missing data or parameter space
3. If you are providing data for an existing molecule, do you wish to overwrite an existing dataset (e.g. provide a completely new set of opacities for H2O), or update a part of the existing set (e.g. provide an update for T>500 K, or a provide an update for certain wavenumber range)


### What to expect after inquiry submission 

Inquiries will be discussed with the [MAESTRO Team](https://github.com/maestro-opacities/submit-data/#the-team), which meets once a month. 

You will be given a “proceed”, “more information needed”, or “pause” with full submission. Common cases for a "pause": 1) suggested line list data has been purposely not selected because of known completeness or accuracy issues, 2) data is not within scope of planetary or sub-stellar atmospheres applicability. 

If you are given a "proceed", you will also receive a set of requirements & suggestions that your calculation would have to abide by. 


### Requirements you may receive after given a “proceed with submission”

**If you are providing partial wavelength coverage that needs to be stitched to our data, we require:**


1. Calculations that have the same or similar setup as our existing data (e.g. line strength cutoff, pressure broadening data)
2. Calculation that are computed on our exact pressure-temperature points, even if you are not covering the full pressure-temperature range
3. Validation plots that showcase negligible artificial stitching effects with our existing data 
4. The same wing cutoff perspection that was used as our default

**If you are providing partial pressure-temperature coverage, we require:**

1. Calculations that have the same or similar setup as our existing data (e.g. line strength cutoff, pressure broadening data)
2. Calculations that are complete for the relevant pressure-temperature parameter space that they are valid for. For example, if there exists H<sub>2</sub>O on a full 1460 pressure-temperature grid and you wish to update line list opacity information with data that is valid below 500 Kelvin, you must submit a calculation that is complete for all existing pressure-temperature points below 500 Kelvin. This ensures consistency across our data set. If you have additional points, including those on the existing grid, you may include those as part of the submission.  
3. The same wing cutoff perspection that was used as our default

### Optional recommendations you may receive after “proceed with submission”

**If you are providing a full new dataset we prefer if:**

1. Calculations cover the full set of pressure-temperature space included in the [grid1460.csv on Zenodo as an example of our ideal 1460 P-T Grid](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y). However, we recognize this will not always be possible 
2. Calculations are at a minimum wavenumber spacing as the [grid1460.csv on Zenodo as an example of our ideal 1460 P-T Grid](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y). However, we recognize this will not always be possible. 


## Step 2: Submit sample for “data peer review”

Your data submission sample will consist of metadata, sample data, and a data validation report. Our process for data submission is completely open, and the review will take place via Github Issues. There are three components of the data submission: 



1. Metadata: this tells us how the data was computed, and with what source data
2. Data sample: this shows us what format your data is in and ensures a seamless integration into our database 
3. Data validation report: this is a collection of simple plots that demonstrates the validity of the data 

See below for further descriptions of these components


