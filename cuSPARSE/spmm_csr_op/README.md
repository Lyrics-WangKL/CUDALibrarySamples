# cuSPARSE Generic APIs - `cusparseSpMM CSR Custom Operators`

## Description

This sample demonstrates the usage of `cusparseSpMMOp` for performing *sparse matrix - dense matrix multiplication* with custom operators, where the sparse matrix is represented in CSR (Compressed Sparse Row) storage format.

[cusparseSpMM Documentation](https://docs.nvidia.com/cuda/cusparse/index.html#cusparse-generic-function-spmm_op)

`op_add(X, Y)   := X + Y`
`op_mul(X, Y)   := X * Y`
`epilogue(X, Y) := 2 * X + Y`

<center>

`C_ij = epilogue( op_add(op_add(op_mul(A_i0, B_0j), op_mul(A_i1, B_1j)), op_mul(A_i2, B_2j)) ..., C_ij )`

![](spmm_csr_op.png)
</center>

## Building

* Linux
    ```bash
    make
    ```

* Windows/Linux
    ```bash
    mkdir build
    cd build
    cmake ..
    make
    ```
    On Windows, instead of running the last build step, open the Visual Studio Solution that was created and build.

## Support

* **Supported SM Architectures:** SM 3.5, SM 3.7, SM 5.0, SM 5.2, SM 5.3, SM 6.0, SM 6.1, SM 6.2, SM 7.0, SM 7.2, SM 7.5, SM 8.0, SM 8.6
* **Supported OSes:** Linux, Windows, QNX
* **Supported CPU Architectures**: x86_64, ppc64le, arm64
* **Supported Compilers**: gcc, clang, Intel icc, IBM xlc, Microsoft msvc, Nvidia HPC SDK nvc
* **Language**: `C99`

## Prerequisites

* [CUDA 11.6 toolkit](https://developer.nvidia.com/cuda-downloads) (or above) and compatible driver (see [CUDA Driver Release Notes](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html#cuda-major-component-versions)).
* [CMake 3.9](https://cmake.org/download/) or above on Windows
