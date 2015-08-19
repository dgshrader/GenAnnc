# Phylogenetic Trees

We're building phylogenetic trees for SAGs and GFMs for each of the following lineages:
- betI (Lhab and Rhodo)
- betII (Pnec)
- betIV (LD28)

### Selection of Reference Genomes
SIGS requests that genome announcements include a phylogenetic tree indicating the placement of new sequences. These three lineages correspond to the following taxonomic groups:
- betI - genera Limnohabitans and Rhodoferax, family Comamonadaceae
- betII - genus Polynucleobacter, family Burkholderiaceae
- betIV - genus Methylotenera, family Methylophilaceae

For each lineage, all finished genomes belonging to the indicated genus were downloaded from IMG. For the betII lineage, environmental genomes from the same family were also downloaded. Finally, the following incomplete genomes were also downloaded:
- betI - 3 draft genomes from Lhab and Rhodo
- betII - 2 draft genomes from Pnec
- betIII - draft genomes from Methylotenera

Each lineagae has the following number of reference genomes:
- betI - 4
- betII - 8
- betIV - 13

### Building Phylogenetic Trees
Each tree contains three groups of genomes: reference genomes, our samples, and outgroups. Reference genomes (```refGenomes```) and samples (```SAGsandGFMs```) are found in the ```genomes``` folder, grouped by lineage. See below for discussion of outgroups.

Trees are built as follows:  
1. For each genome, contigs are concatenated into a continuous alignment (```01FastaSequenceMerger.pl```)  
2. Phylosift extracts marker genes from each genome (```02RunPyhlosift.pl```)  
3. For each genome, marker genes are concatenated into a continuous alignment (```03CreateAlignmentFile.pl```). The concatenated alignment should be called ```lineage.aln```, where lineage is betI, betII, or betIV.  
4. Construct an approximate maximum-likelihood phylogenetic tree using FastTree. Call this tree ```lineageFastTree.nwk```. If the tree looks good ...  
5. Constuct a maximum-likelihood tree using RAxML using 100 rapid bootstraps  
  ```./raxmlHPC-PTHREADS-AVX -f a -m PROTGAMMAAUTO -p 12345 -x 12345 -# 100 -s lineage.aln-msk -T 24 -n lineage```. RAxML will generate the following output files:  
    - ```RaxML_info.lineage``` - information about call to RAxML  
    - ```RAxML_bestTree.lineage``` - best ML tree  
    - ```RAxML_bipartitions.lineage``` - best ML tree with bootstrap support values. Suitable for viewing in ```FigTree``` or another program.  
    - ```RAxML_bipartitionsBranchLabels.lineage``` - same as above but with bootstrap values displayed as branch (instead of node) labels  
    - ```RAxML_bootstrap.lineage``` - contains all boostrap trees  

### Outgroups
Outgroups contain fully sequenced genomes from freshwater members of other beta-proteobacterial lineages. For each lineage, fully sequenced genomes are:
  - betI: ```Limnohabitans_sp_Rim28.fna``` and ```Limnohabitans_sp_Rim47.fna```
  - betII: ```Polynucleobacter_necessarius_asymbioticus_MWH-MoK4.fna```
  - betIV: ```Methylotenera_versatlis_301.fna```

For each lineage, use as outgroups the fully sequenced genomes from the other lineages.
