## Test environments

* local Windows 11 Home install, R 4.5.1
* windows, R version 4.5.1 (via win-builder)
* windows, R Under development (via win-builder)
* macOS Venture 13.3.1, R version 4.5.1 Patched (via macOS builder)

Virtual machines (via rhub): 
* linux, all R versions on GitHub Actions ubuntu-latest
* m1-san, all R versions on GitHub Actions macos-15, ASAN + UBSAN on macos
* macos, all R versions on GitHub Actions macos-13
* macos-arm64, all R versions on GitHub Actions macos-latest
* windows, all R versions on GitHub Actions windows-latest

Containers (via rhub):
* atlas, R Under development on Fedora Linux 38
* c23, clang-asan and clang-ubsan, R Under development on Ubuntu 22.04.5 LTS
* clang16, clang17, clang18, clang19 and clang20; R Under development on Ubuntu 22.04.5 LTS
* gcc-asan, R Under development on Fedora Linux 40
* gcc12, R Under development on Ubuntu 22.04.5 LTS
* gcc13, R Under development on Fedora Linux 38
* gcc15, R Under development on Fedora Linux 42
* intel, R Under development on Fedora Linux 38
* ubuntu-clang, R Under development on Ubuntu 22.04.5 LTS
* ubuntu-next, R 4.5.1 Patched on Ubuntu 22.04.5 LTS
* ubuntu-release, R version 4.5.1 on Ubuntu 22.04.5 LTS
* valgrind, R Under development on Fedora Linux 38


## R CMD check results

There were no ERRORs or WARNINGs. 

There were 2 NOTEs.

* checking for future file timestamps ... NOTE
unable to verify current time

This note was present on c23, R Under development on Ubuntu 22.04.5 LTS and 
gcc13, R Under development on Fedora Linux 38. 
    
* checking compilation flags used ... NOTE
Compilation used the following non-portable flag(s):
  ‘-Wp,-D_FORTIFY_SOURCE=3’

This note was present on clang17, clang18, clang19 and clang20, R Under 
development on Ubuntu 22.04.5 LTS


There was 1 piece of INFO. 

* checking installed package size ... INFO
  installed size is  5.9Mb
  sub-directories of 1Mb or more:
    R      1.2Mb
    libs   4.2Mb

This info was present for the linux virtual machine and macOS Venture 13.3.1, 
R Version 4.5.1 Patched. The installed size was 5.9Mb and the sub-directory 
size ranged from 4.2Mb to 4.7Mb.


## Addressing feedback on the previous submission

An update for the binGroup2 package was initially submitted to CRAN on 
8 September 2025. We received an email from the CRAN teams' auto-check service 
saying the following: 

  package binGroup2_1.3.2.tar.gz does not pass the incoming checks 
  automatically, please see the following pre-tests (additional check issues):

There was 1 WARNING on Debian Linux: 

  warning: Using fallback compilation with Armadillo 14.6.3. Please consider 
  defining -DARMA_USE_CURRENT. See GitHub issue #475 for more. [-W#pragma-messages]

The Makevars and Makevars.win files have been updated to include 
PKG_CPPFLAGS = -DARMA_USE_CURRENT. No related issues were found in the 
extensive R checks done for this resubmission. 


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
Checks of this version (1.3.3) on macos and macos-arm64, all R versions, were successful.
Similar information was found on linux virtual machine and macOS 13.3.1 (via macOS builder). 
  
  
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

