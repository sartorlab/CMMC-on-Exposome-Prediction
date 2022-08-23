# CMMC-on-Exposome-Prediction

This site contains the benchmark datasets and C++ source code of the coupled matrix-matrix completion algorithm for exposome target interaction prediction.

## C++ Source Code

[Armadillo](http://arma.sourceforge.net/) with [OpenBLAS](https://www.openblas.net/) are needed to compile the code.

Complaing example:
g++ CMMC.cpp -o CMMC -std=c++11 -O3 -I/path/to/armadillo/\<include\>/ -I/path/to/openblas/\<include\>/ -L/path/to/openblas/openblas/\<lib\>/ -lopenblas

## Benchmark Dataset

Three different sizes of the input matrices, i.e., 200 chemicals by 400 genes (200_400), 400 chemicals by 600 genes(400_600), and 600 chemicals by 800 genes (600_800), with corresponding coupled matrices can be found in [BenchMarkdatasetsN1](https://github.com/sartorlab/CMMC-on-Exposome-Prediction/tree/main/BenchMarkdatasetsN1) and [BenchMarkdatasetsN2](https://github.com/sartorlab/CMMC-on-Exposome-Prediction/tree/main/BenchMarkdatasetsN2).

For each dataset: 
- "gene_chem_matrix.txt" is the chemical gene interaction matrix. 

- "chem_chem_1_matrix.txt" is the chemical similarites calculated based on the Morgan fingerprints.
- "chem_chem_2_matrix.txt" is the chemical similarites calculated based on the Topological Torsion fingerprints.

- "gene_gene_1_matrix.txt" is the gene similarites calculated based on GOMF.
- "gene_gene_2_matrix.txt" is the gene similarites calculated based on GOBP.
- "gene_gene_3_matrix.txt" is the gene similarites calculated based on GOCC.

- "neg.index.txt" and "pos.index.txt" contain the position indexes of true positve and true negative interactions in the chemical gene interaction matrix. 
 For the true positive dataset, only the most confident chemical-gene pairs, i.e., those that have more than 20 interaction records (not unique PubMed IDs) were selected, which resulted in 462 chemical-gene pairs in the true positive dataset. To generate the true negative dataset, chemicals were sorted by the number genes they interact with to select for the most well-studied chemicals. Then, the top 20 chemicals with the greatest number of interacting genes were selected as chemicals for the negative dataset. In this manner, we generated a chemical-gene pair list with the 20 chemicals and the genes having no interaction evidence with these 20 chemicals as a true negative dataset.  

 - 10 "gene_chem_matrix_replace_values_of_testdata.[X].txt" files are the chemical gene interaction matrix with the randomly selected true positive interactions replaced by 0. 
 - 10 "test.index.[X].txt" files are the indexes of randomly selected true positive and true negative interactions in corresponding chemical gene interaction matrices. 

 - "chem_id.txt" and "gene_id.txt" are the chemical names and gene Entrez IDs. 