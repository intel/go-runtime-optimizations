#  Intel&reg; Go Runtime Optimizations

## Overview
This repository hosts a collection of patches created by Intel’s Golang Tuning Team to optimize the performance of certain CPU intensive functions found within the Golang runtime.  Most of these patches make use of Intel® AVX-512 instruction enhancements and are capable of providing significant performance gains over the built in functions.  All of these optimizations have been submitted to the Golang repository https://go.googlesource.com/go and are available for your use.  While we work with the maintainers to review and gain acceptance of these patches, you may incorporate the optimizations of your choice into your own runtime and immediately benefit from this work.

If you have an interest in these optimizations, please share your support with the Golang community by adding a comment to the appropriate pull request.  Your actions will help demonstrate the value to the community and help the maintainers prioritize and ultimately merge this work.

## Features
The structure of the repositopry is organized in a series of subdirectories to host the different patches, which list will grow as more optimizations come online. Currently, the list of suppported optimizations and their associated subdirectory consists of:

  * **aesgcm:** optimization of the Go AESGCM package using the latest Intel&reg; VAES and VPCLMULQDQ instructions. https://go-review.googlesource.com/c/go/+/334610
  * **sha256:** optimization of the Go SHA-256 package using the latest Intel&reg; SHA-NI instuctions.
  * **md5-nonavx**: optimization of the Go MD5 package using Intel&reg; AVX-512 instructions. https://go-review.googlesource.com/c/go/+/433475
  * **md5-avx:** optimization of the Go MD5 package using latest x86 instructions. https://go-review.googlesource.com/c/go/+/455235
  * **rsa:** optimization of the Go RSA package using Intel&reg; AVX-512, Intel&reg; VPMADD52 and Intel&reg; IFMA instructions. https://go-review.googlesource.com/c/go/+/481618

*NB: Some of the patches have already been merged in the Go runtime and are, therefore, readily available with versions of the runtime starting with go 1.21.* 
