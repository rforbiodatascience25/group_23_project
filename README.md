# group23_project

## Description of .txt files

### data_clinical_patient.txt

This file contains the main informations of all the patients that were studied, it contains 6 columns, patient ID, sex, age at diagnosis, drug received, the "survived month" and their overall status (alive or dead, at the time of the check up). From this data set it is possible to look at the survival rate of the patients and see if different factors such as the medication or the age may have an impact on the survival rate.

### data_gene_panel_matrix.txt

### data_mutations.txt

### data_sv.txt

This file describes 347 structural variants (SV) detected in tumor sample, with 30 columns. Most of the columns provide genome-focused details that might not be relevant to our analysis. But if we need to look more closely at specific variants, this file gives access to sequencing information such as type of SV, region of breakpoint and more.

## Quick summary:

-   Site1 / Site2 columns describe the two breakpoints of a Structural Variant (gene, region, position).
-   Class, Breakpoint_Type, Connection_Type describe the type of SV.
-   Event_Info, Annotation, Comments give biological context.
-   Read counts help assess detection quality and confidence.

Detailed information for each column with examples can be found in the description_data_sv textfile.

## TODOs:

-   Survival Rate (with different parameters, ex tumor types, drug types, tmb, kind of mutation)(Romane)
-   Logistic regression(correlation of survival rate with all the different information)(Cora)
-   Correlation Matrix(Cora)
-   Partial Correlation(survival rates to all the paramters)(Louis)
-   Number of metastasis compared to tumor type(Cora)
-   corellation of TMB to metastasis, mutation(), cancer type(Francesc, Maxence)
-   comparison number of mutations and IMPACT version(Francesc)
-   Kind of mutation to TMB, Metastasis(Maxence)
-   Kind of Mutations numbers(Maxence)

# New TODOs:

-   get data script, download data from web and clean(louis), into raw and data folder

-   bar plot: numbers of mutation, but stacked with kind of mutation(Louis data set)

-   
