# Transcriptomics Data

AMP PD has RNA Fastq and workflow products from Salmon, Star, and Feature Counts for BioFIND, PDBP, and PPMI cohorts. All RNA Sequencing was performed by [Hudson Alpha](https://hudsonalpha.org/) at **150 base pairs**, and is supplied along with corresponding clinical data.

### Processed RNA-Seq Totals

| Cohort | Baseline | Month 0.5 | Month 06 | Month 12 | Month 18 | Month 24 | Month 30+ | Totals |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| BioFIND | 0 | 208 | 0 | 0 | 0 | 0 | 0 | 208 |
| HBS | 726 | 0 | 20 | 625 | 111 | 486 | 180 | 2148 |
| PDBP | 1466 | 0 | 574 | 614 | 506 | 471 | 0 | 3631 |
| PPMI | 1,522 | 0 | 853 | 873 | 0 | 833 | 541 | 4622 |
| Totals | 3,714 | 208 | 1,447 | 2,112 | 617 | 1,790 | 721 | 10,609 |

## Library Preparation and Protocol Details for BioFIND, PDBP, and PPMI Cohorts

All BioFIND, PDBP, and PPMI RNA samples were normalized to 30ng/ul. Depending on the available material, input amounts of RNA used in the rRNA and globin reduction step ranged from 684-752 ng of RNA. All products were used following the manufacturer's directions except where noted. All samples underwent rRNA and globin reduction via the [Illumina Globin-Zero Gold kit](https://www.illumina.com/products/selection-tools/rrna-depletion-selection-guide.html) (catalog number GZG1224).  Following RNA reduction, stranded libraries were prepared by first-strand synthesis and second strand synthesis using the [New England Biolabs (NEB) Ultra II First Strand Module](https://www.neb.com/products/e7771-nebnext-ultra-ii-rna-first-strand-synthesis-module#Product%20Information) (catalog number E7771L) followed by the [NEB Ultra II Directional Second Strand Module](https://www.neb.com/products/e7550-nebnext-ultra-directional-rna-second-strand-synthesis-module#Product%20Information) (catalog number E7550L).

Following second strand synthesis, the double-stranded cDNA was converted to a sequencing library by standard, ligation-based library preparation. The following NEB modules were used, in order:

1. [NEB End Repair Module](https://www.neb.com/products/e6050-nebnext-end-repair-module#Product%20Information) (catalog number E6050L)
2. [NEB A-tailing Module](https://www.neb.com/products/e6053-nebnext-da-tailing-module#Product%20Information) (catalog number E6053L) and
3. [NEB Quick Ligation Module](https://www.neb.com/products/e6056-nebnext-quick-ligation-module#Product%20Information) (catalog number E6056L)

Each of the modules was scaled back 1:2 from the recommended enzyme concentrations using the appropriate buffers. Following ligation to standard Illumina paired-end adaptors, each library was amplified for 12 cycles of PCR using [Roche Kapa HiFi polymerase](https://www.kapabiosystems.com/product-applications/products/pcr-2/kapa-hifi-pcr-kits/) (catalog number KK2612). Each forward and reverse PCR primer included an 8nt unique index sequence. After PCR, the insert sizes were evaluated via [Perkin-Elmer Caliper GX](https://www.perkinelmer.com/Product/24-labchip-gx-touch-cls138162).

Libraries were quantitated using the Roche Kapa SYBR FAST Universal kit (catalog number KR0389) and diluted to 2nM final stocks, pooled in equal molar amounts and sequenced on the [Illumina NovaSeq 6000](https://www.illumina.com/systems/sequencing-platforms/novaseq.html) platform to generate 100M paired reads per sample at 150 nt read lengths. Samples were demultiplexed based on the unique i5 and i7 indexes to individual sample FASTQ files.

## Library Preparation and Protocol Details for the HBS Cohort

All HBS RNA samples were sequenced by Discovery Life Sciences (DLS). The concentration and integrity of the total RNA were assessed using the Ribogreen assay (Invitrogen catalog number R11490) and the Fragment Analyzer (Agilent), respectively. For library preparation, approximately 500 ng of total RNA from each sample was processed using the [Illumina Stranded Total RNA Prep with Ribo-Zero Plus kit](https://www.illumina.com/products/by-type/molecular-biology-reagents/ribo-zero-plus-rrna-depletion.html) (catalog number 20040529), following the manufacturer’s protocol. The final library concentration was measured with the Invitrogen [Picogreen Assay](https://www.thermofisher.com/order/catalog/product/P7589?SID=srch-srp-P7589) (catalog number P7589), and the library size was determined using a DNA High Sense chip on a PerkinElmer [LabChip Gx](https://www.revvity.com/product/ht-dna-1k-12k-hi-sens-labchip-760517) (catalog number 760517). Accurate quantification of the final libraries for sequencing was performed with the Roche qPCR-based [KAPA Biosystems Library Quantification kit](https://rochesequencingstore.com/catalog/kapa-library-quantification-kit/?attribute_options=Illumina-Rox+Low+%5B500rxn%5D) (catalog number 7960336001). Sequencing was conducted using a 2x150 PE setup on the Illumina NovaSeq 6000 instrument (Illumina), generating approximately 100 million paired-end (PE) reads per sample, totaling 200 million reads.

## Using HBS with BioFIND, PDBP, and PPMI Cohorts

HBS RNASeq sample collection and handling followed protocols similar to previously released AMP PD RNASeq data. Workflow processing and QC followed identical protocols using the same workspaces and notebooks that were used four years earlier.

There are differences in the library preparation between the HBS RNASeq data and the previously released RNASeq data. Researchers should pay close attention to these differences.:

|  |  |  |
| --- | --- | --- |
|  | **HBS RNASeq (2024)** | **AMP PD RNASeq (2020)** |
| **Input RNA** | 500 ng | 684-752 ng |
| **Ribo/Globin reduction** | Ribo-Zero Plus | Globin-Zero Gold |
| **Library Preparation** | Illumina Stranded Total RNA Prep with Ribo-Zero Plus | NEBNext Stranded Ultra II + Roche KAPA HiFi polymerase |

While the Ribo-Zero Plus kit has changed to support globin reduction since its publication, this paper provides relevant details on discrepancies between the methods [RNA-Seq of human whole blood: Evaluation of globin RNA depletion on Ribo-Zero library method](https://www.nature.com/articles/s41598-020-62801-6/figures/2).

## Workflows

*[Image omitted: RNA Strand]*

1. **Salmon** is a method for quantifying transcript abundance from RNA-seq reads that is accurate and fast. Salmon uses new algorithms to provide accurate expression estimates quickly and while using little memory. Salmon performs its inference using an expressive and realistic model of RNA-seq data that takes into account experimental attributes and biases commonly observed in real RNA-seq data.
2. **STAR** (Spliced Transcripts Alignment to a Reference) aligns high-throughput long and short RNA-seq data to a reference genome using uncompressed suffix arrays. STAR is a stand alone software capable of aligning reads in a continuous streaming mode. It is able to detect canonical junctions, non-canonical splices and chimeric transcripts and to map full-length RNA sequences.
3. **featureCounts** is a read summarization program suitable for counting reads generated from either RNA or genomic DNA sequencing experiments. The program is developed for counting reads to genomic features such as genes, exons, promoters and genomic bins.

[Access the RNASeq Workflows](https://github.com/amp-pd/amp-pd-workflows/tree/master/rna)

## Transcriptomics Processing & Sequencing Strategy

1. Develop a comprehensive RNA resource from whole blood samples that can be **easily accessed and utilized by researchers**
2. Choose methods to comprehensively profile the samples for researchers to **interrogate genes, pathways, and mechanisms** that play a role in disease
3. Approach and sequencing strategy should **enable scientific inquiries and data analysis into the future with broad applicability**
4. Organize the data in a way that will be **accessible to a wide range of investigators** - from investigators that have the ability to download and analyze the raw files to researchers that do not have significant bioinformatics capabilities

## Transcriptomics Research Data Dictionary

If you want to download a version of the full AMP PD Transcriptomics Research Data Dictionary, click one of the buttons below for a specific format.

[RNA-seq Data Dictionary (pdf)](https://amp-pdrd.org/index.php/sites/default/files/2020-05/AMP_PD_Transcriptomics_Data_Dictionary.pdf)

[RNA-seq Data Dictionary (excel)](https://amp-pdrd.org/index.php/sites/default/files/2020-05/AMP_PD_Transcriptomics_Data_Dictionary.xlsx)

## Data Analysis & Processing

Transcript abundance were estimated using two pipelines. First, Transcripts Per Million transcripts (TPMs) were generated using Salmon pipeline directly from FASTQ files on Gencode29. Second, counts per gene were generated by counting aligned reads from STAR generated BAMs onto B38 of the human genome.

## Salmon v0.11.3

        Options: quant
        --libTypeA
        --threads 16 --numBootstraps 100
        --seqBias --gcBias
        --dumpEq --geneMap
        --gencode.v29.primary\_assembly.annotation.gtf

## STAR v2.6.1d

         STAR --genomeDir STARREF --runMode alignReads
        --twopassMode Basic\
        --outFileNamePrefix SAMPLEID --readFilesCommand zcat\
        --readFilesIn FASTQL1 FASTQL2
        --outSAMtype BAM SortedByCoordinate\
        --outFilterType BySJout --outFilterMultimapNmax 20\
        --outFilterMismatchNmax 999
        --outFilterMismatchNoverLmax 0.1\
        --alignIntronMax 1000000 --alignMatesGapMax 1000000\
        --alignSJoverhangMin 8 --alignSJDBoverhangMin 1\
        --chimOutType WithinBAM --chimSegmentMin 15\
        --chimJunctionOverhangMin 15 --runThreadN 16\
        --outSAMstrandField intronMotif
        --outSAMunmapped Within\
        --outSAMattrRGline RGTAGLIST

## Feature Counts v1.6.2

        Options:
        --T 2 -p  -t exon  -g gene\_id
        --a gencode.v19.annotation.patched\_contigs.gtf
        --s 2

## Transcriptomics Quality Control Approach

AMP PD Transcriptomics data goes through a series of quality control steps prior to making the data available to researchers. This QC process is motivated by a philosophy that encompasses the following principles:

- **Eliminate samples that are fundamentally unusable**
  - An example of an unusable sample is one that has contamination (sample partially matches with two unrelated participants).
- **Annotate samples that are difficult to use**
  - An example of a sample that is difficult to use is one that has a low number of reads, is an outlier (PCA analysis), or moderate contamination.
- **Publish and make available metrics about all samples**
  - Metrics are available in GCS and BigQuery

Following these principles, AMP PD transcriptomics data goes through a series of quality control checks, some of which will result in samples and all derived data being withheld from the published dataset (with potential of being made available in a future release). Other checks will result in annotations being provided in a table for researchers.

Also under consideration is adoption of a method similar to the [ENCODE project](https://academic.oup.com/nar/article/46/D1/D794/4595865): *Red = a critical issue was identified in the data, Orange = a moderate issue was identified in the data, Yellow = a mild issue was identified in the data.*

## RNASeq

## Proof of Concept

As part of the Transcriptomics quality control process, a pilot program was designed to test and validate sequencing methods.

*[Image omitted: RNA-Pilot Step 1]*

#### Pilot Design & Sample Collection

Samples obtained from [Indiana University](https://www.biosend.org/), [Tel Aviv](http://yoran.tau.ac.il/nlgip/) and [BioRep](http://www.biorep.it/en). Whole blood was collected in PaxGene  tubes,  RNA isolated using PaxGene blood miRNA kit  (total RNA isolation), and DNase treated.

*[Image omitted: 2]*

#### Pilot Objectives

Test potentially variability across sites, varying RNA Integrity Number (RIN) (average RIN in PPMI is 7.2), sample preparation methods and read depth.

*[Image omitted: 3]*

#### Pilot Test Setup

Tested kits that would provide the greatest transcript diversity including transcripts without poly(A) tails (circRNA, IncRNA, splicing patterns, splicing junctions,  etc.). All kits tested had: globin depletion, rRNA depletion, and stranded: 1) NED/Kapa; 2) Swift; and 3) TruSeq.

*[Image omitted: RNA-Pilot Step 4]*

#### Pilot Conclusions

NED/Kapa provided high transcript diversity, high correlations, and worked well with HAIB automation. At 100 M read pairs new gene detection reached a plateau. Use of UMI showed a 28% duplication rate.

## Transcriptomics Quality Control Process

Quality control checks were performed for **8,670 RNASeq samples** for AMP PD. The subsections below describe at a high level what checks were executed as part of the RNASeq QC process.

[RNASeq Decision Tree](https://amp-pdrd.org/index.php/transcriptomics-data/rnaseq-decision-tree)

## Concordance Checks

Validation that RNA samples are correctly associated with participants

- **Sex Check:** a sex check has been used during processing of samples to ensure that at a coarse level we have properly identified samples. In the end, the sex check is superceded by the SNP check against genomic data
  **Key Checks:**
  **(1)** All RNA samples sex determined for comparison against clinically reported sex
  **(2)** Does the RNA sample expression level for sex-linked genes match the clinically reported sex for the individual
- **All RNA samples genotype comparison to WGS samples**
  **Key Checks:**
  **(1)** Does RNA sample match the WGS sample for that individual
  **(2)** Does the RNA sample match a WGS sample for a different individual
- **All RNA samples genotype comparison against all RNA samples**
  **Key Checks:**
  **(1)** Does the RNA sample match other samples for the same individual
  **(2)** Does the RNA sample match samples for other individuals

## Mismatched Samples Check

RNA SNP Checks Match Against Genomic SNPs. AMP PD has [whole genome sequencing](https://amp-pdrd.org/whole-genome-data) data (WGS) for most participants. We compared the genotypes for a set of SNPs against the transcriptomic expression.

- Samples that fail to match WGS for the same participant\_id were removed from AMP PD for later evaluation
- If an RNA sample has no associated WGS sample and passes the sex check, but does not match other RNA samples for the individual, then the sample was removed from AMP PD for later evaluation

## Duplicate Samples Check

- **Matched against own WGS data and matched against other WGS data:** Sample is genetically identical to their own WGS sample as well as a WGS sample with a different participant\_id
- **Matched against own RNA data and matched against other RNA data:** Sample is genetically identical to expected RNA sample and to RNA sample(s) with a different participant\_id

## Post-Alignment Quality Check

- **Quant Based PCA** - PCA of salmon output to identify outliers for potential re-analysis, resequencing, or even re-prepping from new samples
- **Count Based PCA**
  - Query and reshape feature counts BigQuery data into a count matrix (genes=rows, sampleID=columns, value=value ie counts). This count matrix coupled with metaData table was used to create a DESeqDataSet or dis object using DESeq2
  - Source: <http://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.html>

---

## Covered FAIRplex datasets

- **`amp-pd-transcriptomics-WB-RWTS`** (`amp_pdrd_0006`): Whole Blood Tissue, RNA Whole Transcriptome Sequence and RWTS Pools

Source: [AMP-PDRD documentation](<https://amp-pdrd.org/index.php/transcriptomics-data>)
