# Extracellular Vesicle (EV) RNA-Sequencing

## Processed EV RNA-Seq Totals

|  |  |  |  |
| --- | --- | --- | --- |
| **Cohort** | **Baseline** | **Month 12** | **Month 24** |
| PDBP | 354 | 355 | 353 |

Bulk Neuron-derived extracellular vesicle (NDEVs) RNA experiments were conducted from plasma samples from 360 participants within PDBP. Sequencing data was processed with GENCODE version 45 and harmonized with the existing whole blood data.

## Plasma RNA Isolation

Neuron-derived extracellular vesicles (NDEs) were isolated from 800μL of plasma using NeuroDex’s proprietary ExoSORT procedure. Briefly, plasma samples are thawed on ice and centrifuged to remove lipids and debris. Next, samples were transferred to isolation tubes and diluted with plasma diluent and precipitated with NeuroDex’s Total Extracellular Vesicle Isolation Buffer. Pellets were resuspended in Binding buffer and incubated overnight with Magnetic beads with NeuroDex proprietary antibodies against GAP43 and NLGN3 at 4°C.  The Following day, the beads were washed three times, and 150μL of RPL lysis buffer from Qiagen’s miRNeasy Serum/Plasma Advanced Kit (cat: 217204) was used to lyse the samples.  The samples were then processed for RNA isolation according to the manufacturer's instructions, including on-column DNase treatment (Cat: 79254), using Qiagen’s RNase-Free DNase Set as instructed. The final RNA elution was performed using 16μl of DNase- and RNase-free water.

### Bulk EV exRNA Experiment Pilot Documentation

*“For each of 18 plasma subject samples, 1mL of plasma was thawed at room temperature, then immediately moved to ice. RNA was then isolated with Qiagen’s miRNeasy Serum/Plasma Kit (Qiagen, Cat. No. 217184) using a modified protocol to include an on-column DNase treatment (Qiagen, Cat. No. 79256).*

*For each of 169 plasma subject samples, 1mL of plasma was thawed at room temperature, then immediately moved to ice. RNA was then isolated with Norgen Biotek’s Plasma/Serum Circulating and Exosomal RNA Purification Mini Kit - Slurry Format (Norgen Biotek, Cat. No. 51000) with DNase treatment (Norgen Biotek, Cat. No. 25720).*

*For each plasma pool, 5mL of plasma provided in 200𝛍L aliquots was thawed at room temperature then immediately moved to ice. All aliquots were pooled together, gently mixed, and re-aliquoted into five 1mL aliquots. RNA was then isolated from each 1mL plasma aliquot with Norgen Biotek’s Plasma/Serum Circulating and Exosomal RNA Purification Mini Kit - Slurry Format (Norgen Biotek, Cat. No. 51000) with DNase treatment (Norgen Biotek, Cat. No. 25720). Isolated RNA across all five aliquots was then pooled together, gently mixed, and re-aliquoted evenly across 5 microcentrifuge tubes.”*

### Small EV exRNA Experiment Pilot Documentation

*“For each of the plasma subject samples, 1mL of plasma was thawed at room temperature, then immediately moved to ice. RNA was then isolated with Norgen Biotek’s Plasma/Serum Circulating and Exosomal RNA Purification Mini Kit - Slurry Format (Norgen Biotek, Cat. No. 51000) with DNase treatment (Norgen Biotek, Cat. No. 25720).”*

## EV Plasma RNA Whole Transcriptome Library Preparation & Sequencing

For each plasma RNA sample, a uniquely dual-indexed, Illumina-compatible, double-stranded cDNA whole transcriptome library was synthesized from up to 2ng of total plasma RNA with Takara Bio’s SMART-Seq Stranded Kit Components (Takara Bio, Cat. No. 634492) and SMARTer RNA Unique Dual Index Kit (Takara Bio, Cat. No. 634452 & 634457). Briefly, this library preparation included RNA fragmentation (94 °C for 2 min), a 5-cycle Indexing PCR, ribosomal cDNA depletion, and a 16-cycle enrichment PCR. Each library was measured for size with Agilent’s High Sensitivity D1000 ScreenTape and buffer (Agilent, Cat. No. 5067-5584 & 5067-5603). 1μL of each library was combined into a non-equimolar pool which was then measured for size and concentration via TapeStation, diluted to 90 pM, then loaded into an iSeq flowcell cartridge (Illumina, Cat. No. 20031371) with a 1% v/v PhiX Control v3 spike-in (Illumina, Cat. No. FC-110-3001), and sequenced at 101 x 8 x 8 x 101 cycles. Passing filter cluster counts per library were generated from this data and used to make a re-balanced pool which was subsequently measured for size and concentration, diluted to 2 nM with a 1% v/v PhiX Control v3 spike-in, denatured and further diluted, loaded into a NovaSeqX flow cell cartridge (Illumina, Cat. No. 20104706), and sequenced at 100 x 8 x 8 x 100 cycles with standard workflow and a final flow cell concentration of 180 pM. Libraries were sequenced to at least 50M read pairs (or 100M paired-end reads).

## Workflows

### Bulk RNA-Seq Workflow Documentation (Pilot Study)

### Salmon

*“**Salmon** is a method for quantifying transcript abundance from RNA-seq reads that is RNA Strandaccurate and fast. Salmon uses new algorithms to provide accurate expression estimates quickly while using little memory. Salmon performs its inference using an expressive and realistic model of RNA-seq data that takes into account experimental attributes and biases commonly observed in real RNA-seq data.*

Salmon v0.11.3

      Options: quant

      --libTypeA

      --threads 16 --numBootstraps 100

      --seqBias --gcBias

      --dumpEq --geneMap

      --gencode.v29.primary\_assembly.annotation.gtf

### STAR

***STAR** (Spliced Transcripts Alignment to a Reference) aligns high-throughput long and short RNA-seq data to a reference genome using uncompressed suffix arrays. STAR is a stand alone software capable of aligning reads in a continuous streaming mode. It is able to detect canonical junctions, non-canonical splices and chimeric transcripts and to map full-length RNA sequences.*

STAR v2.6.1d

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

### featureCounts

***featureCounts** is a read summarization program suitable for counting reads generated from either RNA or genomic DNA sequencing experiments. The program is developed for counting reads to genomic features such as genes, exons, promoters and genomic bins.”*

Feature Counts v1.6.2

      Options:

      --T 2 -p  -t exon  -g gene\_id

      --a gencode.v19.annotation.patched\_contigs.gtf

      --s 2

### UMI-tools

UMI-tools allows for the flexible removal of UMI sequences from fastq reads. UMI sequences are appended to the fastq read names

umi\_tools v1.1.4

      Options: extract

      -I FASTQR2 —bc-pattern=NNNNNNNN

      --stdout=FASTQR2\_processed.fastq.gz

      --read2-in=FASTQR1

      --read2-out=FASTQR1\_processed.fastq.gz

### Salmon

Salmon is a method for quantifying transcript abundance from RNA-seq reads that is RNA Strandaccurate and fast. Salmon uses new algorithms to provide accurate expression estimates quickly and while using little memory. Salmon performs its inference using an expressive and realistic model of RNA-seq data that takes into account experimental attributes and biases commonly observed in real RNA-seq data.

Salmon v1.10.1

      Options: quant

      --libTypeA

      --threads 20 --numBootstraps 100

      --seqBias --gcBias

      --dumpEq --geneMap

      --validateMappings

      --gencode.v29.primary\_assembly.annotation.gtf

### STAR

STAR (Spliced Transcripts Alignment to a Reference) aligns high-throughput long and short RNA-seq data to a reference genome using uncompressed suffix arrays. STAR is a stand alone software capable of aligning reads in a continuous streaming mode. It is able to detect canonical junctions, non-canonical splices and chimeric transcripts and to map full-length RNA sequences.

STAR v2.7.10b

      Options:

      --genomeDir STARREF --runMode alignReads

      --genomeLoad NoSharedMemory --quantMode TranscriptomeSAM

      --twopassMode Basic —alignTranscriptsPerReadNmax 50000

      --outFileNamePrefix SAMPLEID --readFilesCommand zcat

      --readFilesIn FASTQR1 FASTQR2

      --outSAMtype BAM Unsorted

      --outFilterType BySJout --outFilterMultimapNmax 20

      --outFilterMismatchNmax 999

      --outFilterMismatchNoverLmax 0.1 --alignIntronMin 20

      --alignIntronMax 1000000 --alignMatesGapMax 1000000

      --alignSJoverhangMin 8 --alignSJDBoverhangMin 18

      --chimOutType WithinBAM --chimSegmentMin 18

      --chimJunctionOverhangMin 18 --runThreadN 16

      --outSJfilterOverhangMin 18 18 18 18

      --outSAMmode Full --outSAMunmapped Within

### featureCounts

featureCounts is a read summarization program suitable for counting reads generated from either RNA or genomic DNA sequencing experiments. The program is developed for counting reads to genomic features such as genes, exons, promoters and genomic bins.

Feature Counts v2.0.6

      Options:

      --T 10 -p  -t exon  -g gene\_id

      --a gencode.v45.primary\_assembly.annotation.gtf

      --s 2

## Total Cell-Free RNA-Sequencing Pilot Study

Within AMP PD, there’s already whole blood transcriptomic data, so an interesting question that could also be addressed is “what information do the cells release?” which led to this exRNA pilot. Extracellular RNA is interesting because there is a lot of information released by cells when exposed to stressors or other environmental factors. In this pilot study, samples from the BioFIND cohort were used to conduct bulk RNA and small RNA processing experiments.

### Bulk exRNA Experiment

Bulk exRNA experiments were conducted from matching plasma and CSF samples from 185 participants. Sequencing data was processed with two different annotations – VG29 and VGLN. GENCODE version 29 was used and VG29 is harmonized with the existing whole blood data. In addition, samples were also processed using GENCODE version 29 with additional LNCIPEDIA version 5.2 annotation (VGLN) that adds in additional long non-coding RNAs.

### RNA Isolation

Kits that isolated all extracellular RNA were utilized for this experiment – total extracellular RNA preparation. Samples were then processed in the same way as the existing AMP PD whole blood transcriptomics samples.

**CSF RNA Isolation**
For each CSF subject sample, 1mL of CSF was thawed on ice. RNA was then isolated with Qiagen’s miRNeasy Serum/Plasma Kit (Qiagen, Cat. No. 217184) using a modified protocol to include an on-column DNase treatment (Qiagen, Cat. No. 79256).

For each CSF pool, 5mL of CSF provided in 200uL aliquots was thawed on ice, then pooled together, gently mixed, and re-aliquoted into five 1mL aliquots. RNA was then isolated from each 1mL CSF aliquot with Qiagen’s miRNeasy Serum/Plasma Kit (Qiagen, Cat. No. 217184) using a modified protocol to include an on-column DNase treatment (Qiagen, Cat. No. 79256). Isolated RNA across all five aliquots was then pooled together, gently mixed, and re-aliquoted evenly across 5 microcentrifuge tubes.

**Plasma RNA Isolation**
For each of 18 plasma subject samples, 1mL of plasma was thawed at room temperature, then immediately moved to ice. RNA was then isolated with Qiagen’s miRNeasy Serum/Plasma Kit (Qiagen, Cat. No. 217184) using a modified protocol to include an on-column DNase treatment (Qiagen, Cat. No. 79256).

For each of 169 plasma subject samples, 1mL of plasma was thawed at room temperature, then immediately moved to ice. RNA was then isolated with Norgen Biotek’s Plasma/Serum Circulating and Exosomal RNA Purification Mini Kit - Slurry Format (Norgen Biotek, Cat. No. 51000) with DNase treatment (Norgen Biotek, Cat. No. 25720).

For each plasma pool, 5mL of plasma provided in 200uL aliquots was thawed at room temperature then immediately moved to ice. All aliquots were pooled together, gently mixed, and re-aliquoted into five 1mL aliquots. RNA was then isolated from each 1mL plasma aliquot with Norgen Biotek’s Plasma/Serum Circulating and Exosomal RNA Purification Mini Kit - Slurry Format (Norgen Biotek, Cat. No. 51000) with DNase treatment (Norgen Biotek, Cat. No. 25720). Isolated RNA across all five aliquots was then pooled together, gently mixed, and re-aliquoted evenly across 5 microcentrifuge tubes.

### Whole Transcriptome Library Preparation

**CSF RNA Whole Transcriptome Library Preparation & Sequencing**
For each CSF RNA sample, a uniquely dual-indexed, Illumina-compatible, double-stranded cDNA whole transcriptome library was synthesized from all total RNA in 1mL of CSF with Takara Bio’s SMART-Seq Stranded Kit Components (Takara Bio, Cat. No. 634447) and SMARTer RNA Unique Dual Index Kit (Takara Bio, Cat. No. 634452 & 634457). A replicate of each CSF pool was prepared in parallel with every batch of subject CSF. Briefly, this library preparation included RNA priming (72 °C for 3 min), a 5-cycle Indexing PCR, ribosomal cDNA depletion, and a 16-cycle enrichment PCR.

Each library was measured for size with Agilent’s High Sensitivity D1000 ScreenTape and buffer (Agilent, Cat. No. 5067-5584 & 5067-5603) and concentration with KAPA SYBR FAST Universal qPCR Kit (Roche, Cat. No. KK4824). Two libraries did not produce quantifiable libraries and were not sequenced. Libraries were then combined into an equimolar pool which was also measured for size and concentration. The pool was then normalized to 2 nM with a 1% v/v PhiX Control v3 spike-in (Illumina, Cat. No. FC-110-3001), denatured and further diluted, loaded into a NovaSeq 6000 flow cell cartridge (Illumina, Cat. No. 20028313), and sequenced at 101 x 9 x 9 x 101 cycles with standard workflow and a final flow cell concentration of 400 pM. Libraries were sequenced to at least 50 M read pairs (or 100 M paired-end reads).

**Plasma RNA Whole Transcriptome Library Preparation & Sequencing**
For each plasma RNA sample, a uniquely dual-indexed, Illumina-compatible, double-stranded cDNA whole transcriptome library was synthesized from up to 2ng of total plasma RNA with Takara Bio’s SMART-Seq Stranded Kit Components (Takara Bio, Cat. No. 634447) and SMARTer RNA Unique Dual Index Kit (Takara Bio, Cat. No. 634452 & 634457). A replicate of each plasma pool was prepared in parallel with subject samples. Briefly, this library preparation included RNA fragmentation (85 °C for 2 min), a 5-cycle Indexing PCR, ribosomal cDNA depletion, and a 16-cycle enrichment PCR. Each library was measured for size with Agilent’s High Sensitivity D1000 ScreenTape and buffer (Agilent, Cat. No. 5067-5584 & 5067-5603). 1uL of each library was combined into a non-equimolar pool which was then measured for size via TapeStation and concentration via Roche’s KAPA SYBR FAST Universal qPCR Kit (Roche, Cat. No. KK4824), diluted to 70 pM, then loaded into an iSeq flowcell cartridge (Illumina, Cat. No. 20031371) with a 1% v/v PhiX Control v3 spike-in (Illumina, Cat. No. FC-110-3001), and sequenced at 101 x 8 x 8 x 101 cycles. Passing filter cluster counts per library were generated from this data and used to make a re-balanced pool which was subsequently measured for size and concentration, diluted to 2 nM with a 1% v/v PhiX Control v3 spike-in, denatured and further diluted, loaded into a NovaSeq 6000 flow cell cartridge (Illumina, Cat. No. 20028313), and sequenced at 101 x 9 x 9 x 101 cycles with standard workflow and a final flow cell concentration of 400 pM.Libraries were sequenced to at least 50M read pairs (or 100M paired-end reads).

### Small exRNA Experiment

Small exRNA experiments were conducted from the same plasma biosamples used in the bulk exRNA experiment, of which, 180 passed QC and have been released.

### RNA Isolation

For each of the plasma subject samples, 1mL of plasma was thawed at room temperature, then immediately moved to ice. RNA was then isolated with Norgen Biotek’s Plasma/Serum Circulating and Exosomal RNA Purification Mini Kit - Slurry Format (Norgen Biotek, Cat. No. 51000) with DNase treatment (Norgen Biotek, Cat. No. 25720).

### Small RNA Library Preparation and Sequencing

Plasma RNA samples were prepared for library generation with QIAGEN’s RNeasy MinElute Clean-up kit (74204), as follows: 5 ng of total RNA were treated with buffer RLT, and 100% ethanol. The sample was passed through a MinElute column, washed, dried, and RNA was eluted with ultra-pure water. Immediately after the clean-up, RNA was concentrated using a speed-vacuum centrifuge, and used for library preparation with Perkin Elmer’s NEXTFLEX Small RNA-Seq v3 and UDI barcodes (NOVA-5132-06). RNA was denatured at 70°C, and underwent 3’ adapter ligation for 2 hours at 25°C. NEXTFLEX Cleanup Beads were then used to remove excess free adapter, and the 5’ adapter was ligated for 1 hour at 20°C. cDNA was generated from the 3’ and 5’ ligated RNA, followed by a second bead clean-up, and finally PCR-amplified using UDI primers, for 18 cycles.
Libraries were size-selected and cleaned up using PAGE and the DNA Clean and Concentrate kit (Zymo, D4014). Briefly, samples were separated onto 6% PA gels, the band of interest was excised, and the gel piece was crushed and incubated in water overnight, with constant agitation. DNA binding buffer was added to precipitate the DNA, which was then applied to a column, washed, and eluted in ultra-pure water. Library size and concentration was determined via Agilent 2100 Bioanalyzer, using the High Sensitivity DNA kit.

Library pools were denatured with NaOH, and clustered onto flow cells at 14 pM, with 5% PhiX spike-in, using cBot instruments. Sequencing was carried out on Illumina’s HiSeq 2500 using TruSeq v3 reagents.

---

## Covered FAIRplex datasets

- **`amp-pd-transcriptomics-CSF-REBR`** (`amp_pdrd_0007`): CSF Tissue, RNA Extracellular Bulk Read, Version Gencode LNCipedia, Version Gencode 29
- **`amp-pd-transcriptomics-PLA-REBR`** (`amp_pdrd_0008`): Plasma Tissue, RNA Extracellular Bulk Read, Version Gencode LNCipedia, Version Gencode 29
- **`amp-pd-transcriptomics-PLA-RESR`** (`amp_pdrd_0009`): Plasma Tissue, RNA Extracellular Short Read

Source: [AMP-PDRD documentation](<https://amp-pdrd.org/data/EV-RNA-Seq>)
