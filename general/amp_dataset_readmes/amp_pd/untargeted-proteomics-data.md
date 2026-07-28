# Untargeted Proteomics Data

Untargeted proteomics analysis was conducted on cerebrospinal fluid and plasma of both Parkinson's Disease patients and healthy participants in the PDBP and PPMI cohorts. Analysis was conducted using Data-Independent Acquisition mass spectrometry-based (“untargeted”) proteomics utilizing trap-collision based disassociation to measure fragment intensity (smaller portions of peptides) from processed peptide samples.  The method requires this fragment intensity to be combined to give peptide intensity and then peptide intensity is combined to give protein intensity data that can then be used in downstream analysis.

### Table 1. Total number of participants and samples run through mass spectrometry based untargeted proteomics, split by cohort (PDBP, PPMI) and tissue (Plasma, CSF).

|  |  | Participants | Samples |
| --- | --- | --- | --- |
| PDBP | Plasma | 128 | 522 |
|  | CSF | 139 | 524 |
| PPMI | Plasma | 179 | 949 |
|  | CSF | 481 | 2283 |

### Method

### Sample Preparation

#### **Cerebrospinal fluid (CSF)**

**CSF Protein Digestion** - Individual patient CSF samples and four CSF pooled samples from healthy individuals used as data control reads were processed on a Beckman i7 automated liquid handling system in 96-well plate format using a method modified from our previous published methods for plasma and depleted plasma.9-10 The figure below describes the main steps of the sample preparation protocol.

*[Image omitted: 1. Sample Duration and Reduction]*

*[Image omitted: 2. Sample Alkylation]*

*[Image omitted: 3. Sample Quenching]*

*[Image omitted: 4. Sample Dilution and Digestion]*

*[Image omitted: 5. Sample Quenching]*

1. CSF samples were denatured and reduced by incubating with agitation at 60°C for 60 minutes with 30 µL of 55% 2,2,2-trifluoro-ethanol (TFE, Sigma), 14mM Dithiothreitol (DTT, Sigma) and dissolve in 40mM NH4CO3 (Ammonium bicarbonate, Sigma).
2. Samples were alkylated by adding 10µL of 50mM iodoacetamide (IAA, Sigma) and incubated in the dark at room temperature for 30 minutes.
3. The alkylation was quenched by adding 10uL of 100mM DTT to samples followed by a 15-minute incubation with agitation at room temperature.
4. Sample solutions were diluted with 180µL of 100mM NH4CO3 to reduce TFE in solution concentration to ~6.5%. Samples were digested at 42°C for 4 hours in an Inheco incubator trypsin:protein ratio of 1:10.
5. Sample digestion was quenched by adding 10 µL of 12.5% formic acid

The final peptide digest volume in the well was 265 µL, which was immediately sealed with foil adhesive seals and stored at -80°C until thawed for LC-MS analyses. Given the undigested CSF sample aliquot volumes of 25 µL and total final peptide digest volumes of 265 µL, a dilution scheme was used to target a peptide load of 500 ng for each sample injection.

**Adding iRT Peptide Standards to CSF peptides**- To prepare samples for LC-MS processing, sample peptides were thawed at room temperature and spun down, and 53µL were diluted into a second 96-well plate with 47µL 0.1% formic acid in water. 20µL of diluted peptides were then transferred to wells of a PCR plate containing 20µL of diluted commercial indexed retention time peptide standards (iRT) (Biognosys[WK1] ®). iRT standards were prepared by serial dilution, first diluting one vial of iRT peptides with 1000µL of 0.1% formic acid in water, then adding 90uL of the previous dilution to 910uL of 0.1% formic acid in water.

**CSF Sample Desalting** - CSF sample/iRT peptide mixtures were then desalted by loading 20µL of the mixture onto Evotips (EVOSEP, C18 disposable trap columns).

#### **Plasma**

**Plasma Depletion** - Plasma samples were depleted using 96 well plate previously described by McArdle and Binek et al. (2022), in which 14 most abundant proteins including albumin, immunoglobulins A, E, G, and M, kappa and lambda light chains, alpha-1-acidglycoprotein, alpha-1-antitrypsin, alpha-2- macroglobulin, apolipoprotein A1, fibrinogen, haptoglobin, and transferrin using the High Select Top 14 Abundant Protein Depletion Camel Antibody Resin (Thermo Fisher Scientific).9

The McArdle and Binek et al., protocol was scaled to allow for aliquoting depletion resin into 96-well plates in batches of 2 plates. Briefly, after equilibrating depletion resin at room temperature, the resin was poured into a 25mL pipetting reservoir affixed to an in-house made, 3D printed vortex attachment and shaken at 800 rpm to maintain a homogeneous resin slurry for consistent bead concentrations in each well of the 96-well plates containing diluted plasma samples (10 µL plasma diluted with 90 µL ammonium bicarbonate).  Using a multichannel pipette, 300 µl of resin were added to all sample wells, and plates were sealed. Plates were then incubated in a plate shaker at 800 rpm for 1 hour at room temperature. Contents of the 96-well plates were then transferred to filter plates (Nunc) atop empty 96-well plates (Beckman Coulter), and the filter plate was sealed. The samples were then passed through the filter via centrifugation for 4 minutes at 100 rpm. Plates were then removed and rotated 180° then centrifuged for 4 minutes at 100 rpm. Resultant depleted proteins were then lyophilized via Speedvac and frozen at -80°C and stored until two more depleted plasma plates were ready for 4-plex tryptic digestion.

**Naïve Tryptic Digestion and Desalting** - Naïve plasma proteins were digested utilizing an automated sample preparation protocol. Naïve plasma tryptic peptide desalting was carried out using a positive pressure apparatus (Amplius Positive Pressure ALP, Beckman Coulter) mounted on the left side of the i7 workstation deck. The automated sample preparation protocol and desalting protocol are described by Fu et al. (2020).10

**Naïve plasma iRT Peptide Addition** – Naïve plasma peptides were combined 1:1 in MS vials with 1:20 diluted iRT peptides.

**Depleted Plasma Digestion, iRT Addition and Desalting** – Depleted plasma samples underwent the tryptic digestion procedure described by McArdle and Binek et al. (2022).9 Resultant peptides were further diluted (5 µL peptides with 120 µL 0.1% formic acid in H2O) then 25 uL of diluted peptides were spiked into 25uL of iRT standards (Biognosys®) that were diluted as described above for CSF Evotip loading. 20 uL of depleted plasma/iRT peptide mixtures were then desalted using Evotips.

### LC-MS Methods

#### EVOSEP One LC System with Orbitrap Exploris 480 MS for CSF and Depleted Plasma

Data independent acquisition (DIA-MS) was implemented by loading CSF sample peptides from Evotips onto an EVOSEP EV1106 Analytical Column (EVOSEP, C18 AQ, 1.9µm beads, 150µm ID, 15cm long with an EVOSEP One LC system). Samples were injected into an Orbitrap Exploris 480 mass spectrometer (ThermoScientific) with an average flow rate of 1.5 µl/min using the 30SPD EVOSEP method. The MS settings used for data acquisition are as follows: for Global MS Settings, expected LC peak width was set to 20 seconds and default charge state set at 2+. During the MS full scan data were collected in Profile form from 0 to 45 minutes over a scan range of 350-1400 m/z. Orbitrap resolution was set to 120k, while S-lens radio frequency was at 40%, normalized accumulated gain control (AGC) target was 300%, and maximum injection time was 45 milliseconds. DIA data were collected as Profile, scanning over a range of 200-1700 m/z with 50 isolation windows spanning 21 m/z with 1 m/z window overlap. Orbitrap resolution was 15k. Normalized collision energy was set to 28%, normalized AGC target was 100%, and maximum injection time was 22 milliseconds.

Depleted plasma tryptic peptides were separated by EVOSEP One LC System over a 45-minute gradient using the same column type as CSF and injected into an Orbitrap Exploris 480 MS using DIA-MS settings described by McArdle and Binek et al. (2022).9

#### Eksigent-415 LC System with Sciex Triple TOF 6600 MS for Naïve Plasma

Naïve plasma peptides were analyzed using the method described by Holewinski et al. (2016).11 Briefly, samples data were acquired over a 60-minute gradient using a Eksigent-415 microflow LC system coupled to a Sciex Triple TOF 6600. DIA-MS methods used 100 variable windows over a chromatographic gradient of 60 minutes in the 400–1200 m/z range.

### Data Processing

Raw data files were converted to profile mzML format using MSConvert for .raw conversion and Proteowizard for .wiff conversion.

Intensity data for peptide fragments was extracted from mzML files using the open source openSWATH workflow1 against the publicly available plasma library of the human twin population (February 2015) peptide assay library. Target and decoy peptides were then extracted, scored, and analyzed using the mProphet algorithm2 to determine scoring cut-offs consistent with a 1% false discovery rate (FDR). Peak group extraction data from each DIA file was combined using the “feature alignment” script, which performs data alignment and modeling analysis across an experimental data set3, and fragment-level data was normalized by MS2TIC.

Next, to obtain high-quality quantitative data, fragments from non-proteotypic peptides, i.e. peptides shared across different proteins4, were discarded. The large data set showed irregular patterns of missingness distribution, invoking the need for data filtering to discard fragments having ≥50% missingness across all three biological groups (done using metadata provided from the partial unblinding).

Technical bias from batching during digestion was corrected using comBat corrective technique5. In the case of CSF samples, this was followed by Random Forest (RF) imputation6. In the case of plasma, the depleted and native batch corrected data was combined at the fragment-level following the dual plasma workflow as specified in Zhang et al7.

The data was then processed using the mapDIA software8 to roll up fragment-level data to peptide and protein levels. CSF batch corrected and imputed files are provided. Plasma batch corrected files are provided.

## References

1. Röst, H. L.; Rosenberger, G.; Navarro, P.; Gillet, L.; Miladinović, S. M.; Schubert, O. T.; Wolski, W.; Collins, B. C.; Malmström, J.; Malmström, L.; Aebersold, R. OpenSWATH enables automated, targeted analysis of data-independent acquisition MS data. Nat. Biotechnol. 2014, 32, 219– 223,  DOI: 10.1038/nbt.2841
2. Reiter, L.; Rinner, O.; Picotti, P.; Hüttenhain, R.; Beck, M.; Brusniak, M. Y.; Hengartner, M. O.; Aebersold, R. mProphet: automated data processing and statistical validation for large-scale SRM experiments. Nat. Methods 2011, 8, 430– 435,  DOI: 10.1038/nmeth.1584
3. Röst, H. L.; Liu, Y.; D’Agostino, G.; Zanella, M.; Navarro, P.; Rosenberger, G.; Collins, B. C.; Gillet, L.; Testa, G.; Malmström, L.; Aebersold, R. TRIC: an automated alignment strategy for reproducible protein quantification in targeted proteomics. Nat. Methods 2016, 13, 777– 783,  DOI: 10.1038/nmeth.3954
4. Mallick P, Schirle M, Chen SS, Flory MR, Lee H, Martin D, Ranish J, Raught B, Schmitt R, Werner T, Kuster B, Aebersold R. Computational prediction of proteotypic peptides for quantitative proteomics. Nat Biotechnol. 2007
5. Sundararaman N,; Bhat A,; Venkatraman V,; Binek A,; Dwight Z,; Ariyasinghe NR,; Escopete S,; Joung SY,; Cheng S,; Parker SJ,; Fert-Bober J,; and Van Eyk JE. BIRCH: An Automated Workflow for Evaluation, Correction, and Visualization of Batch Effect in Bottom-Up Mass Spectrometry-Based Proteomics Data. Journal of Proteome Research, 2023 22 (2), 471-481, DOI: 10.1021/acs.jproteome.2c00671
6. Wright, M. N.; Ziegler, A. ranger: A Fast Implementation of Random Forests for High Dimensional Data in C++ and R. J. Stat. Softw. 2017, 77, 1– 17,  DOI: 10.18637/jss.v077.i01
7. Zhang S, Raedschelders K, Venkatraman V, Huang L, Holewinski R, Fu Q, Van Eyk JE. A Dual Workflow to Improve the Proteomic Coverage in Plasma Using Data-Independent Acquisition-MS. J Proteome Res. 2020 Jul 2;19(7):2828-2837.
8. Teo G, Kim S, Tsou CC, Collins B, Gingras AC, Nesvizhskii AI, Choi H. mapDIA: Preprocessing and statistical analysis of quantitative proteomics data from data independent acquisition mass spectrometry. Journal of proteomics. 2015 Nov 3;129:108-20.
9. Mc Ardle, A.;  Binek, A.;  Moradian, A.;  Chazarin Orgel, B.;  Rivas, A.;  Washington, K. E.;  Phebus, C.;  Manalo, D.-M.;  Go, J.;  Venkatraman, V.;  Coutelin Johnson, C. W.;  Fu, Q.;  Cheng, S.;  Raedschelders, K.;  Fert-Bober, J.;  Pennington, S. R.;  Murray, C. I.; Van Eyk, J. E., Standardized Workflow for Precise Mid- and High-Throughput Proteomics of Blood Biofluids. Clinical Chemistry 2022, 68 (3), 450-460.
10. Fu, Q.;  Johnson, C. W.;  Wijayawardena, B. K.;  Kowalski, M. P.;  Kheradmand, M.; Van Eyk, J. E., A Plasma Sample Preparation for Mass Spectrometry using an Automated Workstation. JoVE (Journal of Visualized Experiments) 2020,  (158), e59842.
11. Holewinski, R. J.;  Parker, S. J.;  Matlock, A. D.;  Venkatraman, V.; Van Eyk, J. E., Methods for SWATH™: data independent acquisition on TripleTOF mass spectrometers. Quantitative proteomics by mass spectrometry 2016, 265-279.

---

## Covered FAIRplex datasets

- **`amp-pd-proteomics-CSF-PDIA`** (`amp_pdrd_0010`): CSF Tissue, Proteomics Data Independent Acquisition, Native and Depleted, Samples and Aggregates

Source: [AMP-PDRD documentation](<https://amp-pdrd.org/index.php/data/untargeted-proteomics-data>)
