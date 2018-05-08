# 3301 QIIME SCRIPTs
This repository contains the QIIME scripts needed to replicate our 16S rRNA analysis of soil samples from Gordon Square Park or another geographical site as decribed in the 'Materials and Methods' and 'Results' sections of our paper. 

FASTAQ sequencing files, along with the mapping file containing all sample metadata, were uploaded to the SURFsara high performance computer cluster Cartesius and analysed using QIIME. All scripts used in analysis are shown below. The first part of each script describes the cluster resources required to run to script (#SBATCH) which is followed by the QIME python script. Scripts were created in .pbs files and submitted using the code 'sbatch'. Further details of the QIIME scripts used in analysis can be found on the QIIME website (http://qiime.org). 

Joined Paired Reads - the join_pair_reads.py script joins the pair reads in the sequencing file.

Split libraries - the split_libraries.py script is used for demultiplexing and quality filtering.

Filter OTUs by sample - the filter_samples_from_otu_table.py is used to filter samples from the OTU sample - this script was used to remove 3 anomylous samples that were not taken from Gordon Square Park. 

Core diversity analysis - combines several QIIME diversity analyses scripts together to form a basic workflow beginning with a BIOM table, mapping file and phylogentic tree. Subscripts included in the workflow include summarize_taxa_through_plots.py, alpha_rarefaction.py, beta_diversity_through_plots.py, make_distance_boxplots.py, compare_alpha_diversity.py, and group_significance.py.

Make Heatmap - the make_heatmap_.py script was to produce a heatmap of samples grouped according to a variable (in our case, pH) and coloured by intensity according to their relative abundance

Compare categories (ANOSIM method) - the compare_categories.py script tests whether two or more groups of samples are significantly different based on a categorical variable (e.g. K+, P and N levels) found in the metadata mapping file.

