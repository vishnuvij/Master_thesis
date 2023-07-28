# Detection of false positive ortholog assignments using phylogenetic profiles

Master Thesis Proposal

Author - Vishnu Vijayan (00806007)


## Problem Introduction
The functional annotation of protein coding genes is crucial for investigating similarities but
also differences between related organisms. In the era of biodiversity genomics, an automated
transfer of functional annotations has increased in relevance because genomes of species are
being sequenced at a rapid pace that are both genetically but also phenotypically only poorly
characterized (Schatz, 2015; Rhie et al., 2021). It is generally assumed that orthologous genes,
i.e. evolutionarily related genes in different species whose lineages were separated by a
speciation event are likely to have similar functions (Altenhoff et al., 2012; Rogozin et al.,
2014). It is for this reason that the presence of orthologs to an already functionally annotated
gene serves as a proxy for the presence of the corresponding function (Cozzetto and Jones,
2017; Huerta-Cepas et al., 2017). One key step in tracing functions across species and through
time is therefore to determine the presence absence pattern of orthologs across large
collections of phylogenetically diverse species, i.e. the generation of phylogenetic profiles
(Date and Peregrín-Alvarez, 2008; Pellegrini, 2012; Tabach et al., 2013).

The accuracy of functional annotation heavily relies on the quality of ortholog prediction
(Salichos and Rokas, 2011; Trachana et al., 2011). Various strategies have been developed to
improve the performance of the ortholog inference (Pereira et al., 2014; Nichio et al., 2017).
These strategies encompass improving the specificity of sequence similarity searches and
incorporating evolutionary relationships via phylogenetic trees (Yang and Smith, 2014;
Battenberg et al., 2017; Jahangiri-Tazehkand et al., 2017; Lafond et al., 2018). The latter
method has demonstrated high accuracy, albeit it comes along with a substantial
computational effort which limits its use in contemporary data sets that easily encompass
thousands of species and sequences (Gabaldón, 2008; Kristensen et al., 2011). Likewise, the
accuracy of trees computed from a single gene is a limiting factor. Phylogenetic profiles, in
turn, can be rapidly generated, and they also reveal evolutionary relationships among
represented species. Abnormal patterns observed within phylogenetic profiles can potentially
indicate interesting evolutionary signals within specific taxonomic clades. Alternatively, such
patterns may arise from spurious ortholog assignments, rendering them artifacts. Currently,
it lacks approaches that leverage information extracted from phylogenetic profiles for the
assessment of orthology predictions. 

## Research Question
The aim of this project is to develop a machine learning
based approach that utilizes phylogenetic profiles to effectively identify erroneous ortholog
assignments. Is it possible to detect and eliminate false positive orthology assignments in phylogenetic profiles through the use of neural networks?

## Method

In this study, a novel approach for assessing the accuracy of the orthology prediction based
on neural networks will be devised and implemented. The aim is to identify and eliminate
false positive orthology assignments from phylogenetic profiles, either due to a low specificity
of the ortholog search or due to contaminating sequences in genome assemblies. As main sources of information, the algorithm will consider, for one seed protein, the presence/absence pattern of orthology assignments across the tree of life, changes in the
orthologs’ feature architectures, as well as the evolutionary relationships of the taxa the
orthologs were detected in. Optionally, I plan to integrate the conservation of gene order
on a local scale into the prediction. 

1. Generate simulated phylogenetic profiles encompassing varying degrees of information, ranging from gene families, metabolic pathways to complete gene sets, to train the models.

2. Use the evidence from different public databases, such as phylomeDB (Fuentes et al., 2022), pantherDB (Thomas et al., 2022), and OmaDB (Altenhoff et al., 2021) to label the ortholog assessments within these profiles as true positive, false positive, true negative, or false negative.

3. These presence/absence vectors will be complemented with additional information such as protein architecture similarity to serve as input for the neural network model.

4. The model will generate an output vector with scores assigned to each position, indicating the potential assessment for the orthology prediction.

5. Validate the performance model using multiple datasets comprising the phylogenetic profiles of diverse model organisms, including human, frog, mouse, among others, across a wide array of species throughout the tree of life.

6. Compare the results of this approach with the assessments provided by the Quest for Ortholog benchmarking service (Nevers et al., 2022).


The research will predominantly use Python programming language in conjunction with Jupyter Notebook for data analysis, processing, and visualization.The Goethe University also offers a dedicated data server to manage and storing large-scale research datasets securely.It will serve as the primary repository for the numerous datasets generated and collected during this research.

## Research Goal
The research goal it to enhance the accuracy and reliability of orthology prediction, which is a crucial aspect of comparative genomics and evolutionary biology. Accurate orthology assignments are crucial for understanding gene function, evolutionary relationships, and the transfer of biological knowledge between species.
This work would also help researchers avoid misleading interpretations of gene functions and evolutionary histories. 

## Time Plan
The master thesis will be done in 6 months approximately, starting from August 2023 to
January 2024.

| Month    | Intended work |
| -------- | ------- |
| 08.2023 | Studying related literatures; getting familiar with neural networks; preparing working environment (softwares, documentation,...)  |
| 09.2023 | Collecting and processing data; designing model |
| 10 - 11.2023 | Training and optimizing model |
| 12.2024 | Benchmarking the approach; start writing the thesis |
| 01.2024 | Thesis writing |

## References

1. Altenhoff, A.M. et al. (2021) OMA orthology in 2021: website overhaul, conserved isoforms, ancestral gene order and more. Nucleic Acids Res., 49, D373–D379.
https://doi.org/10.1093/nar/gkaa1007

2. Altenhoff, A.M. et al. (2012) Resolving the Ortholog Conjecture: Orthologs Tend to Be Weakly, but Significantly, More Similar in Function than Paralogs. PLoS Comput. Biol., 8, e1002514.https://doi.org/10.1371/journal.pcbi.1002514

3. Battenberg, K. et al. (2017) OrthoReD: a rapid and accurate orthology prediction tool with low computational requirement. BMC Bioinformatics, 18, 310.
https://doi.org/10.1186/s12859-017-1726-5

4. Cozzetto, D. and Jones, D.T. (2017) Computational Methods for Annotation Transfers from Sequence. In, Dessimoz, C. and Škunca, N. (eds), The Gene Ontology Handbook, Methods in Molecular Biology. Springer, New York, NY, pp. 55–67.https://link.springer.com/protocol/10.1007/978-1-4939-3743-1_5

5. Date, S.V. and Peregrín-Alvarez, J.M. (2008) Phylogenetic profiling. Methods Mol. Biol., 453, 201–216.https://doi.org/10.1007/978-1-60327-429-6_9

6. Fuentes, D. et al. (2022) PhylomeDB V5: an expanding repository for genome-wide catalogues of annotated gene phylogenies. Nucleic Acids Res., 50, D1062–D1068. https://doi.org/10.1093/nar/gkab966

7. Gabaldón, T. (2008) Large-scale assignment of orthology: back to phylogenetics? Genome Biol., 9, 235. https://doi.org/10.1186/gb-2008-9-10-235

8. Huerta-Cepas, J. et al. (2017) Fast Genome-Wide Functional Annotation through Orthology Assignment by eggNOG-Mapper. Mol. Biol. Evol., 34, 2115–2122. 
https://doi.org/10.1093/molbev/msx148

9. Jahangiri-Tazehkand, S. et al. (2017) OrthoGNC: A Software for Accurate Identification of Orthologs Based on Gene Neighborhood Conservation. Genomics Proteomics Bioinformatics, 15, 361–370. https://doi.org/10.1016/j.gpb.2017.07.002

10. Kristensen, D.M. et al. (2011) Computational methods for Gene Orthology inference. Brief. Bioinform., 12, 379–391. https://doi.org/10.1093/bib/bbr030

11. Lafond, M. et al. (2018) Accurate prediction of orthologs in the presence of divergence after duplication. Bioinformatics, 34, i366–i375. https://doi.org/10.1093/bioinformatics/bty242

12. Nevers, Y. et al. (2022) The Quest for Orthologs orthology benchmark service in 2022. Nucleic Acids Res., 50, W623–W632. https://doi.org/10.1093/nar/gkac330

13. Nichio, B.T.L. et al. (2017) New Tools in Orthology Analysis: A Brief Review of Promising Perspectives. Front. Genet., 0. https://doi.org/10.3389/fgene.2017.00165

14. Pellegrini, M. (2012) Using phylogenetic profiles to predict functional relationships. Methods Mol. Biol. Clifton NJ, 804, 167–77. https://doi.org/10.1007/978-1-61779-361-5_9

15. Pereira, C. et al. (2014) A meta-approach for improving the prediction and the functional annotation of ortholog groups. BMC Genomics, 15, S16. https://doi.org/10.1186/1471-2164-15-S6-S16

16. Rhie, A. et al. (2021) Towards complete and error-free genome assemblies of all vertebrate species. Nature, 592, 737–746. https://doi.org/10.1038/s41586-021-03451-0

17. Rogozin, I.B. et al. (2014) Gene Family Level Comparative Analysis of Gene Expression in Mammals Validates the Ortholog Conjecture. Genome Biol. Evol., 6, 754–762. https://doi.org/10.1093/gbe/evu051

18. Salichos, L. and Rokas, A. (2011) Evaluating Ortholog Prediction Algorithms in a Yeast Model Clade. PLOS ONE, 6, e18755.  https://doi.org/10.1371/journal.pone.0018755

19. Schatz, M.C. (2015) Biological data sciences in genome research. Genome Res., 25, 1417–1422. https://doi.org/10.1101/gr.191684.115

20. Tabach, Y. et al. (2013) Identification of small RNA pathway genes using patterns of phylogenetic conservation and divergence. Nature, 493, 694–698. https://doi.org/10.1038/nature11779

21. Thomas, P.D. et al. (2022) PANTHER: Making genome-scale phylogenetics accessible to all. Protein Sci., 31, 8–22.  https://doi.org/10.1002/pro.4218

22. Trachana, K. et al. (2011) Orthology prediction methods: a quality assessment using curated protein families. BioEssays News Rev. Mol. Cell. Dev. Biol., 33, 769–80. https://doi.org/10.1002/bies.201100062

23. Yang, Y. and Smith, S.A. (2014) Orthology Inference in Nonmodel Organisms Using Transcriptomes and Low-Coverage Genomes: Improving Accuracy and Matrix Occupancy for Phylogenomics. Mol. Biol. Evol., 31, 3081–3092. https://doi.org/10.1093/molbev/msu245
