## Test environments

* local Windows 11 Home install, R 4.5.1
* windows, R version 4.5.1 (via win-builder)
* windows, R Under development (via win-builder)

Virtual machines (via rhub): 
* linux, all R versions on GitHub Actions ubuntu-latest
* m1-san, all R versions on GitHub Actions macos-15, ASAN + UBSAN on macos
* macos, all R versions on GitHub Actions macos-13
* macos-arm64, all R versions on GitHub Actions macos-latest
* windows, all R versions on GitHub Actions windows-latest

Containers (via rhub):
* atlas, R Under development on Fedora Linux 38
* clang-asan and clang-ubsan, R Under development on Ubuntu 22.04.5 LTS
* gcc-asan, R Under development on Fedora Linux 40
* intel, R Under development on Fedora Linux 38
* ubuntu-clang, R Under development on Ubuntu 22.04.5 LTS
* ubuntu-release, R version 4.5.1 on Ubuntu 22.04.5 LTS
* valgrind, R Under development on Fedora Linux 38


## R CMD check results

There were no ERRORs or WARNINGs. 

There was 1 NOTE.

* checking for future file timestamps ... NOTE
unable to verify current time

This note was present on atlas, R Under development on Fedora Linux 38. 


## Notes for CRAN
* This is a maintenance release: minor bug fix (single line of code) and addition of GitHub repository link.


### Addressing the last released version's CRAN status

There are 2 NOTEs in the current CRAN package check results for binGroup2. 

Version: 1.3.1
Check: installed package size
Result: NOTE 
    installed size is  5.7Mb
    sub-directories of 1Mb or more:
      libs   4.6Mb
Flavors: r-oldrel-macos-arm64, r-oldrel-macos-x86_64

I believe this is due to the fact that the package has compiled code and uses Rcpp.
Checks of this version (1.3.2) on macos and macos-arm64, all R versions, were successful. 
  
  
## Downstream dependencies

The groupTesting package is a downstream dependency for the binGroup2 package. 

There was 1 ERROR and 1 WARNING when checking the groupTesting package. 

* checking PDF version of manual ... WARNING
LaTeX errors when creating PDF version.
This typically indicates Rd problems.
* checking PDF version of manual without index ... ERROR
Re-running with no redirection of stdout/stderr.

These appear to be issues with the PDF version of the manual for the 
groupTesting package, and nothing related to this minor update to the 
binGroup2 package. 

