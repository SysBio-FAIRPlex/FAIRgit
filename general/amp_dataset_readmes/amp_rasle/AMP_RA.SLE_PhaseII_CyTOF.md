# AMP RA.SLE PhaseII CyTOF

AMP RA/SLE Phase II single cell CyTOF data on PBMC samples profiling four panels and total leukocyte samples profiling one panel. Below is a count of debarcoded fcs files available for each panel split by patient type:

**Panel**|**At-Risk-RA**|**Control**|**RA**|**SLE**
B cell|62|40|115|235
Myeloid|58|40|106|210
NK cell|58|39|97|195
T cell|60|40|110|217
Granulocyte|61|40|68|154

### Granulocytes

323 TL samples were randomly distributed across 8 staining and data acquisition days (i.e., batches) at a rate of 40 samples per day and split across one panel targeting granulocytes with each batch broken into two groups of 20 barcoded samples.

- 1x106 cells were used per sample
- QC for granulocyte percentages < 15% = 75 samples eliminated
- QC for viability < 50% = 5 additional samples eliminated
- Granulocyte Pass QC = 243 samples.

QC data is available at [`AMP Phase II_Granunlocyte_QC.xlsx`](https://www.synapse.org/Synapse:syn26353144)

### PBMCs

452 PBMC samples were randomly distributed across 23 staining and data acquisition days  (i.e., batches) at a rate of 20 samples per day and split across four panels (B cell, T cell, Myeloid, NK cell). Note, the samples stained with one panel were barcoded together.

- If ≥3x106 cells = all 4 panels were stained at 0.75x106 cells per panel
- If between 2x106 and 3x106 cells – equal distribution of cells across panels
- If <2x106 – Panel priority (B > T > M > N) put in place (minimum = 0.5x106 cells)

## FCS files

Raw Data – FCS files as written by CyTOF acquisition software before any data processing was applied.

Debarcoded Data – FCS files that have been “cleaned” with the workflows outlined in [protocols.xlsx](https://www.synapse.org/Synapse:syn26353566) and are ready for downstream analysis. These files are the final version, have their proper AMP ID as their file name and a prefix for the panel they are stained with. Note, these files have not been gated for Doublets, EQ beads, or Dead cells.

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=52623570>)
