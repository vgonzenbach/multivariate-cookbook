--- 
title: "Advanced Research Methods: Multivariate Analysis Cookbook"
author: "Virgilio Gonzenbach"
date: "12/15/2019"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib]
biblio-style: apalike
link-citations: yes
description: "A recipe card for Multivariate Analysis"
---



# Introduction

This document is a "recipe card" for how to perform multivariate analysis in R using the ExPosition family of packages, developed by Dr. Hervé Abdi at the University of Texas at Dallas. It showcases the essential code, visualizations and interpretation aids needed for multiple methods of analysis. This recipe card is meant to serve as a quick reference of the general guidelines of use for each of the 8 methods included; it is not meant to be a detailed exposition of the code used to pre-process data and generate the multiple graphs found throughout the document. Those details belong to the Rmarkdown and R source files.  
\indent As a brief summary, all methods rely on the Singular Value Decomposition (SVD). SVD is a matrix operation that produces 3 lower rank matrices to describe a larger original matrix of data. As such, SVD is a dimensionality reduction technique. Each of the 8 methods differ on the type and number of matrices used for the analysis. Detailed differences between methods are discussed throughout and in relation to particular data. Supplementary computational statistic techniques (e.g., bootstrapping) are also discussed. 
 Below, I detail a broad overview of how these methods may be applied. 
  
## Analysis of psychometric questionnaires
Several methods covered in this document can be leveraged to describe the correlations between items of the same psychometric test, or between items from multiple psychometric tests. For example, Principal Component Analysis reveals the intercorrelation of items within a single table. Multiple Correspondence Analysis accomplishes similar objectives when the variables are qualitative. Partial Least Squares Correlation may reveal the common information between two questionnaires at the item-level—a more detailed approach than calculating correlation coefficients between summary scores. Finally, Multiple Factor Analysis allows for the examination of several questionnaires; it is particularly useful for detailed examination of questionnaires that are known to show a major overlap, or that purport to measure the same construct. 

## Transdiagnostic or multi-population studies
Other methods may be leveraged to compare a set of variables across different subpopulations. Versions of discriminant analysis (e.g., Barycentric Discriminant Analysis and Discriminant Correspondence Analysis) maximize differences between groups, and as such provide the basis for classification algorithms. Dual Multiple Factor Analysis may be used to describe sub-populations for which the same information has been collected. Finally, multiblock variants of barycentric discriminant analysis and discriminant correspondence analysis—i.e. Multiblock Barycentric Discriminant Analysis and Multiblock Discriminant Correspondence Analysis, respectively—combine principles from multi-table techniques and discriminant analysis to examine how different tables (e.g., questionnaires) perform at discriminating between subpopulations.

## Neuroimaging analysis
Partial Least Squares Methods enable the examination of multidimensional relationships between brain activity, behavior and experimental designs. Particularly, Partial Least Squares Correlation can be used to reveal the overlap between BOLD signal changes in ROIs and behavioral measurements—e.g., symptoms ratings, self-report questionnaires—or experimental designs—e.g., block or event related fMRI designs. Partial Least Squares Regression follows the same principles when the goal becomes to predict one data table using another, usually to predict behavior from brain activity.  
\indent Functional connectivity analysis is also facilitated by adapting the methods in this document. For an fMRI experiment, STATIS can be adapted to analyze how activity in multiple ROIs covary across time across either different experimental conditions or different participants. In either case, experimental (or quasi-experimental) groups—e.g., as psychiatric diagnoses—can be contrasted in terms of their functional connectivity by combining STATIS and discriminant analysis. Correlations between functional connectivity and behavior can also be examined by combining STATIS with Partial Least Squares methods.

## Further reading
Wiebels, K., Waldie, K. E., Roberts, R. P., & Park, H. R. P. (2016). Identifying grey matter changes in schizotypy using partial least squares correlation. Cortex: A Journal Devoted to the Study of the Nervous System and Behavior, 81, 137–150.

Sabaroedin, K., Tiego, J., Parkes, L., Sforazzini, F., Finlay, A., Johnson, B., … Fornito, A. (2019). Functional connectivity of corticostriatal circuitry and psychosis-like experiences in the general community. Biological Psychiatry.

Kirlic, N., Aupperle, R. L., Rhudy, J. L., Misaki, M., Kuplicki, R., Sutton, A., & Alvarez, R. P. (2019). Latent variable analysis of negative affect and its contributions to neural responses during shock anticipation. Neuropsychopharmacology, 44(4), 695–702.

Klumpp, H., Kinney, K. L., Bhaumik, R., & Fitzgerald, J. M. (2018). Principal component analysis and brain-based predictors of emotion regulation in anxiety and depression. Psychological Medicine.

Klumpp, H., Bhaumik, R., Kinney, K. L., & Fitzgerald, J. M. (2018). Principal component analysis and neural predictors of emotion regulation. Behavioural Brain Research, 338, 128–133.

Weathersby, F. L., King, J. B., Fox, J. C., Loret, A., & Anderson, J. S. (2019). Functional connectivity of emotional well-being: Overconnectivity between default and attentional networks is associated with attitudes of anger and aggression. Psychiatry Research: Neuroimaging, 291, 52–62.

Walther, S., Stegmayer, K., Federspiel, A., Bohlhalter, S., Wiest, R., & Viher, P. V. (2017). Aberrant hyperconnectivity in the motor system at rest is linked to motor abnormalities in schizophrenia spectrum disorders. Schizophrenia Bulletin, 43(5), 982–992.

Patel, R., Steele, C. J., Chen, A. G. X., Patel, S., Devenyi, G. A., Germann, J., … Chakravarty, M. M. (2019). Investigating microstructural variation in the human hippocampus using non-negative matrix factorization. NeuroImage.

Rajah, M. N., & McIntosh, A. R. (2005). Overlap in the Functional Neural Systems Involved in Semantic and Episodic Memory Retrieval. Journal of Cognitive Neuroscience, 17(3), 470–482.

Blake, Y., Terburg, D., Balchin, R., van Honk, J., & Solms, M. (2019). The role of the basolateral amygdala in dreaming. Cortex: A Journal Devoted to the Study of the Nervous System and Behavior, 113, 169–183.

Addis, D. R., Pan, L., Vu, M.-A., Laiser, N., & Schacter, D. L. (2009). Constructive episodic simulation of the future and the past: Distinct subsystems of a core brain network mediate imagining and remembering. Neuropsychologia, 47(11), 2222–2238.

Bellana, B., Liu, Z., Anderson, J. A. E., Moscovitch, M., & Grady, C. L. (2016). Laterality effects in functional connectivity of the angular gyrus during rest and episodic retrieval. Neuropsychologia, 80, 24–34.

Khedher, L., Ramírez, J., Górriz, J. M., Brahim, A., & Segovia, F. (2015). Early diagnosis of Alzheimer’s disease based on partial least squares, principal component analysis and support vector machine using segmented MRI images. Neurocomputing: An International Journal, 151(Part 1), 139–150.

McIntosh, A. R. (2012). Tracing the route to path analysis in neuroimaging. NeuroImage, 62(2), 887–890.

Yu, M., Wu, Z., Luan, M., Wang, X., Song, Y., & Liu, J. (2018). Neural correlates of semantic and phonological processing revealed by functional connectivity patterns in the language network. Neuropsychologia, 121, 47–57.
