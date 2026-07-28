# AMP RA Synovium Bulk RNA-seq

AMP RA Phase I synovium low-input bulk RNA-seq data as described in [Defining inflammatory cell states in rheumatoid arthritis joint synovial tissues by integrating single-cell transcriptomics and mass cytometry](https://doi.org/10.1038/s41590-019-0378-1). Samples from 40 rheumatoid arthritis (RA) and 14 osteoarthritis (OA) patients where synovial tissue was collected by either arthroplasty or biopsy, cells were dissociated and FACS used to collect populations of B cells, T cells, fibroblasts, and monocytes for each sample, generating 192 bulk RNA-seq samples. Dataset includes raw fastq files, processed gene counts, and biospecimen metadata.

Count of patient type by synovial collection procedure:
|  | ** Arthroplasty** | **Biopsy**|
| **OA** | 14 | 0 |
| **RA** | 19 | 21|

Count of sequenced cell types by patient type:
|  | **B cells** | **fibroblasts**| **monocytes**| **T cells**|
| **OA** | 10 | 13 | 14 | 14 |
| **RA**  | 29 | 37 | 38 | 37 |

### Library Prep and Read Alignment
Full-length cDNA and sequencing libraries were performed using Illumina Smart-Seq2 protocol. Libraries were sequenced on MiSeq from Illumina to generate 35 base paired-end reads. Reads were mapped to Ensembl version 83 transcripts using kallisto 0.42.4 and summed expression of all transcripts for each gene to get transcripts per million (TPM) for each gene.

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=61879003>)
