# group_23_project

## Project Contributors:

-   s250823 : benklerc

-   s253698: FrancescCalabuig

-   s253730: MaxenceMarbouty

-   s253729: L0uisP

-   s243419: roms02

## Link to presentation

<https://raw.githack.com/rforbiodatascience25/group_23_project/main/doc/presentation.html>

## Data

Data was obtained from cBioPortal: <https://www.cbioportal.org/study/clinicalData?id=tmb_mskcc_2018>

5 files can be found on cBioPortal

## Description of .txt files

### data_clinical_patient.txt

This file contains the main informations of all the patients that were studied, it contains 6 columns, patient ID, sex, age at diagnosis, drug received, the "survived month" and their overall status (alive or dead, at the time of the check up). From this data set it is possible to look at the survival rate of the patients and see if different factors such as the medication or the age may have an impact on the survival rate.

### data_clinical_sample.txt

This files contains information about the specific samples like cancer type, sample site, measurements on how clean the sample was and how many cancer cells were found per sample. There is one sample per patient. This file also contains the specific age of the patient at the time when the sample was taken.

### data_gene_panel_matrix.txt

This file describes the IMPACT version used to identify mutations and structural variants for each patient. Three panel versions are available: IMPACTv_3 (341 genes), IMPACTv_5 (410 genes), and IMPACTv_6 (468 genes).

### data_mutations.txt

This file describes different gene mutations and indicator for more than 20000 samples. Here's a detail explanation of all the variables implied in this table:

#### Explanation of the variables

| Column name | What it is |
|------------------------------------|------------------------------------|
| Hugo_Symbol | The **Name** of the gene. |
| Entrez_Gene_Id | The gene's unique **ID number**. |
| Chromosome | The specific chromosome where the mutation occurred |
| Start_Position | The first base pair coordinate of the mutation on the chromosome. |
| End_Position | The last base pair coordinate of the mutation. (Often the same as `Start_Position` for single-base changes). |
| Strand | Indicates whether the gene is read on the positive (`+`) or negative (`-`) strand of the DNA double helix. |
| Center | The institution or center that submitted the sequencing data (e.g., `MSKCC` for Memorial Sloan Kettering Cancer Center). |
| NCBI_Build | The specific version of the human genome reference sequence used for mapping (e.g., `GRCh37` is a common older version). |
| Transcript_ID | The ID of the specific mRNA transcript (from the gene) that was analyzed. |
| RefSeq | The reference sequence accession number for the transcript, used for high-quality sequence reporting. |
| Reference_Allele | The normal (wild-type) base(s) found at this position in the reference genome. |
| Tumor_Seq_Allele1 | The first DNA sequence read from the tumor sample. (Often the reference allele, especially if it's a heterozygous mutation). |
| Tumor_Seq_Allele2 | The second DNA sequence read from the tumor sample, which is often the mutated allele. |
| Variant_Type | Describes the physical nature of the change: **SNP** (Single Nucleotide Polymorphism - one base changed), **DEL** (Deletion), **INS** (Insertion), etc. |
| Variant_Classification | Describes the functional impact of the mutation on the gene's function: `Missense_Mutation` (changes one amino acid), `Nonsense_Mutation` (creates a stop signal), `Frame_Shift_Del` (shifts the reading frame). |
| Consequence | A technical, detailed description of the mutation's location and effect (e.g., `missense_variant`, `splice_region_variant`). |
| HGVSc | HGVS notation describing the change at the **c**DNA level (e.g., `c.839G>A`). (The **Code Change** in the mRNA message.) |
| HGVSp | HGVS notation describing the change at the protein level (e.g., `p.Arg280Lys`). This shows which amino acid was changed and what it became. |
| HGVSp_Short | A short version of the protein change (e.g., `p.R280K`). |
| Protein_position | The position number of the amino acid affected in the protein sequence. |
| Codons | The triplet of DNA bases that codes for the amino acid, showing the change (e.g., `Cgg/Tgg`). |
| t_ref_count | The number of times the **reference** allele (normal base) was observed in the **tumor** sample reads. |
| t_alt_count | The number of times the **alternate** allele (mutant base) was observed in the **tumor** sample reads |
| n_ref_count | The number of times the **reference** allele was observed in the matched **normal** (non-tumor) sample reads. |
| n_alt_count | The number of times the **alternate** allele (mutant base) was observed in the matched **normal** sample reads. |
| Mutation_Status | Indicates if the mutation is **SOMATIC** (acquired in the tumor, not inherited) or **GERMLINE** (inherited and present in all cells). Somatic is expected in cancer data. |
| Validation_Status | Indicates if the mutation was confirmed by a secondary method (like an independent test). `Unknown` means it was not specifically validated. |
| dbSNP_RS | The identifier (rs ID) from the **dbSNP** database if this change is a known polymorphism in the general population. If this is present, the mutation might not be cancer-specific. |
| Hotspot | A simple flag (`0` or `1`) indicating if this specific amino acid position is known to be frequently mutated across many cancer types. |
| ALLELE_NUM | The numerical index for the alternate allele (used internally in some formats). |
| IS_NEW | Indicates whether this specific mutation was previously seen in the MSK-IMPACT cohort. |
| Score | A general quality score or ranking of the mutation, which can vary depending on the analysis pipeline. |
| Tumor_Sample_Barcode | A unique, standardized identifier that links that specific mutation event back to the original tissue sample taken from a specific patient. |

### data_sv.txt

This file describes 347 structural variants (SV) detected in tumor sample, with 30 columns. Most of the columns provide genome-focused details that might not be relevant to our analysis. But if we need to look more closely at specific variants, this file gives access to sequencing information such as type of SV, region of breakpoint and more.

Main information from the file, description:

-   Site1 / Site2 columns describe the two breakpoints of a Structural Variant (gene, region, position).
-   Class, Breakpoint_Type, Connection_Type describe the type of SV.
-   Event_Info, Annotation, Comments give biological context.
-   Read counts help assess detection quality and confidence.

Detailed information for each column with examples can be found in the description_data_sv textfile.

# Structure

project/

**raw/tmb_msckcc_2018**

Contains all the imported raw files:

data_clinical_patients.txt\
data_clinical_sample.txt\
data_gene_panel_matrix.txt\
data_mutation.txt\
data_sv.txt\

**data/**

Contains the saved cleaned and merged files:

data_mutation_cleaned.tsv\
patient_sample_gen_panel.tsv\
sv_cleaned.tsv\

**R/**

Contains the Quarto script for loading, cleaning, analysis...

ex: 00_all.qmd\
\
**results/**

Contains the Rendered scripts in html

ex: 00_all.html\
\
**results/figures/**

Contains the figures saved for the presentation

ex: EGFR_count_per_cancer.png\
\
**doc/**

The folder with the presenattion slides

presentation.qmd\
presentation.html\
styles.css

.gitignore

└── README.md

# Instructions to Run

order of run:

1.  01_load.qmd : To load the data into raw
2.  02_clean_qmd : To clean the .txt files
3.  03_augment.qmd : merging some files and saving the files in data
4.  individual analysis:
    1.  04_01_data_clinical_patient_analysis.qmd : description and investigation on the Clinical Patients file
    2.  04_02_data_clinical_sample_analysis.qmd : description and investigation on the Clinical Sample file
    3.  04_03_data_mutations_analysis.qmd : description and investigation on the Mutations file
    4.  04_04_gene_panel_mutation.qmd : description and investigation on the gene panel mutation file
    5.  04_05_sv_class_analysis.qmd : description and investigation on the Structural variants file
5.  05_Survival_rate_parameter_analysis.qmd : analysis on merged between clinical patients and sample files
6.  06_mutation_types.qmd : analysis on merged between sample and mutation files
7.  07_EFGR_SV_analysis.qmd : analysis specified of the EGFR gene (Glioma cancer)
8.  08_Cox_Regression.qmd
9.  09_gene_enrichment_analysis.qmd

00_all.qmd can run all the files
