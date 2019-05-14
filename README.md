# CBMF4761 Computational Genomics Spring 2019

This repository contains the project software files (source code/scripts, sample input and output files, additional necessary files for running the associated software) for the final project "Identifying Master Regulator Dependencies in Pediatric Osteosarcoma using VIPER" submitted by Jovana Pavisic, jp3679, as her final project for the Columbia University CBMF4761 Computational Genomics class during the Spring 2019 semester.

The source code is presented in the form of a jupyter notebook and can be run with the R kernel enabled. 

The required packages are listed in the first cell of the notebook. All other files needed are in the SourceCode_files directory. Of note, only the data files that are publicly available are included, specifically the RNAseq gene expression data for pediatric osteosarcoma patients (as TPM counts) and clinical annotations for those patients available through the Therapeutically Applicable Research to Generate Effective Treatments (TARGET) Project. These can be downloaded at any time from the TARGET data matrix: https://ocg.cancer.gov/programs/target/data-matrix.

However, in this project, I used the original RNAseq FASTQ files from 86 pediatric OS patients available through TARGET and 35 pediatric OS patients available from the DFCI Pediatric Osteosarcoma Genomics Project which are under controlled access requiring submission of an application through dbGaP (projects phs000218.v4.p1 and phs000699.v1.p1, respectively), and 39 samples provided by a collaborating institution through a MTA. I then ensured uniform RNA alignment and gene quantification using Kallisto for all the samples and obtained gene expression counts as logTPMs. The publicly available TARGET RNAseq TPM counts are highly correlated with those obtained using Kallisto and thus that will serve as a template file for running the code. Unfortunately, I cannot provide the sequencing or clinical data used in this project from the other two sites or the original RNA sequencing data.

## SourceCode_files

1. `TARGET_OS_Discovery_ClinicalData.csv` This file contains all of the patient metadata, like relapse status, metastatic disease status, and survival post treatment.
2. `TOS_TPM.txt` Read counts measured in transcripts per million, which was downloaded directly from the TARGET Osteosarcoma study. This is the input for viper. 
3. `ens2entrez.rda` This has information for mapping genes labels from ensembl ids to entrez ids. This is necessary for downstream MR processing. 
3. `viper_dset.csv` A precomputed table of master regulator signatures for each patient. The process used to generate this file is described in detail in the report. 

