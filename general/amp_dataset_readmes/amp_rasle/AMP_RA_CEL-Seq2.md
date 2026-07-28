# AMP RA CEL-Seq2

This dataset contains scRNAseq data on the synovium from 58 individuals with Rheumatoid arthritis or Osteoarthritis.

**RNA sequencing and Processing**
scRNA-seq was performed using the CEL-Seq2 method. Paired-end sequencing of ~1 million paired-end reads per cell was performed on the HiSeq 2500. A modified version of the Drop-seq pipeline developed by the [McCarroll lab](https://doi.org/10.1186/s13059-016-0938-8) to produce gene by cell expression matrices of reads as well as unique molecular identifiers (UMIs). These steps include demultiplexing, quality filtering, polyA and adapter trimming, aligning, and collapsing reads with unique combinations of cell+gene+UMI. STAR-2.5.1b was used to align reads to the Hg19 human genome reference.

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=47606568>)
