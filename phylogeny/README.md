# Phylogenetic Trees

We're building phylogenetic trees for each SAGs and GFMs for each of the following lineages:
- betI (Lhab and Rhodo)
- betII (Pnec)
- betIV (LD28)

Trees are built as follows:
1. Extract and align marker genes using phylosift
2. Mask alignment using GBlocks w/ default parameters
3. Build tree using RAxML w/ 100 rapid bootstraps

Genomes and Outgroups:
- reference genomes: 'refGenomes' folder for each lineage
- samples: 'SAGsandGFMs' folder for each lineage
- outgroups: for each lineage, use fully sequenced FW genomes from the other lineages
  - betI: Limnohabitans_sp_Rim28.fna and Limnohabitans_sp_Rim47.fna
  - betII: Polynucleobacter_necessarius_asymbioticus_MWH-MoK4.fna
  - betIV: Methylotenera_versatlis_301.fna
