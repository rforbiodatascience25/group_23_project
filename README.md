# group23_project

## Description of .txt files

### data_clinical_patient.txt

### data_gene_panel_matrix.txt

### data_mutations.txt

### data_sv.txt
This file describes 347 structural variants (SV) detected in tumor sample, with 30 columns. Most of the columns provide genome-focused details that might not be relevant to our analysis. But if we need to look more closely at specific variants, this file gives access to sequencing information such as type of SV, region of breakpoint and more.

## Quick summary:

- Site1 / Site2 columns describe the two breakpoints of a Structural Variant (gene, region, position).
- Class, Breakpoint_Type, Connection_Type describe the type of SV.
- Event_Info, Annotation, Comments give biological context.
- Read counts help assess detection quality and confidence.

Detailed information for each column with examples can be found in the description_data_sv textfile.

