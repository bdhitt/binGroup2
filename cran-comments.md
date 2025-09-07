## Test environments
* local Windows 10 Enterprise install, R 4.3.2
* Windows Server 2022 (via win-builder), R-oldrel, 32/64 bit 
* Windows Server 2022 (via win-builder), R-devel and R-release, 64 bit
* Windows Server 2022 (via rhub), R-devel, 64 bit
* Windows Server 2022 (via rhub), R-oldrel, 32/64 bit
* Fedora Linux (via rhub), R-devel, GCC and clang, gfortran
* Ubuntu Linux 20.04.1 LTS (via rhub), R-release and R-devel, GCC
* Debian Linux (via rhub), R-devel, clang, ISO-8859-15 locale
* Debian Linux (via rhub), R-devel and R-patched and R-release, GCC 
* Debian Linux (via rhub), R-devel, GCC ASAN/UBSAN and no long double
* Apple M1 (via macOS builder), macOS 13.3.1, R-release, GCC, CRAN setup


## R CMD check results

There were no ERRORs or WARNINGs. 

There was 1 NOTE. 

* checking installed package size ... NOTE
  installed size is  5.4Mb
  sub-directories of 1Mb or more:
    libs   4.2Mb

This note was present on MacOS, Fedora Linux and Ubuntu Linux. The installed package size indicated ranged from 5.2 Mb to nearly 11 Mb, depending on the platform. I believe this is due to the fact that the package has compiled code and uses Rcpp. 


This is an update to the existing binGroup2 package. 


## Addressing feedback on the previous submission   

An update for the binGroup2 package was initially submitted to CRAN on 12 November 2023. We received an email from the CRAN teams' auto-check service saying the following: 

  package binGroup2_1.3.tar.gz does not pass the incoming checks automatically, 
  please see the following pre-tests:

There were 2 NOTEs on Windows and Debian Linux: 

* checking CRAN incoming feasibility ... NOTE
Maintainer: 'Brianna Hitt <brianna.hitt@afacademy.af.edu>'

Found the following (possibly) invalid file URI:
  URI: www.chrisbilder.com/grouptesting
    From: inst/doc/Identification-through-group-testing.html

The URL has been updated. The full URL has been specified, including the scheme and a final slash. The URL has been checked and is currently valid. 


* checking S3 generic/method consistency ... NOTE
Mismatches for apparent methods not registered:

There were four background functions (none exported) that were being recognized as apparent S3 methods. None of these were S3 methods that needed to be registered, and the function names have been changed to avoid this confusion in the future. 

The package version was increased to 1.3.1 to reflect the changes made.


### Addressing the last released version's CRAN status

There are 2 NOTEs in the current CRAN package check results for binGroup2. 

Version: 1.2.4
Check: C++ specification
Result: NOTE
     Specified C++11: please drop specification unless essential

The C++ specification has been dropped as suggested. 


Version: 1.2.4
Check: installed package size
Result: NOTE
     installed size is 5.9Mb
     sub-directories of 1Mb or more:
     libs 4.8Mb

This is the same note addressed above. I believe this is due to the fact that the package has compiled code and uses Rcpp. 
  
  
## Downstream dependencies
There are currently no downstream dependencies for this package.
