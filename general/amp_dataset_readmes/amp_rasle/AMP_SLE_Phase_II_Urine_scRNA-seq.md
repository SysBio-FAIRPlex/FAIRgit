# AMP SLE Phase II Urine scRNA-seq

Multiplexed 10x Genomics Chromium 3' v3.1 scRNA-seq profiling cells collected from 338 urine samples from 155 SLE subjects. For several
subjects, urine samples were collected at multiple timepoints.

| Diagnosis | Subjects | Samples |
| :-: | :-: | :-: |
| SLE | 155 | 338 |

Each `libraryID` corresponds to one 10X GEM channel in which 8-12 samples were multiplexed. For many samples there were two
aliquots of cryopreserved urine cells. One aliquot was run initially, and if the yield was low then the other aliquot was
sequenced again in another library. Genotype-based demultiplexing methods are needed to separate cells by sample.

### Processed Data
This dataset includes Cell Ranger raw and filtered feature-barcode matrices and [demuxlet](https://github.com/statgen/demuxlet?tab=readme-ov-file#interpretation-of-output-files) results
are provided. A Seurat Object of the demultiplexed cell gene counts is available in an RDS file.

### Note
This dataset profiled samples collected from individuals that re-enrolled in the AMP RA/SLE program and which were
assigned new individualIDs upon re-enrollment. In total, 12 individualIDs listed in [`AMP-RA.SLE_PhaseII_urine.scRNA-seq.sample_meta.csv`](https://www.synapse.org/Synapse:syn63930511)
correspond to 6 unique subjects. This duplication corresponds to 15 total samples. The individualIDs in question can be
selected using `has_duplicateID` column.

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=63930514>)
