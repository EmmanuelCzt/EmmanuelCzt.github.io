# A field guide for the non-coding genome explorer: Is this piece of non-coding DNA worth investigating?

Exploring the function of the non-coding genome in multicellular eukaryotes can feel like looking for a needle in a haystack with lots of straw strands looking like needles, thanks to enzymatic promiscuity[^1],[^2]. Biochemical activity is not enough to call for function and experimental validation of a sequence of interest can be tedious. Hence, deciding whether or not to investigate the function of a piece of DNA can be a daunting question and *because my supervisor says so* is never a good argument. 

Here is the distilled wisdom I have brewed over my Phd (2019-2023), for the bold, but not reckless, non-coding genome explorer. I hope the young explorer my find some value to it, while the seasoned explorer might find. In any case feel free to reach out if you have any questions or remarks

## Sequence and data mining 

1. **Are there nucleotides subjected to natural selection in your locus of interest?** Indeed, functional nucleotides contributes to the organism fitness and should be subjected to measurable natural selection. Nucleotide conservation or purifying selection, as measured by the phyloP score[^3] is available for humans and other flagship mammals on the UCSC genome [browser](https://genome.ucsc.edu/cgi-bin/hgTrackUi?hgsid=2466062763_y1pG5VqsjKr6wQc3K1a9xZa8jAaW&db=hg38&c=chr7&g=cons447way). If the fitness gain of your locus of interest kicked-in the last 5 million years or less it might be evolutionary too young to be detected by phyloP scores computed from the multiple sequence alignment of mammalian genomes[^3]. In that case checking population genomics data might be of interest interesting and can be done throught the gnomAD constraint scores also available as a genome browser track at [UCSC](https://genome.ucsc.edu/cgi-bin/hgTrackUi?hgsid=2466062763_y1pG5VqsjKr6wQc3K1a9xZa8jAaW&db=hg38&c=chr7&g=gnomadVariants).

2. **Is the region of interest linked to a trait?** The genetic architecture underlying some traits could be evolving near neutrality as they have recently evolved or because they do not contribute to organismal fitness. Once again, humans are data-rich, curated resources linking loci to traits like [Open Targets](https://www.opentargets.org/) or the [UK Biobank](https://www.ukbiobank.ac.uk/) can be mined when looking for candidates.

3. What is the **Transposable Elements content in your region of interest** relative to similar random regions? While *some* TE insertions are adopted by the genome it is unclear if it is the case for *most* TEs. If fact, the sequence of protein-coding genes, mostly evolving under purifying selection are depleted of TE insertions[^5]. Functional TE-born enhancers tend to be evolutionary older[^6] than evolutionary younger TE-born enhancers that shows no regulatory activity[^7]. It is not to say that, you should not investigate the function of TE-rich sequences, research on how TE insertions contributes to genome function and evolution is an exciting research area. However, diversifying your portofolios of candidates by balancing with TE-rich and TE-avarage or even poor candidates might be your best shot at getting results.

4. How does **the intensity of the biochemical activity over the region of interest range regarding the genome-wide distribution?** If your enhancer of interest has low chromatin accessibility signal or your long non-coding RNA of interest has a unique splicing pattern it could suggest a unique function. It could also indicates no function at all, just promiscuous enzymatic activity of RNA-polII. I'm not trying to discourage you to investigate the quirks of genomes, you should do it, but considering more classically looking candidates is a good way to mitigate the risk.

## High content reverse genetic approaches: Test them all, let the Omics sort them out

1. Massively parallel report assays test the potential of sampled candidate cREs to activate a minimal promoter. It streamlines the identification of active enhancers but does not directly tie them to their target genes.

2. Perturb-Seq: perturbations are induced by targeting the CRISPRi tech to gene promoters or candidate cREs and outputs are measured using scRNA-Seq to create rich genotype-phenotype maps to streamline the interpretation of complex phenotypes as well as the functional interrogation of thousands of non-coding targets at once. It is, however, highly expensive currently, since to have enough statistical power ~100 cells per perturbation or sgRNA are required. If we target 100 genes with 2 sgRNAs per promoter, we should sequence 20,000 cells which currently cost ~4,700$ (for the 10X Genomics sequencing platform).

3. CRISPRi-FlowFISH couples CRISPRi targeting of every regulatory candidate of a locus with the staining of the targeted RNA using oligos probes and then FAC sorting, allowing for the efficient and robust coupling of regulatory elements with their target genes. However, only the regulatory network of targeted genes can be investigated.

4. Recently, an imaging-based technique has been developed to screen for signaling pathways regulating the genome's 3D folding; however, only one locus is used as a reporter and performing whole genome HiC is prohibitively expensive for a screen setup. Hence, high-content screening strategies for the 3D genome remain to be developed.



[^1]: [The physical basis and practical consequences of biological promiscuity](https://iopscience.iop.org/article/10.1088/1478-3975/ab8697)
[^2]: [Functional Long Non-coding RNAs Evolve from Junk Transcripts](https://www.cell.com/cell/abstract/S0092-8674(20)31244-7)
[^3]: [Detection of nonneutral substitution rates on mammalian phylogenies](https://genome.cshlp.org/content/20/1/110)
[^4]: [Identification of constrained sequence elements across 239 primate genomes](https://doi.org/10.1038/s41586-023-06798-8)
[^5]: [Volatile evolution of long noncoding RNA repertoires: Mechanisms and biological implications](https://www.sciencedirect.com/science/article/pii/S0168952514001346?via%3Dihub)
[^6]: [Mammalian evolution of human cis-regulatory elements and transcription factor binding sites](10.1126/science.abn7930)
[^7]: [Functional evaluation of transposable elements as enhancers in mouse embryonic and trophoblast stem cells](https://doi.org/10.7554/eLife.44344)