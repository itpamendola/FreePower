# FreePower
Fisher matrix for spectrum and bispectrum

FreePower, by L. Amendola (2023)
================================
Collaboration with M. Pietroni, M. Marinucci, M. Quartin

FreePower is composed of two Mathematica notebooks, to be run in sequence. 
It produces the calculations of paper arXiv:2307.02117. If you use this code, please cite that paper.
Let us call FreePower  the directory in which the zip file is opened.

All the directories in which input or output is located are named in the file 
FreePower/Fisher/folder.txt and are read from this file.


The analytic kernels are already stored  in FreePower/Fisher/kernels.

You need to install the CUBA integration package by T. Hahn into a directory FreePower/Cuba.

The first code is
FreePower/Fisher/SpectraAndDerivatives.nb
This reads the kernels, the input linear spectra (in FreePower/inputlinearspectra) 
and the survey fiducial (in FreePower/fiducials) and creates the one-loop spectra 
and the needed derivatives, and store the results in FreePower/Fisher/Results/SpectraAndDerivatives
This needs to be run once for every different input linear spectrum or different fiducial values.
It takes around three hours.


The second code is 
FreePower/Fisher/NLFisher-bispectrum.nb
This reads the spectra and derivatives and creates configuration files in FreePower/Fisher/Results/config, 
and then produces the Fisher matrices for P,B,P+B, storing the results in FreePower/Fisher/Results/FM. 
The main types of output files are
P-FM-raw-km0.25kmb0.1s0.01.dat (FM without priors for P)
P-FM-prior-km0.25kmb0.1s0.01.dat (FM with priors for P)
P-invFM-prior-1.1km0.25kmb0.1s0.01.dat (Inverse FM for the redshift bin 1.1 parameters for P)
P-err-km0.25kmb0.1s0.01.dat (marginalised errors for P)
Analogously for B and PB.
An example of corner plot will be stored in FreePower/Fisher/Results/plots.
It takes around 10 minutes.

