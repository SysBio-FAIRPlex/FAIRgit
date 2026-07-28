# AMP SLE C1-HT scRNA-Seq

This dataset contains scRNAseq on kidney and skin tissue from 23 individuals with or without systemic lupus erythematosus.

### Sample processing and sequencing
Single-cell suspensions at a concentration of 200,000 cells/ml and no less than 2,000 cells were loaded into a medium diameter C1 HT 800-well integrated microfluidic chip (IFC) (Fluidigm) and processed according to the Fluidigm C1 HT protocol revision A using the recommended standard mRNA-seq reagents and program.  The chip is divided into two 400-well sections allowing for loading of skin and kidney samples matched by individual on the same chip. Pre-amplified cDNA libraries were tagmented and barcoded using the Nextera XT Library Preparation Kit (Illumina) with indexing according to the Fluidigm C1 HT protocol revision A. An enrichment primer to select for the 3’ ends was added during this step. PCR-products originating from up to 800 cells per chip were pooled together using the 20 barcodes recommended by Fluidigm, and sequenced paired-end using the Illumina NextSeq500. Read 1 was sequenced 30 cycles and Read 2 120 cycles. Single FASTQ files corresponding to up to 800 cells were demultiplexed into 20 FASTQ files by separating reads based on the Illumina Nextera index primers. Each of the 20 FASTQ files represents a single column (up to 40 cells) on the Fluidigm C1 HT IFC and was further demultiplexed into single-cell FASTQ files using a Perl script provided by Fluidigm. Resulting FASTQ files were then trimmed using cutadapt (version 1.12) in nextseq mode followed by polyA trimming

### Reference
See [Tubular cell and keratinocyte single-cell transcriptomics applied to lupus nephritis reveal type I IFN and fibrosis relevant pathways](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6584054/) for more information about this dataset.

### Change log
- A corrupted fastq file was identified and removed from the dataset along with the corresponding R1 fastq file

- specimenID information was added to `AMP-SLE_C1-HT_mRNA-Seq_biospecimen_metadata.csv` file for 46 specimenID missing from Release 1.0

### Known Issues
- Conflicting specimenID and specimenType labels identified in metadata for six specimenID

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=44288868>)
