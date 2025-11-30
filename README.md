# group23_project

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

-   Add cleaning into Importing_raw_data script(louis), add merging and then load into data folder

    -   load merged data Sample+Patient+ Impact, SV , Mutation

    -   changing analysis scripts to load data in scripts

-   bar plot: numbers of mutation, but stacked with kind of mutation(Louis data set)

-   data description in read-me+ clean up

-   mutation analysis of glioma samples(Maxence)

-   do analysis on subset of cancer type = glioma(Cora, Louis, maybe Romane)

-   structure github

    -   do requirements of course

    -   add contributions in readme

Potential analysis:

-   Gene level enrichment(are certain genes more often mutated than others)

-   Map genes to functional pathways

-   correlation tmb vs mutation of specific genes

# Presentation:

1.  Introduction to our data(give background)(cancer data, study, data formats in the 5 files)
2.  Material(Francesc) with Impact
3.  Overview over data, general plots
4.  Patient information(age distribution, sex, number of patients, etc)(barplot age &sex stacked)+ survival rate
5.  SV+most mutated gene+most present in Glioma
6.  Network based on glioma
