# AESGCM
## Overview
This sub-directory hosts the optimization of the Go AESGCM package using the latest Intel® VAES and Intel® VPCLMULQDQ instructions. This patch was built against the latest version of the Go runtime (GO 1.21). It is important to note that the patches we provide start with go 1.21 and are not backward compatible.

## Prerequisites
The instructions below assume that the user has a local copy of the Go runtime. Information on how to clone and build the runtime can be found on the [Golang official repository][Go].

## Instructions
### Apply the patch

```bash
    git clone https://github.com/go-runtime-optimizations.git
    cp go-runtime-optimizations/aesgcm/go121-crypto-aes-Implement-new-and-improved-AES-GCM-cipher.patch <your-GOROOT-directory>
    cd <your-GOROOT-directory>
    git apply --whitespace=fix go121-crypto-aes-Implement-new-and-improved-AES-GCM-cipher.patch
```
*NB: The patches will be updated with each release of the runtime, and a prefix will be attached to the name of the patch to reflect the Go release version it was built against. The current patch
    contains the prefix "go121" since it was built against Go 1.21. Make sure you choose the patch that matches or closely matches your Go runtime version.*

### Test
These instructions are to be executed after you build the patched runtime and properly set your environment variables to use it.
```bash
    cd <your-GOROOT-directory>/src/crypto/cipher
    go test -bench=.
```
 [Go]: https://github.com/golang/go/tree/master
