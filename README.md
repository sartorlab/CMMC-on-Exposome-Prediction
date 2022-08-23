# CMMC-on-Exposome-Prediction

This site contains the benchmark datasets and C++ source code of the coupled matrix-matrix completion algorithm for exposome target interaction prediction.

[Armadillo](http://arma.sourceforge.net/) with [OpenBLAS](https://www.openblas.net/) are needed to compile the code.

Complaing example:
g++ CMMC.cpp -o CMMC -std=c++11 -O3 -I/path/to/armadillo/<include>/ -I/path/to/openblas/<include>/ -L/path/to/openblas/openblas/<lib>/ -lopenblas