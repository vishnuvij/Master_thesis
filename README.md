# Detection of false positive ortholog assignments using phylogenetic profiles

Master Thesis Proposal

Author - Vishnu Vijayan (00806007)


## Problem Introduction

Orthologous genes are genes found in different species that share a common evolutionary origin before a speciation event. Ortholog assignment is the procedure of recognizing such orthologous genes among diverse species. Functional annotation involves assigning specific biological functions or roles to genes, which is essential for investigating both similarities and differences between related organisms. In the era of biodiversity genomics, use of computational methods and algorithms for functional annotations has an increased relevance. These techniques help to accelerate the sequencing of the genomes of species which are both genetically and phenotypically poorly characterized [^1][^2]. An ortholog’s feature architecture refers to the arrangement and combination of various features or annotations such as functional domains, transmembrane domains, low complexity regions or secondary structure elements that are associated with protein sequences [^3]. The gene order is one of the important indicators for orthologs. The significance of gene order conservation has grown in predicting protein function because, as genomes evolve over time, the arrangement of genes is rearranged. This means that maintaining a consistent gene order within a local region reflects the functional limitations associated with the protein [^4]. 

It's generally assumed that the orthologous genes perform similar functions [^5][^6]. This is why the existence of orthologs to a gene with a known function is used as an indirect indicator for the presence of the same function [^7][^8]. One key step in tracing functions over different species and evolutionary periods involves establishing the presence or absence of orthologs across large collection of phylogenetically diverse species, which will entile the generation of phylogenetic profiles [^9][^10][^11]. The accuracy of functional annotation heavily relies on the quality of ortholog prediction [^12][^13]. Various strategies have been developed to improve the performance of the ortholog inference [^14][^15]. These strategies encompass improving the specificity of sequence similarity searches or incorporating evolutionary relationships via phylogenetic trees [^16][^17][^18][^19]. The latter method has demonstrated high accuracy, although it comes along with a substantial computational effort which limits its use in contemporary data sets that easily encompass thousands of species and sequences [^20],[^21]. Likewise, the accuracy of trees computed from a single gene is a limiting factor. Phylogenetic profiles, in turn, can be rapidly generated, and they also reveal evolutionary relationships among represented species. Abnormal patterns observed within phylogenetic profiles can potentially indicate interesting evolutionary signals within specific taxonomic clades. Alternatively, such patterns may arise from spurious ortholog assignments, rendering them artifacts. Currently, it lacks approaches that leverage information extracted from phylogenetic profiles for the assessment of orthology predictions.

## Research Goal

The research goal is to enhance the accuracy and reliability of orthology prediction, which is a crucial aspect of comparative genomics and evolutionary biology. Accurate orthology assignments are crucial for understanding gene function, evolutionary relationships, and the transfer of biological knowledge between species. In this project, I will investigate whether it is possible to detect and eliminate false positive orthology assignments in phylogenetic profiles through the use of neural networks. This will help researchers avoid misleading interpretations of gene functions and evolutionary histories. 

## Method

In this study, a novel approach for assessing the accuracy of the orthology prediction based on neural networks will be devised and implemented. The aim is to identify and eliminate false positive orthology assignments from phylogenetic profiles, either due to i) a low specificity of the ortholog search or ii) due to contaminating sequences in genome assemblies. As main sources of information, the algorithm will consider, for one seed protein, the presence/absence pattern of orthology assignments across the tree of life, changes in the orthologs’ feature architectures, as well as the evolutionary relationships of the taxa the orthologs were detected in. Optionally, I plan to integrate the conservation of gene order on a local scale into the prediction. 

1.	Generate simulated phylogenetic profiles using different ortholog prediction tools such as OMA [^22] (10.1101/gr.243212.118) or fDOG which is an in-house tool, encompassing varying degrees of information, ranging from gene families, metabolic pathways to complete gene sets, to train the models.

2.	Use the evidence from different public databases, such as phylomeDB [^23], pantherDB [^24], and OmaDB [^25] to label the ortholog assessments within these profiles as true positive, false positive, true negative, or false negative. These presence/absence vectors will be complemented with additional information such as protein architecture similarity to serve as input for the neural network model.

3.	The model will generate an output vector with scores assigned to each position of an ortholog, indicating the level of certainty for the orthology prediction.

4.	Validate the performance model using multiple in-house datasets comprising the phylogenetic profiles of diverse model organisms, including human, frog, mouse, 
    among others, across a wide array of species throughout the tree of life.

5.	Compare the results of this approach with the assessments provided by the Quest for Ortholog benchmarking service [^26].

6.	The research will predominantly use Python programming language in conjunction with Jupyter Notebook for data analysis, processing, and visualization.
     A dedicated data server offered by the Goethe University will serve as the primary repository for the numerous datasets generated and collected during this   
     research.

## Tools
The following tools are required to achieve the output. 

1.	fdog [^27]: fDOG - Feature-aware Directed OrtholoG search fDOG tool is distributed as a python package called fdog. It is compatible with Python ≥ v3.7. 

2.	OMA browser [^25]: The OMA (“Orthologous MAtrix”) project is a method and database for the inference of orthologs among complete genomes. 

3.	Phylo profile [^28]: PhyloProfile is a tool for exploring complex phylogenetic profiles.

4.	Python: Python is a high-level, general-purpose programming language. Its design philosophy emphasizes code readability with the use of significant indentation. The main libraries to be used in this project 		are: Tensor flow: [^29], Keras [^30], Numpy [^31], Pytorch [^32]

5.	Jupyter Noebook [^33]: The Jupyter Notebook is a web-based interactive computing platform that allows users to author data- and code-driven narratives that combine live code, equations, narrative text, 			visualizations, interactive dashboards and other media. 


## Time Plan
The master thesis will be done in 6 months approximately, starting from August 2023 to
January 2024.

| Month    | Intended work |
| -------- | ------- |
| 08.2023 | Studying related literature; getting familiar with neural networks; preparing working environment (softwares, documentation,...)  |
| 09.2023 | Collecting and processing data; designing model |
| 10 - 11.2023 | Training and optimizing model. First presentation | 
| 12.2024 | Benchmarking the approach; start writing the thesis |
| 01.2024 | Thesis writing. Final presentation |

## References

[^1]:	Schatz, M.C. (2015) Biological data sciences in genome research. Genome Res., 25, 1417–1422. https://doi.org/10.1101/gr.191684.115
[^2]:  Rhie, A. et al. (2021) Towards complete and error-free genome assemblies of all vertebrate species. Nature, 592, 737–746. https://doi.org/10.1038/s41586-021-03451-0
[^3]:	Dosch, J. et al. (2023) FAS: assessing the similarity between proteins using multi-layered feature architectures. Bioinformatics, Volume 39. https://doi.org/10.1093/bioinformatics/btad226
[^4]:	Thomas Dandekar a b. et al. (1998) Conservation of gene order: a fingerprint of proteins that physically interact. Trends in Biochemical Sciences, 23, 324-328. https://doi.org/10.1016/S0968-0004(98)01274-2 	
[^5]:	Altenhoff, A.M. et al. (2012) Resolving the Ortholog Conjecture: Orthologs Tend to Be Weakly, but Significantly, More Similar in Function than Paralogs. PLoS Comput. Biol., 8, e1002514. https://doi.org/10.1371/journal.pcbi.1002514
[^6]:	Rogozin, I.B. et al. (2014) Gene Family Level Comparative Analysis of Gene Expression in Mammals Validates the Ortholog Conjecture. Genome Biol. Evol., 6, 754–762. https://doi.org/10.1093/gbe/evu051
[^7]:	Cozzetto, D. and Jones, D.T. (2017) Computational Methods for Annotation Transfers from Sequence. In, Dessimoz, C. and Škunca, N. (eds), The Gene Ontology Handbook, Methods in Molecular Biology. Springer, New York, NY, pp. 55–67. https://link.springer.com/protocol/10.1007/978-1-4939-3743-1_5
[^8]:	Huerta-Cepas, J. et al. (2017) Fast Genome-Wide Functional Annotation through Orthology Assignment by eggNOG-Mapper. Mol. Biol. Evol., 34, 2115–2122. https://doi.org/10.1093/molbev/msx148
[^9]:	Date, S.V. and Peregrín-Alvarez, J.M. (2008) Phylogenetic profiling. Methods Mol. Biol., 453, 201–216.https://doi.org/10.1007/978-1-60327-429-6_9
[^10]:	Pellegrini, M. (2012) Using phylogenetic profiles to predict functional relationships. Methods Mol. Biol. Clifton NJ, 804, 167–77. https://doi.org/10.1007/978-1-61779-361-5_9
[^11]:	Tabach, Y. et al. (2013) Identification of small RNA pathway genes using patterns of phylogenetic conservation and divergence. Nature, 493, 694–698. https://doi.org/10.1038/nature11779 
[^12]:	Salichos, L. and Rokas, A. (2011) Evaluating Ortholog Prediction Algorithms in a Yeast Model Clade. PLOS ONE, 6, e18755.  https://doi.org/10.1371/journal.pone.0018755 
[^13]:	Trachana, K. et al. (2011) Orthology prediction methods: a quality assessment using curated protein families. BioEssays News Rev. Mol. Cell. Dev. Biol., 33, 769–80. https://doi.org/10.1002/bies.201100062
[^14]:	Pereira, C. et al. (2014) A meta-approach for improving the prediction and the functional annotation of ortholog groups. BMC Genomics, 15, S16. https://doi.org/10.1186/1471-2164-15-S6-S16
[^15]:	Nichio, B.T.L. et al. (2017) New Tools in Orthology Analysis: A Brief Review of Promising Perspectives. Front. Genet., 0. https://doi.org/10.3389/fgene.2017.00165
[^16]:	Yang, Y. and Smith, S.A. (2014) Orthology Inference in Nonmodel Organisms Using Transcriptomes and Low-Coverage Genomes: Improving Accuracy and Matrix Occupancy for Phylogenomics. Mol. Biol. Evol., 31, 3081–3092. https://doi.org/10.1093/molbev/msu245
[^17]:	Battenberg, K. et al. (2017) OrthoReD: a rapid and accurate orthology prediction tool with low computational requirement. BMC Bioinformatics, 18, 310. https://doi.org/10.1186/s12859-017-1726-5
[^18]:	Jahangiri-Tazehkand, S. et al. (2017) OrthoGNC: A Software for Accurate Identification of Orthologs Based on Gene Neighborhood Conservation. Genomics Proteomics Bioinformatics, 15, 361–370. https://doi.org/10.1016/j.gpb.2017.07.002
[^19]:	Lafond, M. et al. (2018) Accurate prediction of orthologs in the presence of divergence after duplication. Bioinformatics, 34, i366–i375. https://doi.org/10.1093/bioinformatics/bty242
[^20]:	Gabaldón, T. (2008) Large-scale assignment of orthology: back to phylogenetics? Genome Biol., 9, 235. https://doi.org/10.1186/gb-2008-9-10-235
[^21]:	Kristensen, D.M. et al. (2011) Computational methods for Gene Orthology inference. Brief. Bioinform., 12, 379–391. https://doi.org/10.1093/bib/bbr030
[^22]: Altenhoff, A.M. et al. (2019) OMA standalone: orthology inference among public and custom genomes and transcriptomes. Genome Res. 2019. 29: 1152-1163. http://www.genome.org/cgi/doi/10.1101/gr.243212.118.
[^23]: Fuentes, D. et al. (2022) PhylomeDB V5: an expanding repository for genome-wide catalogues of annotated gene phylogenies. Nucleic Acids Res., 50, D1062–D1068. https://doi.org/10.1093/nar/gkab966 
[^24]: Thomas, P.D. et al. (2022) PANTHER: Making genome-scale phylogenetics accessible to all. Protein Sci., 31, 8–22.  https://doi.org/10.1002/pro.4218 
[^25]: Altenhoff, A.M. et al. (2021) OMA orthology in 2021: website overhaul, conserved isoforms, ancestral gene order and more. Nucleic Acids Res., 49, D373–D379. https://doi.org/10.1093/nar/gkaa1007 
[^26]: Nevers, Y. et al. (2022) The Quest for Orthologs orthology benchmark service in 2022. Nucleic Acids Res., 50, W623–W632. https://doi.org/10.1093/nar/gkac330 
[^27]: Ebersberger, I. et al. (2009) HaMStR: Profile hidden markov model based search for orthologs in ESTs. BMC Evol Biol 9, 157, doi:10.1186/1471-2148-9-157
[^28]: Ngoc-Vinh Tran. et al. (2018) PhyloProfile: dynamic visualization and exploration of multi-layered phylogenetic profiles, Bioinformatics, Volume 34, Issue 17, Pages 3041–3043, https://doi.org/10.1093/bioinformatics/bty225
[^29]: Abadi, M. et al. (2015). TensorFlow [Software]. Available from https://www.tensorflow.org/
[^30]: Chollet, F. et al. (2015). Keras. GitHub. Retrieved from https://github.com/fchollet/keras
[^31]: Harris, C. R. et al. (2020). Array programming with NumPy. Nature, 585, 357–362. https://doi.org/10.1038/s41586-020-2649-2
[^32]: Paszke, A. et al. (2019). PyTorch: An Imperative Style, High-Performance Deep Learning Library. In Advances in Neural Information Processing Systems 32 (pp. 8024–8035). Curran Associates, Inc. Retrieved from http://papers.neurips.cc/paper/9015-pytorch-an-imperative-style-high-performance-deep-learning-library.pdf
[^33]: Kluyver, T. et al. (2016). Jupyter Notebooks – a publishing format for reproducible computational workflows. In F. Loizides & B. Schmidt (Eds.), Positioning and Power in Academic Publishing: Players, Agents and Agendas (pp. 87–90).
