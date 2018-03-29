This folder includes the three datasets used for evaluating relation mapping in the following paper (dbmp, dev, test):

Z. Zhang, A. Gentile, E. Blomqvist, I. Augenstein, F. Ciravegna. 2016. An unsupervised data-driven method to discover equivalent relations in large Linked Datasets. Semantic web 8 (2), 197-223

For the descriptions of each dataset, see Section 4.5.2 in the paper. 

For each dataset there is 
"pair"     - annotated pair-wise equivalence
"clusters" - gs for evaluating clustering of equivalent relations, derived from "pair" data

Files inside "pair" have 6 columns
1 - relation 1 url
2 - relation 2 url
3 - ignore
4 - ignore
5 - ignore
6 - annotation (1-true pos; -1 true neg; 0-don't know; all others should be considered -1)


Files inside "cluster" have 7 columns
1 - cluster id
2 - relation 1 url
3 - relation 2 url
4 - ignore
5 - ignore
6 - ignore
7 - annotation (should always be 1)


**NOTE** Since DBpedia releases new data periodically and new experiments carried out with new data may not lead to identical results reported in the paper, we release additionally cached query data collected during our experiments and Java code for reading these data. However, these data are very large and therefore, not hosted here. Please contact [Ziqi Zhang] to obtain them. 

[Ziqi Zhang]: <mailto:ziqi.zhang@sheffield.ac.uk>
