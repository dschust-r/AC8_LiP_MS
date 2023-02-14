# AC8_LiP_MS

This repository contains all files relevant for the data analysis of the publication (doi_here). 

The experimental setup, as well as the LC-MS/MS conditions for the experiment can be found in the methods section and/or on PRIDE (). 
Raw files, FASTA files and search results can be found on PRIDE ().

All relevant files for the 3 different experiments (CaM, Gas, Gbg) can be found in the R folder
  * 230214_P04_CaM_LiP
  * 230214_P04_CaM_TC
  * 230214_P04_Gas_LiP
  * 230214_P04_Gas_TC
  * 230214_P04_Gbg_LiP
  * 230214_P04_Gbg_TC 
  
The sample list (containing information on the naming and conditions) can be found in the R folder but the condition setup is also contained in the search output deposited on PRIDE.
 
 # Aims

The aims of these experiments was to study the interaction of AC8 with 3 different regulators: CaM, Gas and Gbg. 
The CaM data set was already published [here](https://www.biorxiv.org/content/10.1101/2023.02.01.522707v1.full.pdf) as part of a proof-of-principle experiment.
The binding site of Gas was determined experimentally with cryo-EM. 
The interaction of Gbg was uncharacterized.
 
 # Experiment 
 
The experiment was conducted in quadruplicates. 

**LiP-MS:** 
Membrane pellets were produced as mentioned [here](https://www.biorxiv.org/content/10.1101/2023.02.01.522707v1.full.pdf). They were resuspended in LiP-buffer with 1 mM MnCl2 and 100 uM GTPgS for samples containing G proteins.
The interaction partners were added in increasing concentrations (0, 0.01, 0.1, 0.5, 1, 2, 3 ug) to 50 uL of membrane suspension at 2 ug/uL protein.
The samples were incubated for 10 min at 25°C, followed by an unspecific digest with proteinase K (1 ug) for 5 min at 25°C. 
The digest was quenched by boiling the samples (99°C) for 5 min, then cooling them down and adding sodium deoxycholate to a final % of 5%. 
Disulfide bonds were reduced (5 mM TCEP-HCl) and free cysteines were alkylated (40 mM iodoacetamide). 
The proteins were digested overnight with Lys-C and trypsin and desalted (C18 cleanup) the next day.

**Trypsin controls:**
Trypsin control samples were produced to check for unwanted protein abundance changes. They were treated the same way as the LiP-MS samples, except that instead of proteinase K water was added.

# LC-MS/MS
Samples were reconstituted in 5% ACN, 0.1% FA + iRT peptides (Biognosys). 
The LC-MS/MS details can be found in the publication or in the respective PRIDE repositories. 

Pooled samples of all conditions were prepared for library generation. 

# Data processing
Raw data was searched with Spectronaut (v.15), against a contaminant FASTA file (MaxQuant), the human proteome (reviewed and unreviewed entries), the sequence of bovine AC8 with all of its tags and the respective interaction partner sequences. 
Single hits were excluded, min peptide length was set to 5 amino acids, imputation was switched off. Protease-specificity for LiP samples was set to semi-specific. Peptides were grouped by their modified sequences for quantification. 
Data was exported from Spectronaut and further analyzed in R.
