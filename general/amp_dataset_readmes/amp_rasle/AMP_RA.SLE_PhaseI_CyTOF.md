# AMP RA.SLE PhaseI CyTOF

AMP RA/SLE Phase I CyTOF of PBMC samples profiling marker panels targeting T cells, B cells, and myeloid cells and total leukocyte (TL) samples profiling marker panels targeting TLs and PMN cells.

## PBMCs

The 79 PBMC samples were processed in a total of 5 mass cytometry batches, with the batches run within a span of 14 days. Batches had balanced numbers of samples from controls, RA patients, and SLE patients. Each PBMC sample was stained with panels for T cells, B cells, and myeloid cells. Panel markers are described in [AMP Phase 1 PBMC Antibody Panels.xlsx](https://www.synapse.org/#!Synapse:syn26324624).

Patient type count:
| **Control** | **OA** | **RA** | **SLE** |
| :--: | :--: | :--: | :--: |
| 18   |   7  |  27 |  27 |

### Reference
See [PD-1hiCXCR5– T peripheral helper cells promote B cell responses in lupus via MAF and IL-21](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6824311/) for more information about this dataset.

## Total Leukocytes

47 total leukocyte (TL) samples stained with a 36 parameter TL panel and 36 parameter PMN panel.

Patient type count:
**Control** | **RA** | **SLE**
| :--: | :--: | :--: | :--: |
10 | 13 | 24

Normalized and debarcoded FCS files were normalized and debarcoded with the standalone Matlab packages. These data files need their channels annotated (refer to marker panels described in [TL and PMN panel.xlsx](https://www.synapse.org/Synapse:syn26324383))

Normalized, debarcoded, pre-gated for live cells FCS files were uploaded to Cytobank and gated for the following parameters:
- Singlets – residual vs DNA (these gates were tailored by sample)
- Bead negative – residual vs 140Ce
- Live cells – residual vs 195Pt (cisplatin), set signal cutoff at 101

---

Source: [ARK Portal dataset page](<https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=61917712>)
