# AMP SLE CEL-Seq2

This dataset contains scRNAseq data on kidney tissue or urine from 34 individuals with or without Systemic lupus erythematosus.

**RNA sequencing and Processing**
scRNA-seq was performed using the CEL-Seq2 method. Paired-end sequencing of ~1 million paired-end reads per cell was performed on the HiSeq 2500. A modified version of the Drop-seq pipeline developed by the [McCarroll lab](http://mccarrolllab.com/wp-content/uploads/2016/03/DropseqAlignmentCookbookv1.2Jan2016.pdf) to produce gene by cell expression matrices of reads as well as unique molecular identifiers (UMIs). These steps include demultiplexing, quality filtering, polyA and adapter trimming, aligning, and collapsing reads with unique combinations of cell+gene+UMI. STAR-2.5.1b was used to align reads to the Hg19 human genome reference.

**Reference**
See [The immune cell landscape in kidneys of patients with lupus nephritis](https://www.nature.com/articles/s41590-019-0398-x) for more information about this dataset.

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=44288592>)
