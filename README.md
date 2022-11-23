# Data Contributor Guidelines

The goal of MAESTRO is to create a repository of opacity data that is reproducible and validated. 

As such, our data contribution process operates much like the traditional peer review process. 


## MAESTRO guiding principles: what to know before starting 



1. For each molecule, we aim to provide a complete set of opacities for Temperature=75.0-4000.0 Kelvin, Pressures=10<sup>-6</sup>-3000 bar, Wavenumbers=30-30000 cm<sup>-1</sup>. [See grid1460.csv on Zenodo as an example of our ideal 1460 P-T Grid](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y). There is no stringent requirement for providing this entire pressure-temperature-wavenumber space, especially if there is no other data available.
2. For each molecule, we aim to provide "high-resolution" opacities with wavenumber bins ~0.003 cm-1 for the lowest pressures. [The same Zenodo posting shows how to recreate our pressure-temperature-variable wavelength grid.](https://zenodo.org/record/4458189#.Y2Kyb-zMI8Y) There is no stringent requirement for providing this entire P-T space, especially if there is no data available.
3. For each molecule, we aim to provide an opacity file for each molecule (that is a weighted sum of all isotopologues), along with the individual isotopologues unweighted, if available. Our metadata structure will allow you to specify the weightings used for each. 
4. For each molecule, we prioritize H<sub>2</sub>-He line width broadening in a mixture that is 15% He, and 85% H<sub>2</sub>. However, we welcome other additions. 
5. For cases where data does not exist for a particular broadener (e.g. H<sub>2</sub>-He), we welcome extrapolations or substitutions that are scientifically justified. These will be reviewed upon submission.


## Benefits of contributing to the MAESTRO database



1. Visibility on science.data.nasa.gov 
2. Easy community access to your data 
3. Open data peer-review validation by MAESTRO team, which includes line list and broadening experts (e.g. [HITRAN](https://hitran.org/), [ExoMol](https://www.exomol.com/))
4. Increased citation count from our easy-to-use citation metadata includes citations to your code & your data 

## Steps to Contribute 

The three basic steps to contribute are : 

1. Submit a data inquiry by opening a (Github Issue here)[https://github.com/maestro-opacities/submit-data/issues/new/choose] 
2. Following our team's feedback, submit a sample data. This acts much like a peer review. 
3. Following our open data peer review, submit the full dataset and meta data. 

See full instructions here. 

## Receiving Credit 

We want to highlight all data contributors beyond the citations. We follow the [all-contributors](https://github.com/all-contributors/all-contributors) specification. This means that contributions of any kind are welcome! Once you have contributed to the data, we will use the [contributor bot to log your contribution](https://allcontributors.org/docs/en/bot/usage). MAESTRO releases will occur on Zenodo, and all contributors will be added to the author list. 


## The Team

- Natasha Batalha (NASA Ames) 
- Nikole Lewis (Cornell University) 
- Ehsan Gharib-Nezhad (NASA Ames) 
- Katy Chubb (University of St Andrews)
- Richard Freedman (SETI) 
- Iouli Gordon (HITRAN/Harvard) 
- Rob Hargreaves (HITRAN/Harvard) 
- Clara Sousa-Silva (Bard College)
- Jonathan Tennyson (ExoMol/University College London) 
- Jeff Valenti (STScI) 
- Sergey Yurchenko (ExoMol/University College London)
- Ryan MacDonald (University of Michigan) 

