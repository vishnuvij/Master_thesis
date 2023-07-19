# Detection of false positive ortholog assignments using phylogenetic profiles

Master Thesis Proposal

Author - Vishnu Vijayan (0080ti007)


## Background
The functional annotation of protein coding genes is crucial for investigating similarities but
also differences between related organisms. In the era of biodiversity genomics, an automated
transfer of functional annotations has increased in relevance because genomes of species are
being sequenced at a rapid pace that are both genetically but also phenotypically only poorly
characterized (Schatz, 2015; Rhie et al., 2021). It is generally assumed that orthologous genes,
i.e. evolutionarily related genes in different species whose lineages were separated by a
speciation event are likely to have similar functions (Altenhoff et al., 2012; Rogozin et al.,
2014). It is for this reason that the presence of orthologs to an already functionally annotated
gene serves as a proxy for the presence of the corresponding function (CozzeQo and Jones,
2017; Huerta-Cepas et al., 2017). One key step in tracing functions across species and through
time is therefore to determine the presence absence paQern of orthologs across large
collections of phylogenetically diverse species, i.e. the generation of phylogenetic profiles
(Date and Peregrín-Alvarez, 2008; Pellegrini, 2012; Tabach et al., 2013).

The accuracy of functional annotation heavily relies on the quality of ortholog prediction
(Salichos and Rokas, 2011; Trachana et al., 2011). Various strategies have been developed to
improve the performance of the ortholog inference (Pereira et al., 2014; Nichio et al., 2017).
These strategies encompass improving the specificity of sequence similarity searches and
incorporating evolutionary relationships via phylogenetic trees (Yang and Smith, 2014;
BaQenberg et al., 2017; Jahangiri-Tazehkand et al., 2017; Lafond et al., 2018). The laQer
method has demonstrated high accuracy, albeit it comes along with a substantial
computational effort which limits its use in contemporary data sets that easily encompass
thousands of species and sequences (Gabaldón, 2008; Kristensen et al., 2011). Likewise, the
accuracy of trees computed from a single gene is a limiting factor. Phylogenetic profiles, in
turn, can be rapidly generated, and they also reveal evolutionary relationships among
represented species. Abnormal paQerns observed within phylogenetic profiles can potentially
indicate interesting evolutionary signals within specific taxonomic clades. Alternatively, such
paQerns may arise from spurious ortholog assignments, rendering them artifacts. Currently,
it lacks approaches that leverage information extracted from phylogenetic profiles for the
assessment of orthology predictions. The aim of this project is to develop a machine learning
based approach that utilizes phylogenetic profiles to effectively identify erroneous ortholog
assignments.

## Method

In this study, a novel approach for assessing the accuracy of the orthology prediction based
on neural networks will be devised and implemented. The aim is to identify and eliminate
false positive orthology assignments from phylogenetic profiles, either due to a low specificity
of the ortholog search or due to contaminating sequences in genome assemblies. As main sources of information, the algorithm will consider, for one seed protein, the
presence/absence paQern of orthology assignments across the tree of life, changes in the
orthologs’ feature architectures, as well as the evolutionary relationships of the taxa the
orthologs were detected in. Optionally, we plan to integrate the conservation of gene order
on a local scale into the prediction. To train the models, simulated phylogenetic profiles will
be generated, encompassing varying degrees of information, ranging from gene families,
metabolic pathways to complete gene sets. The ortholog assessments within these profiles
will be labeled as true positive, false positive, true negative, or false negative using evidence
from different public databases, such as phylomeDB (Fuentes et al., 2022), pantherDB
(Thomas et al., 2022), and OmaDB (Altenhoff et al., 2021). These presence/absence vectors
will be complemented with additional information such as protein architecture similarity to
serve as input for the neural network model. The model will generate an output vector with
scores assigned to each position, indicating the potential assessment for the orthology
prediction.

Multiple datasets comprising the phylogenetic profiles of diverse model organisms, including
human, frog, mouse, among others, across a wide array of species throughout the tree of life
will be used to validate the performance of the model. The results of this approach will be
compared with the assessments provided by the Quest for Ortholog benchmarking service
(Nevers et al., 2022).

## Time Plan
The master thesis will be done in ti months approximately, starting from July 2023 to
February 2024.

## References
    Altenhoff,A.M. et al. (2021) OMA orthology in 2021: website overhaul, conserved isoforms,
ancestral gene order and more. Nucleic Acids Res., 49, D373–D379.
    Altenhoff,A.M. et al. (2012) Resolving the Ortholog Conjecture: Orthologs Tend to Be
Weakly, but Significantly, More Similar in Function than Paralogs. PLoS Comput. Biol.,
8, e1002514.
    BaQenberg,K. et al. (2017) OrthoReD: a rapid and accurate orthology prediction tool with
low computational requirement. BMC Bioinforma;cs, 18, 310.
    CozzeQo,D. and Jones,D.T. (2017) Computational Methods for Annotation Transfers from
Sequence. In, Dessimoz,C. and Škunca,N. (eds), The Gene Ontology Handbook,
Methods in Molecular Biology. Springer, New York, NY, pp. 55–ti7.
Date,S.V. and Peregrín-Alvarez,J.M. (2008) Phylogenetic profiling. Methods Mol. Biol., 453,
201–21ti.
Fuentes,D. et al. (2022) PhylomeDB V5: an expanding repository for genome-wide
catalogues of annotated gene phylogenies. Nucleic Acids Res., 50, D10ti2–D10ti8.
Gabaldón,T. (2008) Large-scale assignment of orthology: back to phylogenetics? Genome
Biol., 9, 235.
Huerta-Cepas,J. et al. (2017) Fast Genome-Wide Functional Annotation through Orthology
Assignment by eggNOG-Mapper. Mol. Biol. Evol., 34, 2115–2122.
Jahangiri-Tazehkand,S. et al. (2017) OrthoGNC: A Sonware for Accurate Identification of
Orthologs Based on Gene Neighborhood Conservation. Genomics Proteomics
Bioinforma;cs, 15, 3ti1–370.
Kristensen,D.M. et al. (2011) Computational methods for Gene Orthology inference. Brief.
Bioinform., 12, 379–391.
Lafond,M. et al. (2018) Accurate prediction of orthologs in the presence of divergence aner
duplication. Bioinforma;cs, 34, i3titi–i375.
Nevers,Y. et al. (2022) The Quest for Orthologs orthology benchmark service in 2022. Nucleic
Acids Res., 50, Wti23–Wti32.
Nichio,B.T.L. et al. (2017) New Tools in Orthology Analysis: A Brief Review of Promising
Perspectives. Front. Genet., 0.
Pellegrini,M. (2012) Using phylogenetic profiles to predict functional relationships. Methods
Mol. Biol. CliHon NJ, 804, 1ti7–77.
Pereira,C. et al. (2014) A meta-approach for improving the prediction and the functional
annotation of ortholog groups. BMC Genomics, 15, S1ti.
Rhie,A. et al. (2021) Towards complete and error-free genome assemblies of all vertebrate
species. Nature, 592, 737–74ti.
Rogozin,I.B. et al. (2014) Gene Family Level Comparative Analysis of Gene Expression in
Mammals Validates the Ortholog Conjecture. Genome Biol. Evol., ti, 754–7ti2.
Salichos,L. and Rokas,A. (2011) Evaluating Ortholog Prediction Algorithms in a Yeast Model
Clade. PLOS ONE, ti, e18755.
Schatz,M.C. (2015) Biological data sciences in genome research. Genome Res., 25, 1417–
1422.
Tabach,Y. et al. (2013) Identification of small RNA pathway genes using paQerns of
phylogenetic conservation and divergence. Nature, 493, ti94–ti98.
Thomas,P.D. et al. (2022) PANTHER: Making genome-scale phylogenetics accessible to all.
Protein Sci., 31, 8–22.
Trachana,K. et al. (2011) Orthology prediction methods: a quality assessment using curated
protein families. BioEssays News Rev. Mol. Cell. Dev. Biol., 33, 7ti9–80.
Yang,Y. and Smith,S.A. (2014) Orthology Inference in Nonmodel Organisms Using
Transcriptomes and Low-Coverage Genomes: Improving Accuracy and Matrix
Occupancy for Phylogenomics. Mol. Biol. Evol., 31, 3081–3092.
