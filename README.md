# CMMC-on-Exposome-Prediction

This site contains the benchmark datasets and C++ source code of the coupled matrix-matrix completion algorithm for exposome target interaction prediction.

## C++ Source Code

[Armadillo](http://arma.sourceforge.net/) with [OpenBLAS](https://www.openblas.net/) are needed to compile the code.

Complaing example:
g++ CMMC.cpp -o CMMC -std=c++11 -O3 -I/path/to/armadillo/\<include\>/ -I/path/to/openblas/\<include\>/ -L/path/to/openblas/openblas/\<lib\>/ -lopenblas

## Benchmark Dataset

Three different sizes of the input matrices, i.e., 200 chemicals by 400 genes (200_400), 400 chemicals by 600 genes(400_600), and 600 chemicals by 800 genes (600_800), with corresponding coupled matrices can be found in [BenchMarkdatasetsN1](https://github.com/sartorlab/CMMC-on-Exposome-Prediction/tree/main/BenchMarkdatasetsN1) and [BenchMarkdatasetsN2](https://github.com/sartorlab/CMMC-on-Exposome-Prediction/tree/main/BenchMarkdatasetsN2).

