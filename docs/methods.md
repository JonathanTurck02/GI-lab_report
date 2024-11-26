### DNA Isolation and Sequencing

Fecal samples were collected from both groups and stored at -80 °C before being shipped on dry ice to the Gastrointestinal Laboratory of Texas A&M University, College Station, Texas. Microbial DNA from the fecal samples was extracted and quantified using the DNeasy PowerSoil Pro Kit (QIAGEN Inc., Germantown, Maryland) and the Thermo Scientific NanoDrop Microvolume Spectrophotometers, respectively.

For sequencing library preparation, the Nextera XT DNA Library Preparation Kit (Illumina Inc., San Diego, CA, USA) was utilized before pooling the libraries. Following pooling, SPRI bead purification and concentration were performed using SpeedBeads Magnetic Carboxylate Modified Particles (Cytiva Life Sciences, Marlborough, MA, USA). The pooled libraries were denatured with NaOH, diluted, and spiked with 2% PhiX before sequencing on the Illumina NovaSeq6000 using a 2x150 flow cell to target a median of 2 million read pairs. Sequencing was performed at Diversigen Laboratory (New Brighton, MN).

Post-sequencing, FASTQ files were filtered for low quality (Q-score <30) and short lengths (<50 bp). Adapter sequences were trimmed, and all sequences were truncated to a maximum length of 100 bp prior to alignment. Raw sequences were submitted to the NCBI Sequence Read Archive for storage and later analyzed using established pipelines.

For taxonomic classification, FASTA sequences were aligned to a curated database containing representative genomes from the NCBI RefSeq genome collection for prokaryotes, supplemented with manually curated bacterial strains. Alignments were conducted at 97% identity and compared to reference genomes. Taxonomy was assigned to the lowest common ancestor, provided that ≥80% of the reference sequences matched. Operational Taxonomic Units (OTUs) accounting for fewer than one million species-level markers, or OTUs with <0.01% of their unique genome regions or <0.1% of the whole genome matching, were excluded.

For downstream analyses, normalized and filtered data tables were imported into QIIME2. To ensure uniform analysis depth, samples were rarefied to match the sequence count of the sample with the lowest number of sequences prior to diversity analysis.

---

### Statistics

Statistical analysis was conducted to test the hypothesis that the fecal microbiome differed between the two groups. Data were tested for normality using the Shapiro-Wilk test in GraphPad Prism v10.0.2 (GraphPad Software, Inc., La Jolla, CA, USA). While most data conformed to a normal distribution, the zero-inflated and compositional nature of microbiome data necessitated non-parametric methods.

Alpha diversity indices (Shannon, Chao1, and Observed Features) were analyzed using Mann-Whitney tests in GraphPad Prism. To assess dissimilarity in microbial structure between groups, a non-parametric ANOSIM (analysis of similarities) was performed on the Bray-Curtis distance matrix in QIIME2 2024.2. Groups were defined by treatment and collection time points. Statistical significance was computed using 999 permutations with pairwise comparisons against baseline. A significance level of *p* < .05 was applied, and Benjamini-Hochberg correction was used for multiple comparisons.

To analyze differential abundances of ASVs and taxonomies, ANCOM-BC2 (Analysis of Composition of Microbiomes with Bias Correction 2) from the ANCOMBC R package v2.2.0 was employed. Data from QIIME2 (v2024.05) was imported into R statistical software v4.2.3 using the phyloseq v3.20 package.

Significant taxa between groups were identified at the phylum, family, genus, species, and ASV levels. These taxa were further plotted and analyzed in GraphPad Prism. Dunnett's multiple comparisons test was used to compare significant taxa across time points within each group, while Šídák's multiple comparisons test identified differences between treatment and control groups at each time point.

A stacked relative abundance table at the phylum level was generated using R with the phyloseq package for visualization.
