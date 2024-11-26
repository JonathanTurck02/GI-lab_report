### DNA Isolation and Sequencing

The fecal samples were collected from both groups and were stored at -80 °C before being shipped on dry ice to the Gastrointestinal Laboratory of Texas A&M University, College Station, Texas. The microbial DNA from fecal samples was extracted and quantified using the DNeasy PowerSoil Pro Kit (QIAGEN Inc, Germantown, Maryland) and the Thermo Scientific NanoDrop Microvolume Spectrophotometers respectively.
The Nextera XT DNA Library Preparation Kit (Illumina Inc., San Diego, CA, USA) was used for sequencing library preparation, followed by pooling of the libraries. Afterward, SPRI bead purification and concentration were performed with SpeedBeads Magnetic Carboxylate Modified Particles (Cytiva Life Sciences, Marlborough, MA, USA). The pooled libraries were denatured using NaOH, diluted, and spiked with 2% PhiX. Sequencing was carried out on an Illumina NovaSeq6000 with a 2x150 flow cell to achieve a median of 2 million read pairs at the Diversigen laboratory (New Brighton, MN). The data were converted to FASTQ files and filtered for low-quality (Q-score <30) and short lengths (<50) sequences. Adapter sequences were removed, and all remaining sequences were trimmed to a maximum length of 100 base pairs before proceeding with the alignment process. Raw sequence data were uploaded to the NCBI Sequence Read Archive and analyzed using established pipelines. For taxonomic classification, FASTA sequences were aligned to a curated database containing all representative prokaryotic genomes from the NCBI RefSeq collection, as well as additional manually curated bacterial strains. Alignments were performed at 97% identity and compared with reference genomes. Taxonomy assignment was based on the lowest common ancestor approach, with compatibility to at least 80% of the reference sequences. Operational Taxonomic Units (OTUs) with fewer than one million species-level markers, or with less than 0.01% unique genome region matching and less than 0.1% of the entire genome, were discarded.
The normalized and filtered data tables were then imported into QIIME2 for subsequent downstream analysis. Prior to conducting diversity analyses, samples were rarefied to depth of  64000, ensuring uniform depth for analysis.



---

### Statistics

Statistical analysis was conducted to test the hypothesis that there is a difference in the fecal microbiome between the two groups. Data were tested against the hypothesis of normal distribution by conducting the Shapiro-Wilk’s test using GraphPad Prism v10.0.2 (GraphPad Software, Inc., La Jolla, CA, USA). The data did mainly follow a normal distribution. However, due to the zero inflated and compositional nature of microbiome data, non-parametric methods were applied.

Statistics on the Shannon, Chao1, and Observed Features indices were performed using Mann-Whitney tests. All alpha diversity statistical analyses were performed in GraphPad Prism v10.0.2 (GraphPad Software, Inc., La Jolla, CA, USA).

To quantify the dissimilarity in microbial structure between groups, a non-parametric ANOSIM (analysis of similarities) was performed on the Bray-Curtis distance matrix in Quantitative Insights Into Microbial Ecology 2 (QIIME2 2024.2). Groups were defined based on the individual’s respective treatment and the time point at collection. To compute p-values, 999 permutations were calculated, and pairwise comparisons were performed against baseline. The significance level was set at a p-value of <.05, and the Benjamini-Hochberg method was used to correct for multiple comparisons.

Differential abundance analysis between the groups was identified using Composition of Microbiomes with Bias Correction (ANCOM-BC) at phylum, family, genus, species, and strain levels. Briefly, data obtained from QIIME2 (v2024.05) was imported into R statistical software v4.2.3 (R Core Team, 2020) with the R package ANCOMBC (v 2.2.0) and phyloseq (v3.20) package.

Identified significant taxa were visualized using GraphPad Prism v10.0.2 (GraphPad Software, Inc., La Jolla, CA, USA).

A stacked relative abundance table on a phylum level was created utilizing R statistical software v4.2.3 (R Core Team, 2020) with the phyloseq v3.20 package.
