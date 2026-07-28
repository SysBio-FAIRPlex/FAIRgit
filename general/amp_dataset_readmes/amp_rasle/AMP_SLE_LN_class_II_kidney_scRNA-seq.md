# AMP SLE LN class II kidney scRNA-seq

AMP SLE Phase II kidney 10x Genomics scRNA-seq dataset generated from 12 class II lupus nephritis (SLE) and 5 healthy control cases (Ctrl) from the AMP RA/SLE METRO team. Two biopsies were collected from control cases resulting in both kidney-A and kidney-B biopsy libraries for a total of 19 samples.

Sample counts:
**Biopsies** | **SLE** | **Control**
1 | 12 | 3
2 | 0 | 2

### Fastq files

This dataset includes two sets of fastq files: 10x Genomics Chromium GEX libraries and DASH-treated 10x Genomics Chromium GEX libraries where there original 10x GEX library was treated to remove abundant transcripts targeting 35 mRNA and 26 mitochondrial rRNA transcripts. several mito rRNA transcripts with lower expression (e.g., MT-ND5) were not targeted and which can still be used for downstream QC steps.

#### Note
- 10x GEX libraries include data for specimen `200-2752_SLE_kidney-A` but there is no corresponding DASH-treated library.
- Only a DASH-treated library is available for specimen `200-2736_SLE_kidney-A`

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=62408999>)
