
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


# Step 2: Submit sample for “data peer review”

Your data submission sample will consist of metadata, sample data, and a data validation report. Our process for data submission is completely open, and the review will take place via Github Issues. There are three components of the data submission: 

1. Metadata: this tells us how the data was computed, and with what source data
2. Data sample: this shows us what format your data is in and ensures a seamless integration into our database 
3. Data validation report: this is a collection of simple plots that demonstrates the validity of the data 

See below for further descriptions of these components. 

## Metadata

You will need to submit a json file that includes the following information. [You can see examples of previously submitted files here](https://github.com/maestro-opacities/submit-data/tree/main/examples/metadata). The basic information we request is as follows:

**Calculation Info**

1.  Intensity cutoff used
2.  Wing cutoff used
3.  Citation for line profile citation
4.  DOI for opacity bundle (if there is no paper associated with the data, then we will require you to post a sample of the data to Zenodo _<span style="text-decoration:underline;">after</span>_ we have approved your data addition. This is for your own benefit so that users can explicitly cite your work! 
5.  Wavelength grid used. Alternatively if you used a variable grid such as the one shown here [grid1460.csv](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y) you can provide a file.
6.  File formatting statement: e.g., `C2H2_T{temperature:.0f}_P{pressure:.4e}.xsec` [see python string literals tutorial](https://docs.python.org/3/tutorial/inputoutput.html#formatted-string-literals). This allows us to easily build your file names. If you do not know python we can assist with this. 
7.  File read statement in python: e.g. np.fromfile(filename) where result would be a 1d array of cross sections. If you do not know python we can assist with this. 

**Broadener Info**

For each broadener agent used (e.g. if H2, He mixture used), specify:

1.  broadener mixture (e.g. 14 % H2)
2.  calculation type (see options)
3.  functional form, if applied
4.  citation DOI for broadener info
5.  user warning (see options)
6.  user notes (optional)

**Line List Info**

For each line list used, specify:

1.  min wno used
2.  max wno used
3.  min temp applied to
4.  max temp applied to
5.  database name (e.g. AYT2 ExoMol, version 20160726)
6.  linelist DOI
7.  user warning (see options)
8.  user notes (optional)



## Data validation report

### Requirements for data validation


* A few representative samples of your raw data. Though it is not a requirement to submit the full dataset initially, we do ask for a few representative cases that complement the plots submitted. These files should follow the eventual data format requirements.
* Representative plots that showcase the data. It is up to your discretion how these should be made. Note that the team will want to assess the native resolution of the data, to some degree. For example, you could provide native high resolution opacities across bands of interest, and low resolution plots at R~100-1000 across a wide wavelength range 
* If only a certain wavelength range, or pressure-temperature profile is included in the submission for an existing dataset, then validation is required at the edges. E.g. at the temperature transition, or at the wavelength transition.


### Optional Recommendations for data validation

Here are some general guidelines that can help guide your submission: 

* If there is existing data that you wish to overwrite with a new dataset, please provide a direct comparison between what we have and your new calculation. Any differences should be scientifically motivated. 
* If there is no data for a specific molecule, sufficiently detailed methodology should be provided to convince the team the calculation is valid. Additionally, other data sources available through other providers or platforms can also be used as comparison (even if they are only provided at lower resolution, for example)
* A comparison should be made at the native resolution of the computed data 

## Data formats and units for sample data

* One file (ascii or other) for each pressure-temperature combination that contains all wavenumbers associated with the calculation
* One file that analogous to [grid1460.csv on Zenodo](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y)that contains the pressure-temperature grid, and any information regarding the wavelength grid 
* Data should be in units of cm2/species 

## Submission 

* Metadata json file can be uploaded to the Github issues ticket
* Link to sample data can be uploaded to the Github issues ticket 
* Pdf or markdown of the data validation report can be uploaded to the Github issues ticket

## Feedback 

New data submissions will also be reviewed on a monthly cadence that coincide with team meetings. Expect to receive written feedback through Github Issue within 3-4 weeks.  




# Step 3: Final data transfer 

Once all feedback has been incorporated, we will move to the final data transfer! 


## Data formats and units from original sample

* One file (ascii or other) for each pressure-temperature combination that contains all wavenumbers associated with the calculation
* One file that analogous to [grid1460.csv on Zenodo ](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y)that contains the pressure-temperature grid, and any information regarding the wavelength grid 
* Data should be in units of cm2/species 


## Data transfer

We accept any method of data transfer (e.g. google, box, institutional websites). If you need resources for this (e.g. box space) please let us know and we will assist you. 


## Journey of the data 

Your data will be pushed to the SQL database hosted at NASA Ames within a couple weeks, where anyone will be able to access and download it.  


## Erratum 

Any errors that are noted after the insert should be handled through the original Github issues posting. Please follow the steps: 

1. Navigate to [closed issues on Github ](https://github.com/maestro-opacities/submit-data/issues?q=is%3Aissue+is%3Aclosed)
2. Find your original data issue and reopen it 
3. Describe the problem: 1) what molecule is affected, 2) what pressure-temperature range is affected, 3) what wavelength range is affected 
4. Showcase the solution via plots and new sample data uploads 
5. The MAESTRO team will review your report and provide any necessary feedback 
6. If the erratum is approved, you will have to submit a new version to your Zenodo posting of the sample data. In the event where the data was tied to a published paper, please provide the erratum of the published paper instead. 
7. Update your json file with the new DOI for the opacity calculation and resend the data 
8. Your update will be pushed to SQL database ASAP. 
