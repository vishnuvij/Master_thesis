# Detection of false positive ortholog assignments using phylogenetic profiles


Background
The func6onal annota6on of protein coding genes is crucial for inves6ga6ng similari6es but
also differences between related organisms. In the era of biodiversity genomics, an automated
transfer of func6onal annota6ons has increased in relevance because genomes of species are
being sequenced at a rapid pace that are both gene6cally but also phenotypically only poorly
characterized (Schatz, 2015; Rhie et al., 2021). It is generally assumed that orthologous genes,
i.e. evolu6onarily related genes in different species whose lineages were separated by a
specia6on event are likely to have similar func6ons (Altenhoff et al., 2012; Rogozin et al.,
2014). It is for this reason that the presence of orthologs to an already func6onally annotated
gene serves as a proxy for the presence of the corresponding func6on (CozzeQo and Jones,
2017; Huerta-Cepas et al., 2017). One key step in tracing func6ons across species and through
6me is therefore to determine the presence absence paQern of orthologs across large
collec6ons of phylogene6cally diverse species, i.e. the genera6on of phylogene6c profiles
(Date and Peregrín-Alvarez, 2008; Pellegrini, 2012; Tabach et al., 2013).

The accuracy of func6onal annota6on heavily relies on the quality of ortholog predic6on
(Salichos and Rokas, 2011; Trachana et al., 2011). Various strategies have been developed to
improve the performance of the ortholog inference (Pereira et al., 2014; Nichio et al., 2017).
These strategies encompass improving the specificity of sequence similarity searches and
incorpora6ng evolu6onary rela6onships via phylogene6c trees (Yang and Smith, 2014;
BaQenberg et al., 2017; Jahangiri-Tazehkand et al., 2017; Lafond et al., 2018). The laQer
method has demonstrated high accuracy, albeit it comes along with a substan6al
computa6onal effort which limits its use in contemporary data sets that easily encompass
thousands of species and sequences (Gabaldón, 2008; Kristensen et al., 2011). Likewise, the
accuracy of trees computed from a single gene is a limi6ng factor. Phylogene6c profiles, in
turn, can be rapidly generated, and they also reveal evolu6onary rela6onships among
represented species. Abnormal paQerns observed within phylogene6c profiles can poten6ally
indicate interes6ng evolu6onary signals within specific taxonomic clades. Alterna6vely, such
paQerns may arise from spurious ortholog assignments, rendering them ar6facts. Currently,
it lacks approaches that leverage informa6on extracted from phylogene6c profiles for the
assessment of orthology predic6ons. The aim of this project is to develop a machine learning
based approach that u6lizes phylogene6c profiles to effec6vely iden6fy erroneous ortholog
assignments.

## Method

In this study, a novel approach for assessing the accuracy of the orthology predic6on based
on neural networks will be devised and implemented. The aim is to iden6fy and eliminate
false posi6ve orthology assignments from phylogene6c profiles, either due to a low specificity
of the ortholog search or due to contamina6ng sequences in genome assemblies. As main sources of informa6on, the algorithm will consider, for one seed protein, the
presence/absence paQern of orthology assignments across the tree of life, changes in the
orthologs’ feature architectures, as well as the evolu6onary rela6onships of the taxa the
orthologs were detected in. Op6onally, we plan to integrate the conserva6on of gene order
on a local scale into the predic6on. To train the models, simulated phylogene6c profiles will
be generated, encompassing varying degrees of informa6on, ranging from gene families,
metabolic pathways to complete gene sets. The ortholog assessments within these profiles
will be labeled as true posi6ve, false posi6ve, true nega6ve, or false nega6ve using evidence
from different public databases, such as phylomeDB (Fuentes et al., 2022), pantherDB
(Thomas et al., 2022), and OmaDB (Altenhoff et al., 2021). These presence/absence vectors
will be complemented with addi6onal informa6on such as protein architecture similarity to
serve as input for the neural network model. The model will generate an output vector with
scores assigned to each posi6on, indica6ng the poten6al assessment for the orthology
predic6on.

Mul6ple datasets comprising the phylogene6c profiles of diverse model organisms, including
human, frog, mouse, among others, across a wide array of species throughout the tree of life
will be used to validate the performance of the model. The results of this approach will be
compared with the assessments provided by the Quest for Ortholog benchmarking service
(Nevers et al., 2022).
