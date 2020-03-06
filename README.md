# LymphGen
Repsoitory for Lymphgen algorithm

This archive contains an R version LymphGen algorithm that was the basis of the 2020 Wright et al Cancer cell paper.

This is intended for achival purposes and for those who wish to investigate the code that underlies the LymphGen predictor.  We do not recommend using these scripts to predict samples. for that purpose we have set up a web based version of the predictor available at https://llmpp.nih.gov/lymphgen/index.php.  The web based predictor runs far more efficiently and includes additional pre-processing features and error checks.  In particular version of the algorithm assumes that all mutations have been prefiltered by location. (e.g. Synon mutations only included if within 4kb of the start site.) 

The zipped archive includes a number of different files.
Model9.R includes a number of functions that are required for the LymphGen predictor.  This file should be sourced first
Trialrun.R is the main script that imports the necessary files, runs the prediction algorithm and exports the results.  Flags

Full.Uber.2019.txt, Fullmat.2019.txt, Index.Flat.txt, originalpred.txt, and Study,sampR.txt are files related to training set.  These should all be included in the working directory where Trialrun.R is sourced.  At the top of this code are a number of flags that should be set in order to customize the run to a particular data set.

The following input files that represent the data of the samples to be predicted should also be included in the working directory.

Sample.annot  (an annotation file for the samples)
mut.genelist.txt  (the list of GeneIDs for which mutations were available.)

Mutation.flat.txt  ( the list of mutations found on each sample)

Copy flat.txt     (The list of copy number changes found in each sample, only needed if copy number is available)

CGH.genelist.txt     (The list of genesIDs for which copy number data is available. only used if copy number is available)

Arm.file.txt (The list of copy number changes on chromosomal arms,  This file is optional)

Once run, the algorithm will output 3 files:

Result.txt    (The results of the predictor)

Compare.txt (The accuracy of the predictors on the training data.  This is useful in determining the extent to which the incomplteness of data my affect preformance)

warn.txt  (a file indicating possible issues with the input data)

Example input and output files are included in separate folders.  For a complete discussion of the algorithm and the format of the input files users are directed to https://llmpp.nih.gov/lymphgen/LymphGenInstructions.pdf?v=1583520112







