# AbioticAraMicrobe

This repository includes raw data (Otu tables, Taxonomy and sequences of otus and metadata) and all the scripts were used to generate figures of the manuscript entitled: "Seasonality adaptation patterns of the natural Arabidopsis leaf microbiome over several plant generations are shaped by environmental factors"

manuscript is currently available as a preprint in [*bioRxiv*](https://doi.org/10.1101/2023.12.17.572047).

Scripts are written by [Maryam Mahmoudi](mailto:maryam.mahmoudi@uni-tuebingen.de).

Final figures and plots used in the manuscript are in :
Final_FigsAndTables/


# About amplicon sequencing data
Illumina-based amplicon sequencing (Miseq $2 \times 300$ cycle). Taxonomic markers included the bacterial 16S rRNA V5-V7 region, fungal ITS2, and 18S rRNA region of eukaryotes. 
Sequencing data are available under  [NCBI Bioproject PRJNA961058]()

# Step 1: Processing raw amplicon sequencing data
amplicon sequncing data were processed using  [Mothur (Version=1.42.3)](https://mothur.org)
 script for bacterial 16S rRNA V5-V7 region: [scripts/MothurCommands/Bacteria_mothur_pipline.sh)](https://mothur.org)
 script for fungal ITS2: [scripts/MothurCommands/Fungi_mothur_pipline.sh)](https://mothur.org)
 script for 18S rRNA region of eukaryotes: [scripts/MothurCommands/NonFungalEukaryotes_mothur_pipline.sh)](https://mothur.org)

 ### Outputs of step1 are in : data/MothurOutput

 #### Output files are : 

 For Bacteria : BV5Otu.txt, BV5Taxa.txt,  BV5.rep.fasta 

For Fungi : FITS2Otu.txt,	FITS2Taxa.txt, FITS2.rep.fasta	 

For non-fungal eukaryotes :  PrV9Otu.txt,	PrV9Taxa.txt, PrV9.rep.fasta

#### Description to output files: 

*Otu.txt files are Otu tables (abundance of each otu in samples)

*Taxa.txt files are taxonomy table per OTU 

*rep.fasta files are sequence of each otu


# Step 2: Cleaning OTU tables

 Description: Some preprocessing were done on each otu table (e.g., removing low read OTUs or Unclassified otus, etc.).
 
 This steps was done using this script: 
 scripts/RawOtuTablePreprocessing.ipynb 

 The output files were stored in data/DataClean

# Step 3: Extracting environmental factors from [terraclimate database](https://www.climatologylab.org/terraclimate.html).

Fourteen environmental factors used i this study (Fig. 1B) were extracted from terraclimate database. Environmental factors have monthly resolutions. Environmental factors of sampling months were extracted for each sampling locations 

In script called scripts/ExtractEnvironmentalDataFrom_terraclimatedata.ipynb steps are explaind.
This script will generate :
data/environmental_data.txt file and tables/tableS2_EnvironmentalFactors.csv

Which environmental_data.txt will use in analysis and tableS2_EnvironmentalFactors.csv is used as supplementary table.

 # Step4: Creating main figures of the manuscript (Note: some of the figurers generated by these scripts are further modified in other figure editors and final figures and tables are in the folder called: FigsAndTables)
note: some of the plots generated by these scripts are saved in the folder plots/ and tables in folder called tables/ 


  #### Figure1: []() is generated using script []()
  Figure1 panelA (sampling locations on map )  is generated using scripts/Fig1A_map.ipynb

  Figure1 PanelB,C and D are generated in other softwares.

  #### Figure2 Panel A an B: []() is generated using scripts/Fig2A_B_permanova_nmds.ipynb  []() and further modified in powerpoint ()
  Figure2 Panel C  is generated using scripts/SFig1_alpha_diversity.ipynb

  Figure2 Panel D: []() is generated using scripts/Fig2C_topGenus_abundances_compartments.ipynb []()

  #### Figure3 Panel A: []() is generated using scripts/Fig3A_heatmap_permanova_environmental_factors.ipynb []()
  Figure3 Panel B: []() is generated using scripts/Fig3B_heatmap_alpha_diversity_environmental_factors.ipynb []()

  
  #### To generate Figure4, first a linear model were done using:
   (scripts/Fig4_GeneratingLinearModels.ipynb)
 output of this step were used to generate the figure 4

  Figure4 (heatmaps): []() are generated using scripts/Fig4_Plot_GLM_Models.ipynb.ipynb []()

  #### Figure5 (generating microbial interaction networks files): 
  
  scripts/Fig5A_generating_microbialnetworks.ipynb[]() is generated using script []()
  This script were used to generate Fig5A (microbial network)

  Figure5 PanelB and C which shows the correlation of environmental factors and number of nodes in the networks: []() is generated using scripts/Fig5BC_NetworkEnvironmentalFactors.ipynb []()

Figure5 Panel D and E which shows the plots of cohesion across compartment and in correlation with environmental factors
is generated using scripts/Fig5_DE_AndSFig3_networkFeatures_environmentalFactors

 # Step3: Creating suplementary figures of the manuscript

   #### Suplementary_Figure1: []() is generated using scripts/SFig1_alpha_diversity.ipynb  []()

   #### Suplementary_Figure2: []() is generated using scripts/SFig2_EnvironmentalFactorsAcrossTimeAndSite.ipynb []()
 
   #### Suplementary_Figure3: []() is generated using scripts/Fig5_DE_AndSFig3_networkFeatures_environmentalFactors []()


 # Step4: Creating suplementary tables of the manuscript

 #### Table1.S1
 Contains number of samples per time point, locations and leaf compartments

 #### Table.S2
 Has information of the environmental factors
 
#### Table.S3 
Results of PERMANOVA to investigate individual environmental factors' impact on leaf compartments' microbial communities.
#### Table.S4: 
Results of modeling association of environmental factors and microbial genera.

#### Table.S5: 
Pearson correlation analysis results depicting the relationship between the number of nodes in microbial networks and the average environmental factors per sampling point.

   

   For any questions regarding the scripts or manuscript please contact:
   [Maryam Mahmoudi](mailto:maryam.mahmoudi@uni-tuebingen.de)