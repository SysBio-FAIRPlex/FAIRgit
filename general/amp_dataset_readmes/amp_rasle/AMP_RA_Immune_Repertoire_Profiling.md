# AMP RA Immune Repertoire Profiling

This is a multimodal dataset consisting of 5' CITE-seq (scRNA-seq + surface protein feature barcode sequencing) with TCR and BCR repertoire sequencing of pooled T and B cell populations sorted from synovial tissue (n=13) and matching PBMC (n=10) samples collected from [rheumatioid arthritis](http://purl.obolibrary.org/obo/DOID_7148) (RA) cases. This dataset includes raw fastq files and output from 10x Genomics Cell Ranger `counts` and `vdj` runs.

**Methods**
Cells collected from cell sorting were encapsulated into oil droplets using a Chromium NextGEM Chip G (10X Genomics). Following reverse transcription and cDNA amplification, 5’ gene expression, immune repertoire, and feature barcode libraries were constructed following manufacturer protocols (v1.1). The libraries were finally pooled for sequencing on an Illumina Novaseq 6000 using an S4 flow cell. Gene expression libraries were sequenced to obtain a read depth of 100,000 reads per cell, feature barcode libraries were sequenced at 5,000 reads per cell, and immune repertoire libraries were sequenced at 5,000 reads per cell. FASTQ file demultiplexing for gene expression libraries was performed using the mkfastq function in CellRanger (10X Genomics, v4.0). Following this, alignment to a reference genome (GRCh38) and counting was completed using the count function to generate expression matrices for each sample. Immune repertoire FASTQ files were separately demultiplexed, and the vdj function was used to perform sequence assembly and clonotype calling for TCR and BCR sequences in each

### Overview of libraries per subject biospecimen

|**individualID** | **PBMC** | **synovium**|
|:-:|:-:|:-:|
|300-0150|x|x|
|300-0171|x|x|
|300-0173|x|x|
|300-0174|x|x|
|300-0392|x|x|
|300-0410|x|x|
|300-0414|x|x|
|300-0415||x|
|300-0416||x|
|300-1883||x|
|300-1930|x|x|
|301-0174|x|x|
|301-0270|x|x|

**Associated Publication Datasets**
- [Clonal associations between lymphocyte subsets and functional states in rheumatoid arthritis synovium](https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=47217489)
- [Granzyme K+ CD8 T cells form a core population in inflamed human tissue](https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=29837062)

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=47090942>)
