# Assignment-1
VEP Variant annotation using python
# CTX Bioinformatics Intern Assignment – Variant Annotation & Analysis

## Overview
This project demonstrates the analysis of annotated VCF files using **Ensembl VEP** (Variant Effect Predictor) and downstream processing in **Python (pandas)**.  
Two VCF files were annotated separately using VEP (human cache version 113, GRCh38 assembly), and then analyzed for variant-level and gene-level insights.

---

## Steps Performed

### 1. Variant Annotation with VEP
- VEP was installed locally.
- Human cache (GRCh38, version 113) was downloaded.
- Each VCF was processed separately using VEP:
  ```bash
  perl ensembl-vep/vep \
    --cache \
    --dir_cache /home/subhashree/Project/vep_cache \
    --species homo_sapiens \
    --assembly GRCh38 \
    --cache_version 113 \
    --offline \
    --tab \
    --everything \
    --force_overwrite \
    -i Input_data/test1_data_1.vcf \
    -o test1_data_1_vep.tsv

2. **Variant Annotation**
   - Ran VEP on both VCFs separately.
   - Generated output in **tab-delimited TSV** format.
   - Also saved **log files** and **annotated HTML reports** for each VCF.

3. **Data Processing and Analysis**
   - Opened a **Jupyter Notebook** for downstream analysis.
   - Imported the VEP output TSV files using **pandas**.
   - Cleaned the header and metadata lines.
   - Extracted:
     - Total number of variants
     - Unique genes
     - Unique traits/disease conditions (from the `PHENO` field)
     - Clinical significance (`CLIN_SIG`) distributions
     - Pathogenic and likely pathogenic variants
     - Per chromosome variant counts
     - Variants with and without dbSNP IDs (rsIDs)

4. **Output Organization**
   - Uploaded:
     - Cleaned and processed notebook (`.ipynb`)
     - VEP log files
     - Annotated HTML reports for both VCFs

---

## b. Approaches Taken
- Used **VEP with cache-based annotation** to ensure reproducibility and speed without requiring live API queries.
- Processed **each VCF independently** to maintain separation of results.
- Chose **pandas in Python** for downstream processing because:
  - Efficient handling of large tabular outputs from VEP.
  - Easy integration with Jupyter Notebook for interactive analysis.
- Focused on **clinically meaningful filters** such as `CLIN_SIG`, `PHENO`, and variant identifiers.

---

## c. Decisions Made
- **Cache-based VEP annotation** was chosen over live mode to avoid dependency on internet connectivity and ensure consistent results.
- **Separated analyses for each VCF** instead of merging, so results could be compared independently.
- Kept **summary-level outputs** (counts, unique values, distributions) in the notebook to provide clarity without overwhelming with raw data.
- Uploaded **HTML annotation reports** from VEP to preserve a detailed view of variants that complements the summary statistics.
- Organized results logically: variant-level summaries first (counts, rsIDs), then gene/trait-level insights, followed by clinical significance.

---

## Notes
- The **code** implementing these analyses is included in the Jupyter Notebook (`.ipynb`).
- The **raw annotation html outputs** and **log files** are available for verification.

