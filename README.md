# SZ-paper-data
This repository contains processed expression data and differential expression analysis (DEA) results derived from **GSE119291** platform **GPL25480**.
## File Descriptions
### GEO_source_info.csv
Sample-level metadata for GSE119291
Includes:
- Sample_geo_accession (GSM ID)
- Sample_source (hiPSC_control / hiPSC_SZ)
- Sample_perturbagen (drug name or DMSO)
- Sample_dosage
- Sample_batch

---

### GSE119291-GPL25480_raw_matrix.csv
Raw L1000 expression matrix downlowded from GSE119291.
- Rows: probe IDs
- Columns: GEO sample accessions

---

### annot_expr_mat.csv
Annotated expression matrix with samples' perturbagens overlap with drugs of interest.

- Columns: samples retained after drug filtering
- Rows: mapped gene identifiers where available  
  (Mapping was performed using hgu133plus2.db package; unmapped probes are retained as probe IDs)

---

### DEA_hiPSC_control.csv
Differential expression analysis results for **hiPSC_control** samples. 
The linear model was fitted using the limma framework with `~ batch + drug`, DMSO was used as the reference condition.
Final result was filtered by p< 0.05 for statistical significance.

Rows:
Each row corresponds to a **probe–drug** comparison against **DMSO**.

Columns:
- PROBEID: probe IDs
- drug: perturbagen name
- logFC: log fold change (drug vs DMSO)
- adjP: Benjamini–Hochberg adjusted p-value
- direction: Up / Down regulation
- gene_id: gene identifier mapped from probe ID

---

### DEA_hiPSC_SZ.csv
Differential expression analysis results for **hiPSC_SZ** samples. 
The linear model was fitted using the limma framework with `~ batch + drug`, DMSO was used as the reference condition.
Final result was filtered by p< 0.05 for statistical significance.

Rows:
Each row corresponds to a **probe–drug** comparison against **DMSO**.

Columns:
- PROBEID: probe IDs
- drug: perturbagen name
- logFC: log fold change (drug vs DMSO)
- adjP: Benjamini–Hochberg adjusted p-value
- direction: Up / Down regulation
- gene_id: gene identifier mapped from probe ID


