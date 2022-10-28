# `rb3` - package review

## **Reviewer:** [@quishqa](https://github.com/quishqa)

### Review Submitted: 28/10/2022

------------------------------------------------------------------------

------------------------------------------------------------------------

<br>

This report contains documents associated with the review of
**rOpenSci** submitted package:

### **`rb3`: ropensci/software-review** issue [\#534](https://github.com/ropensci/software-review/issues/534).

<br>

## Package info

**Description:**

Download and parse public files released by B3 and convert them into
useful formats and data structures common to data analysis
practitioners.

**Author:** Wilson Freitas <wilson.freitas@gmail.com> \[aut, cre\],
Marcelo Perlin <marceloperlin@gmail.com> \[aut\]

**repo url:** <https://github.com/wilsonfreitas/rb3>

**website url:** <https://wilsonfreitas.github.io/rb3/>

## Review info

#### See [reviewer guidelines](https://ropensci.github.io/dev_guide/reviewerguide.html) for further information on the rOpenSci review process.

**key review checks:**

-   Does the code comply with **general principles in the [Mozilla
    reviewing
    guide](https://mozillascience.github.io/codeReview/review.html)**?
-   Does the package **comply with the [ROpenSci packaging
    guide](https://ropensci.github.io/dev_guide/building.html)**?
-   Are there **improvements** that could be made to the **code style?**
-   Is there **code duplication** in the package that should be reduced?
-   Are there **user interface improvements** that could be made?
-   Are there **performance improvements** that could be made?
-   Is the
    [**documentation**](https://ropensci.github.io/dev_guide/building.html#documentation)
    (installation instructions/vignettes/examples/demos) **clear and
    sufficient**?

Please be respectful and kind to the authors in your reviews. The
rOpenSci [code of
conduct](https://ropensci.github.io/dev_guide/policies.html#code-of-conduct)
is mandatory for everyone involved in our review process.

------------------------------------------------------------------------

### session info

``` r
sessionInfo()
#> R version 4.2.1 (2022-06-23)
#> Platform: x86_64-pc-linux-gnu (64-bit)
#> Running under: Ubuntu 22.04.1 LTS
#> 
#> Matrix products: default
#> BLAS:   /usr/lib/x86_64-linux-gnu/openblas-pthread/libblas.so.3
#> LAPACK: /usr/lib/x86_64-linux-gnu/openblas-pthread/libopenblasp-r0.3.20.so
#> 
#> locale:
#>  [1] LC_CTYPE=pt_BR.UTF-8       LC_NUMERIC=C              
#>  [3] LC_TIME=pt_BR.UTF-8        LC_COLLATE=en_US.UTF-8    
#>  [5] LC_MONETARY=pt_BR.UTF-8    LC_MESSAGES=en_US.UTF-8   
#>  [7] LC_PAPER=pt_BR.UTF-8       LC_NAME=C                 
#>  [9] LC_ADDRESS=C               LC_TELEPHONE=C            
#> [11] LC_MEASUREMENT=pt_BR.UTF-8 LC_IDENTIFICATION=C       
#> 
#> attached base packages:
#> [1] stats     graphics  grDevices utils     datasets  methods   base     
#> 
#> other attached packages:
#> [1] devtools_2.4.5 usethis_2.1.6  magrittr_2.0.3
#> 
#> loaded via a namespace (and not attached):
#>  [1] Rcpp_1.0.9        urlchecker_1.0.1  compiler_4.2.1    later_1.3.0      
#>  [5] remotes_2.4.2     prettyunits_1.1.1 profvis_0.3.7     tools_4.2.1      
#>  [9] digest_0.6.30     pkgbuild_1.3.1    pkgload_1.3.1     evaluate_0.17    
#> [13] memoise_2.0.1     lifecycle_1.0.3   rlang_1.0.6       shiny_1.7.3      
#> [17] cli_3.4.1         rstudioapi_0.14   yaml_2.3.6        xfun_0.34        
#> [21] fastmap_1.1.0     stringr_1.4.1     knitr_1.40        fs_1.5.2         
#> [25] htmlwidgets_1.5.4 glue_1.6.2        R6_2.5.1          processx_3.8.0   
#> [29] rmarkdown_2.17    sessioninfo_1.2.2 purrr_0.3.5       callr_3.7.2      
#> [33] promises_1.2.0.1  ps_1.7.2          ellipsis_0.3.2    htmltools_0.5.3  
#> [37] mime_0.12         xtable_1.8-4      httpuv_1.6.6      stringi_1.7.8    
#> [41] miniUI_0.1.1.1    cachem_1.0.6      crayon_1.5.2
```

## Test installation

### test local `rb3` install:

``` r
install(pkg_dir, dependencies = T, build_vignettes = T)
#> 
#>      checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’ ...  ✔  checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’
#>   ─  preparing ‘rb3’:
#>    checking DESCRIPTION meta-information ...  ✔  checking DESCRIPTION meta-information
#>   ─  installing the package to build vignettes
#>      creating vignettes ...  ✔  creating vignettes (52.5s)
#>   ─  checking for LF line-endings in source and make files and shell scripts
#>   ─  checking for empty or unneeded directories
#>      Omitted ‘LazyData’ from DESCRIPTION
#>   ─  building ‘rb3_0.0.7.tar.gz’
#>      
#> Running /usr/lib/R/bin/R CMD INSTALL /tmp/RtmplxABwy/rb3_0.0.7.tar.gz \
#>   --install-tests 
#> * installing to library ‘/home/quishqa/R/x86_64-pc-linux-gnu-library/4.2’
#> * installing *source* package ‘rb3’ ...
#> ** using staged installation
#> ** R
#> ** inst
#> ** tests
#> ** byte-compile and prepare package for lazy loading
#> ** help
#> *** installing help indices
#> *** copying figures
#> ** building package indices
#> ** installing vignettes
#> ** testing if installed package can be loaded from temporary location
#> ** testing if installed package can be loaded from final location
#> ** testing if installed package keeps a record of temporary installation path
#> * DONE (rb3)
```

``` r
remove.packages("rb3")
#> Removing package from '/home/quishqa/R/x86_64-pc-linux-gnu-library/4.2'
#> (as 'lib' is unspecified)
```

#### **comments:**

Local Installation Ok!

<!-- record comments on local install here -->

------------------------------------------------------------------------

### test install of `rb3` from GitHub with:

``` r
devtools::install_github("wilsonfreitas/rb3", dependencies = T, build_vignettes = T)
#> Downloading GitHub repo wilsonfreitas/rb3@HEAD
#> 
#>      checking for file ‘/tmp/RtmplxABwy/remotesc48e7a47218/wilsonfreitas-rb3-1150c7f/DESCRIPTION’ ...  ✔  checking for file ‘/tmp/RtmplxABwy/remotesc48e7a47218/wilsonfreitas-rb3-1150c7f/DESCRIPTION’
#>   ─  preparing ‘rb3’:
#>    checking      checking DESCRIPTION meta-information ...  ✔  checking DESCRIPTION meta-information
#>   ─  installing the package to build vignettes
#>      creating vignettes ...  ✔  creating vignettes (58.8s)
#>   ─  checking for LF line-endings in source and make files and shell scripts
#>   ─  checking for empty or unneeded directories
#>      Omitted ‘LazyData’ from DESCRIPTION
#>   ─  building ‘rb3_0.0.7.tar.gz’
#>      
#> 
#> Installing package into '/home/quishqa/R/x86_64-pc-linux-gnu-library/4.2'
#> (as 'lib' is unspecified)
```

#### **comments:**

-   Installation from Github Ok!
    <!-- record comments on github install here -->

------------------------------------------------------------------------

## Check package integrity

### run checks on `rb3` source:

``` r
devtools::check(pkg_dir)
#> ══ Documenting ═════════════════════════════════════════════════════════════════
#> ℹ Updating rb3 documentation
#> ℹ Loading rb3
#> 
#> ══ Building ════════════════════════════════════════════════════════════════════
#> Setting env vars:
#> • CFLAGS    : -Wall -pedantic
#> • CXXFLAGS  : -Wall -pedantic
#> • CXX11FLAGS: -Wall -pedantic
#> • CXX14FLAGS: -Wall -pedantic
#> • CXX17FLAGS: -Wall -pedantic
#> • CXX20FLAGS: -Wall -pedantic
#>          checking      checking for file      checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’     checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’ ...     checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’ ...      checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’ ... OK  ✔  checking for file ‘/home/quishqa/projects/rOpenSci/reviews/rb3/DESCRIPTION’
#>      preparing ‘rb3’  ─  preparing ‘rb3’:
#>    checking DESCRIPTION meta-information ...  ✔  checking DESCRIPTION meta-information
#>   ─  installing the package to build vignettes
#>      creating vignettes ...  ✔  creating vignettes (1m 2.1s)
#>   ─  checking for LF line-endings in source and make files and shell scripts
#>   ─  checking for empty or unneeded directories
#>      Omitted ‘LazyData’ from DESCRIPTION
#>   ─  building ‘rb3_0.0.7.tar.gz’
#>      
#> ══ Checking ════════════════════════════════════════════════════════════════════
#> Setting env vars:
#> • _R_CHECK_CRAN_INCOMING_USE_ASPELL_           : TRUE
#> • _R_CHECK_CRAN_INCOMING_REMOTE_               : FALSE
#> • _R_CHECK_CRAN_INCOMING_                      : FALSE
#> • _R_CHECK_FORCE_SUGGESTS_                     : FALSE
#> • _R_CHECK_PACKAGES_USED_IGNORE_UNUSED_IMPORTS_: FALSE
#> • NOT_CRAN                                     : true
#> ── R CMD check ─────────────────────────────────────────────────────────────────
#>   ─  using log directory ‘/tmp/RtmplxABwy/filec48e114962e0/rb3.Rcheck’
#>   ─  using R version 4.2.1 (2022-06-23)
#> ─  using platform: x86_64-pc-linux-gnu (64-bit)
#> ─  using session charset: UTF-8
#>   ─  using options ‘--no-manual --as-cran’
#>      checking for file ‘rb3/DESCRIPTION’ ...  ✔  checking for file ‘rb3/DESCRIPTION’
#> ─  this is package ‘rb3’ version ‘0.0.7’
#>   ─  package encoding: UTF-8
#>    checking package namespace information ...  ✔  checking package namespace information
#>    checking      checking package dependencies ...  ✔  checking package dependencies (1.4s)
#>    checking if this is a source package ...  ✔  checking if this is a source package
#> ✔  checking if there is a namespace
#>      checking for executable files ...  ✔  checking for executable files (638ms)
#>   ✔  checking for hidden files and directories
#>    checking for portable file names ...  ✔  checking for portable file names
#>   ✔  checking for sufficient/correct file permissions
#>      checking whether package ‘rb3’ can be installed ...  ✔  checking whether package ‘rb3’ can be installed (11.4s)
#>      checking installed package size ...  ✔  checking installed package size
#>      checking package directory ...  ✔  checking package directory
#>    checking for future file timestamps ...  ✔  checking for future file timestamps
#>   ✔  checking ‘build’ directory
#>    checking DESCRIPTION meta-information ...  ✔  checking DESCRIPTION meta-information (384ms)
#>    checking top-level files ...  ✔  checking top-level files
#> ✔  checking for left-over files
#>    checking index information ...  ✔  checking index information
#>    checking package subdirectories ...  ✔  checking package subdirectories (433ms)
#>      checking R files for non-ASCII characters ...  ✔  checking R files for non-ASCII characters
#>      checking R files for syntax errors ...  ✔  checking R files for syntax errors
#>      checking whether the package can be loaded ...  ✔  checking whether the package can be loaded (3s)
#>      checking whether the package can be loaded with stated dependencies ...  ✔  checking whether the package can be loaded with stated dependencies (3.5s)
#>    checking whether the package can be unloaded cleanly ...  ✔  checking whether the package can be unloaded cleanly (3.6s)
#>    checking whether the namespace can be loaded with stated dependencies ...  ✔  checking whether the namespace can be loaded with stated dependencies (2.3s)
#>      checking whether the namespace can be unloaded cleanly ...  ✔  checking whether the namespace can be unloaded cleanly (2.1s)
#>      checking loading without being on the library search path ...  ✔  checking loading without being on the library search path (2.9s)
#>    checking dependencies in R code ...  ✔  checking dependencies in R code (3.1s)
#>      checking S3 generic/method consistency ...  ✔  checking S3 generic/method consistency (3.9s)
#>    checking replacement functions ...  ✔  checking replacement functions (2.9s)
#>      checking foreign function calls ...  ✔  checking foreign function calls (2.9s)
#>      checking R code for possible problems ...  ✔  checking R code for possible problems (14.9s)
#>    checking Rd files ...  ✔  checking Rd files (361ms)
#>      checking Rd metadata ...  ✔  checking Rd metadata
#>      checking Rd line widths ...  ✔  checking Rd line widths
#>    checking Rd cross-references ...  ✔  checking Rd cross-references
#>    checking for missing documentation entries ...  ✔  checking for missing documentation entries (3.2s)
#>    checking for code/documentation mismatches ...  ✔  checking for code/documentation mismatches (9s)
#>      checking Rd \usage sections ...  ✔  checking Rd \usage sections (4s)
#>    checking Rd contents ...  ✔  checking Rd contents
#>    checking for unstated dependencies in examples ...  ✔  checking for unstated dependencies in examples
#>      checking installed files from ‘inst/doc’ ...  ✔  checking installed files from ‘inst/doc’
#>      checking files in ‘vignettes’ ...     checking files in ‘vignettes’ ...      checking files in ‘vignettes’ ... OK  ✔  checking files in ‘vignettes’
#>    checking examples ...  ✔  checking examples (6s)
#>      checking for unstated dependencies in ‘tests’ ...  ✔  checking for unstated dependencies in ‘tests’
#>      checking tests ...  ─  checking tests
#>      Running ‘testthat.R’    ✔  Running ‘testthat.R’ [25s/50s] (50.2s)
#>      checking for unstated dependencies in vignettes ...  ✔  checking for unstated dependencies in vignettes
#>    checking package vignettes in ‘inst/doc’ ...  ✔  checking package vignettes in ‘inst/doc’
#>      checking re-building of vignette outputs ...  ✔  checking re-building of vignette outputs (40.3s)
#>   ✔  checking for non-standard things in the check directory
#> ✔  checking for detritus in the temp directory
#>    
#>    
#> 
#> ── R CMD check results ────────────────────────────────────────── rb3 0.0.7 ────
#> Duration: 2m 55.8s
#> 
#> 0 errors ✔ | 0 warnings ✔ | 0 notes ✔
```

#### **comments:**

-   The check returned no error and no warnings. All good!
    <!-- record comments on checks here -->

------------------------------------------------------------------------

### run tests on `rb3` source:

``` r
devtools::test(pkg_dir)
#> ℹ Testing rb3
#> 
#> Attaching package: 'testthat'
#> 
#> 
#> The following object is masked from 'package:devtools':
#> 
#>     test_file
#> 
#> 
#> The following objects are masked from 'package:magrittr':
#> 
#>     equals, is_less_than, not
#> ✔ | F W S  OK | Context
#> ⠏ |         0 | bd_arbit                                                        ✔ |         9 | bd_arbit
#> ⠏ |         0 | bdin                                                            ⠋ |         1 | bdin                                                            ✔ |         2 | bdin [0.3s]
#> ⠏ |         0 | cache                                                           ✔ |         3 | cache
#> ⠏ |         0 | cdi                                                             ⠋ |         1 | cdi                                                             ⠹ |         3 | cdi                                                             ✔ |         3 | cdi [1.3s]
#> ⠏ |         0 | cdiidi                                                          ⠴ |         6 | cdiidi                                                          ⠧ |         8 | cdiidi                                                          ✔ |         9 | cdiidi [0.5s]
#> ⠏ |         0 | contrcad                                                        ✔ |         1 | contrcad
#> ⠏ |         0 | convert_to                                                      ✔ |         2 | convert_to
#> ⠏ |         0 | cotahist                                                        ⠋ |         1 | cotahist                                                        ⠸ |         4 | cotahist                                                        ⠸ |        14 | cotahist                                                        ⠼ |        25 | cotahist                                                        ⠴ |   1    35 | cotahist                                                        ⠇ |   4    35 | cotahist                                                        ⠙ |   6    36 | cotahist                                                        ⠸ |   8    36 | cotahist                                                        ✔ |   9    37 | cotahist [3.1s]
#> ────────────────────────────────────────────────────────────────────────────────
#> Warning (']8;line = 87:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate.underlying"` instead of `.data$refdate.underlying`
#> Backtrace:
#>   1. rb3::cotahist_equity_options_superset(ch, yc)
#>        at ]8;line = 87:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87:2]8;;
#>   5. dplyr:::select.data.frame(...)
#>   8. tidyselect::eval_select(expr(c(...)), .data)
#>   9. tidyselect:::eval_select_impl(...)
#>  13. tidyselect:::vars_select_eval(...)
#>  14. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  15. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  16. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  17. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 87:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"cod_isin"` instead of `.data$cod_isin`
#> Backtrace:
#>   1. rb3::cotahist_equity_options_superset(ch, yc)
#>        at ]8;line = 87:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87:2]8;;
#>   5. dplyr:::select.data.frame(...)
#>   8. tidyselect::eval_select(expr(c(...)), .data)
#>   9. tidyselect:::eval_select_impl(...)
#>  13. tidyselect:::vars_select_eval(...)
#>  14. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  15. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  16. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  17. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 87:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::cotahist_equity_options_superset(ch, yc)
#>        at ]8;line = 87:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87:2]8;;
#>   9. dplyr:::select.data.frame(...)
#>  12. tidyselect::eval_select(expr(c(...)), .data)
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  20. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  21. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 87:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"forward_date"` instead of `.data$forward_date`
#> Backtrace:
#>   1. rb3::cotahist_equity_options_superset(ch, yc)
#>        at ]8;line = 87:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87:2]8;;
#>   9. dplyr:::select.data.frame(...)
#>  12. tidyselect::eval_select(expr(c(...)), .data)
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  20. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  21. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 87:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"r_252"` instead of `.data$r_252`
#> Backtrace:
#>   1. rb3::cotahist_equity_options_superset(ch, yc)
#>        at ]8;line = 87:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:87:2]8;;
#>   9. dplyr:::select.data.frame(...)
#>  12. tidyselect::eval_select(expr(c(...)), .data)
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  20. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  21. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 89:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"cod_isin"` instead of `.data$cod_isin`
#> Backtrace:
#>   1. rb3::cotahist_options_by_symbol_superset("PETR4", ch, yc)
#>        at ]8;line = 89:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89:2]8;;
#>   5. dplyr:::select.data.frame(...)
#>   8. tidyselect::eval_select(expr(c(...)), .data)
#>   9. tidyselect:::eval_select_impl(...)
#>  13. tidyselect:::vars_select_eval(...)
#>  14. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  15. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  16. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  17. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 89:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::cotahist_options_by_symbol_superset("PETR4", ch, yc)
#>        at ]8;line = 89:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89:2]8;;
#>   9. dplyr:::select.data.frame(...)
#>  12. tidyselect::eval_select(expr(c(...)), .data)
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  20. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  21. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 89:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"forward_date"` instead of `.data$forward_date`
#> Backtrace:
#>   1. rb3::cotahist_options_by_symbol_superset("PETR4", ch, yc)
#>        at ]8;line = 89:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89:2]8;;
#>   9. dplyr:::select.data.frame(...)
#>  12. tidyselect::eval_select(expr(c(...)), .data)
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  20. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  21. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 89:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89]8;;'): it should use cotahist_equity_options_superset
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"r_252"` instead of `.data$r_252`
#> Backtrace:
#>   1. rb3::cotahist_options_by_symbol_superset("PETR4", ch, yc)
#>        at ]8;line = 89:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-cotahist.Rtest-cotahist.R:89:2]8;;
#>   9. dplyr:::select.data.frame(...)
#>  12. tidyselect::eval_select(expr(c(...)), .data)
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  20. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  21. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> ────────────────────────────────────────────────────────────────────────────────
#> ⠏ |         0 | downloaders                                                     ⠋ |         1 | downloaders                                                     ⠼ |         5 | downloaders                                                     ⠏ |        10 | downloaders                                                     ⠙ |        12 | downloaders                                                     ⠹ |        13 | downloaders                                                     ⠼ |        15 | downloaders                                                     ⠦ |        17 | downloaders                                                     ✔ |        17 | downloaders [9.0s]
#> ⠏ |         0 | fields                                                          ⠹ |        13 | fields                                                          ✔ |        13 | fields [0.1s]
#> ⠏ |         0 | file                                                            ⠧ |        18 | file                                                            ✔ |        19 | file [0.1s]
#> ⠏ |         0 | futures                                                         ⠋ |         1 | futures                                                         ⠸ |         4 | futures                                                         ⠧ |         8 | futures                                                         ✔ |        26 | futures [4.3s]
#> ⠏ |         0 | indexes                                                         ⠴ |         6 | indexes                                                         ⠦ |         7 | indexes                                                         ⠹ |        13 | indexes                                                         ⠴ |        16 | indexes                                                         ⠇ |   1    18 | indexes                                                         ⠋ |   3    18 | indexes                                                         ⠹ |   5    18 | indexes                                                         ⠸ |   6    18 | indexes                                                         ⠴ |   8    18 | indexes                                                         ⠇ |   11    18 | indexes                                                        ⠙ |   14    18 | indexes                                                        ⠧ |   16    22 | indexes                                                        ⠋ |   19    22 | indexes                                                        ⠹ |   21    22 | indexes                                                        ⠴ |   24    22 | indexes                                                        ⠧ |   26    22 | indexes                                                        ⠋ |   29    22 | indexes                                                        ⠹ |   31    22 | indexes                                                        ⠴ |   34    22 | indexes                                                        ⠧ |   36    22 | indexes                                                        ⠙ |   40    22 | indexes                                                        ⠹ |   41    22 | indexes                                                        ⠴ |   44    22 | indexes                                                        ⠧ |   46    22 | indexes                                                        ⠋ |   49    22 | indexes                                                        ⠹ |   51    22 | indexes                                                        ⠴ |   54    22 | indexes                                                        ⠧ |   56    22 | indexes                                                        ⠋ |   59    22 | indexes                                                        ⠹ |   61    22 | indexes                                                        ⠴ |   64    22 | indexes                                                        ⠧ |   66    22 | indexes                                                        ⠋ |   69    22 | indexes                                                        ⠹ |   71    22 | indexes                                                        ⠦ |   75    22 | indexes                                                        ⠧ |   76    22 | indexes                                                        ⠋ |   79    22 | indexes                                                        ⠹ |   81    22 | indexes                                                        ⠴ |   84    22 | indexes                                                        ⠧ |   86    22 | indexes                                                        ⠙ |   90    22 | indexes                                                        ⠹ |   91    22 | indexes                                                        ⠴ |   94    22 | indexes                                                        ⠧ |   96    22 | indexes                                                        ⠋ |   99    22 | indexes                                                        ⠹ |   101    22 | indexes                                                       ⠦ |   105    22 | indexes                                                       ⠧ |   106    22 | indexes                                                       ⠋ |   109    22 | indexes                                                       ⠹ |   111    22 | indexes                                                       ⠴ |   114    22 | indexes                                                       ⠧ |   116    22 | indexes                                                       ⠋ |   119    22 | indexes                                                       ⠹ |   121    22 | indexes                                                       ⠦ |   125    22 | indexes                                                       ⠏ |   128    22 | indexes                                                       ⠸ |   132    22 | indexes                                                       ⠦ |   135    22 | indexes                                                       ⠋ |   139    22 | indexes                                                       ⠧ |   142    26 | indexes                                                       ⠙ |   146    26 | indexes                                                       ⠴ |   150    26 | indexes                                                       ✔ |   150    31 | indexes [11.1s]
#> ────────────────────────────────────────────────────────────────────────────────
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>  10. tidyr:::pivot_longer.data.frame(...)
#>  11. tidyr::build_longer_spec(...)
#>  12. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  20. tidyselect:::walk_data_tree(...)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>  10. tidyr:::pivot_longer.data.frame(...)
#>  11. tidyr::build_longer_spec(...)
#>  12. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  20. tidyselect:::walk_data_tree(...)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>  10. tidyr:::pivot_longer.data.frame(...)
#>  11. tidyr::build_longer_spec(...)
#>  12. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  20. tidyselect:::walk_data_tree(...)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>  10. tidyr:::pivot_longer.data.frame(...)
#>  11. tidyr::build_longer_spec(...)
#>  12. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  20. tidyselect:::walk_data_tree(...)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>  10. tidyr:::pivot_longer.data.frame(...)
#>  11. tidyr::build_longer_spec(...)
#>  12. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  20. tidyselect:::walk_data_tree(...)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>  10. tidyr:::pivot_longer.data.frame(...)
#>  11. tidyr::build_longer_spec(...)
#>  12. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  13. tidyselect:::eval_select_impl(...)
#>  17. tidyselect:::vars_select_eval(...)
#>  18. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  19. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  20. tidyselect:::walk_data_tree(...)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 52:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("2020-01-01"))
#>        at ]8;line = 52:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:52:2]8;;
#>   2. purrr::map_dfr(...)
#>        at ]8;line = 301:col = 6;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:6]8;;
#>   3. purrr::map(.x, .f, ...)
#>   4. rb3 (local) .f(.x[[i]], ...)
#>   5. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 301:col = 20;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:301:20]8;;
#>   7. dplyr:::select.data.frame(...)
#>  10. tidyselect::eval_select(expr(c(...)), .data)
#>  11. tidyselect:::eval_select_impl(...)
#>  15. tidyselect:::vars_select_eval(...)
#>  16. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  17. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  18. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  19. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  20. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  21. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 58:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"))
#>        at ]8;line = 58:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:58:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month01"` instead of `.data$month01`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"month12"` instead of `.data$month12`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>  11. tidyr:::pivot_longer.data.frame(...)
#>  12. tidyr::build_longer_spec(...)
#>  13. tidyselect::eval_select(enquo(cols), data[unique(names(data))])
#>  14. tidyselect:::eval_select_impl(...)
#>  18. tidyselect:::vars_select_eval(...)
#>  19. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  20. tidyselect:::eval_colon(expr, data_mask, context_mask)
#>  21. tidyselect:::walk_data_tree(...)
#>  22. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  23. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"index_name"` instead of `.data$index_name`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 64:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64]8;;'): it should get index historical data
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"value"` instead of `.data$value`
#> Backtrace:
#>   1. rb3::index_get(index_name, as.Date("1997-01-01"), as.Date("1999-01-01"))
#>        at ]8;line = 64:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-indexes.Rtest-indexes.R:64:2]8;;
#>   3. purrr::map_dfr(...)
#>   4. purrr::map(.x, .f, ...)
#>   5. rb3 (local) .f(.x[[i]], ...)
#>   6. rb3:::single_index_get(index_name, year, cache_folder, do_cache)
#>        at ]8;line = 311:col = 29;file:///home/quishqa/projects/rOpenSci/reviews/rb3/R/scraper-indexes.Rrb3/R/scraper-indexes.R:311:29]8;;
#>   8. dplyr:::select.data.frame(...)
#>  11. tidyselect::eval_select(expr(c(...)), .data)
#>  12. tidyselect:::eval_select_impl(...)
#>  16. tidyselect:::vars_select_eval(...)
#>  17. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  18. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  19. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  20. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  21. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  22. tidyselect:::call_kind(expr, context_mask, error_call)
#> ────────────────────────────────────────────────────────────────────────────────
#> ⠏ |         0 | indic                                                           ✔ |         1 | indic
#> ⠏ |         0 | PUWEB                                                           ✔ |         2 | PUWEB
#> ⠏ |         0 | readers                                                         ⠋ |         1 | readers                                                         ⠙ |         2 | readers                                                         ⠏ |        10 | readers                                                         ✔ |        12 | readers [0.8s]
#> ⠏ |         0 | transmute                                                       ⠇ |        19 | transmute                                                       ⠸ |        44 | transmute                                                       ⠋ |        61 | transmute                                                       ⠇ |        79 | transmute                                                       ✔ |        80 | transmute [0.4s]
#> ⠏ |         0 | yc                                                              ⠋ |         1 | yc                                                              ⠸ |         4 | yc                                                              ⠧ |         8 | yc                                                              ⠼ |        15 | yc                                                              ⠧ |        18 | yc                                                              ⠙ |        22 | yc                                                              ⠇ |        29 | yc                                                              ⠙ |        32 | yc                                                              ⠴ |        36 | yc                                                              ⠹ |   1    42 | yc                                                              ⠧ |   4    44 | yc                                                              ⠹ |   7    46 | yc                                                              ✔ |   9    48 | yc [7.2s]
#> ────────────────────────────────────────────────────────────────────────────────
#> Warning (']8;line = 138:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:138]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::yc_superset(yc, fut)
#>        at ]8;line = 138:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:138:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 138:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:138]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"forward_date"` instead of `.data$forward_date`
#> Backtrace:
#>   1. rb3::yc_superset(yc, fut)
#>        at ]8;line = 138:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:138:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 138:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:138]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"symbol"` instead of `.data$symbol`
#> Backtrace:
#>   1. rb3::yc_superset(yc, fut)
#>        at ]8;line = 138:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:138:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 142:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:142]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::yc_usd_superset(yc, fut)
#>        at ]8;line = 142:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:142:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 142:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:142]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"forward_date"` instead of `.data$forward_date`
#> Backtrace:
#>   1. rb3::yc_usd_superset(yc, fut)
#>        at ]8;line = 142:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:142:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 142:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:142]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"symbol"` instead of `.data$symbol`
#> Backtrace:
#>   1. rb3::yc_usd_superset(yc, fut)
#>        at ]8;line = 142:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:142:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 146:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:146]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"refdate"` instead of `.data$refdate`
#> Backtrace:
#>   1. rb3::yc_ipca_superset(yc, fut)
#>        at ]8;line = 146:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:146:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 146:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:146]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"forward_date"` instead of `.data$forward_date`
#> Backtrace:
#>   1. rb3::yc_ipca_superset(yc, fut)
#>        at ]8;line = 146:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:146:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> 
#> Warning (']8;line = 146:col = 1;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:146]8;;'): Test of yc_superset function
#> Use of .data in tidyselect expressions was deprecated in tidyselect 1.2.0.
#> i Please use `"symbol"` instead of `.data$symbol`
#> Backtrace:
#>   1. rb3::yc_ipca_superset(yc, fut)
#>        at ]8;line = 146:col = 2;file:///home/quishqa/projects/rOpenSci/reviews/rb3/tests/testthat/test-yc.Rtest-yc.R:146:2]8;;
#>   3. dplyr:::select.data.frame(...)
#>   6. tidyselect::eval_select(expr(c(...)), .data)
#>   7. tidyselect:::eval_select_impl(...)
#>  11. tidyselect:::vars_select_eval(...)
#>  12. tidyselect:::walk_data_tree(expr, data_mask, context_mask)
#>  13. tidyselect:::eval_c(expr, data_mask, context_mask)
#>  14. tidyselect:::reduce_sels(node, data_mask, context_mask, init = init)
#>  15. tidyselect:::walk_data_tree(new, data_mask, context_mask)
#>  16. tidyselect:::expr_kind(expr, context_mask, error_call)
#>  17. tidyselect:::call_kind(expr, context_mask, error_call)
#> ────────────────────────────────────────────────────────────────────────────────
#> 
#> ══ Results ═════════════════════════════════════════════════════════════════════
#> Duration: 41.2 s
#> 
#> [ FAIL 0 | WARN 168 | SKIP 0 | PASS 315 ]
```

#### **comments:**

<!-- record comments on tests here -->

------------------------------------------------------------------------

### check `rb3` for goodpractice:

``` r
goodpractice::gp(pkg_dir)
#> Preparing: covr
#> Preparing: cyclocomp
#> 
#>      checking for file ‘/tmp/RtmplxABwy/remotesc48e4f0231a5/rb3/DESCRIPTION’ ...  ✔  checking for file ‘/tmp/RtmplxABwy/remotesc48e4f0231a5/rb3/DESCRIPTION’
#>   ─  preparing ‘rb3’:
#>      checking DESCRIPTION meta-information ...  ✔  checking DESCRIPTION meta-information
#>      checking vignette meta-information ...  ✔  checking vignette meta-information
#>   ─  checking for LF line-endings in source and make files and shell scripts
#>   ─  checking for empty or unneeded directories
#>   ─  building ‘rb3_0.0.7.tar.gz’
#>      
#> 
#> Preparing: description
#> Preparing: lintr
#> Preparing: namespace
#> Preparing: rcmdcheck
#> ── GP rb3 ──────────────────────────────────────────────────────────────────────
#> 
#> It is good practice to
#> 
#>   ✖ write unit tests for all functions, and all package code in
#>     general. 81% of code lines are covered by test cases.
#> 
#>     R/addin-display-template.R:16:NA
#>     R/addin-display-template.R:17:NA
#>     R/addin-display-template.R:18:NA
#>     R/addin-display-template.R:19:NA
#>     R/addin-display-template.R:20:NA
#>     ... and 277 more lines
#> 
#>   ✖ avoid long code lines, it is bad for readability. Also, many people
#>     prefer editor windows that are about 80 characters wide. Try make
#>     your lines shorter than 80 characters
#> 
#>     R/scraper-futures.R:105:81
#>     R/scraper-indexes.R:148:81
#>     R/scraper-yc.R:4:81
#>     R/scraper-yc.R:10:81
#> 
#>   ✖ avoid sapply(), it is not type safe. It might return a vector, or a
#>     list, depending on the input data. Consider using vapply() instead.
#> 
#>     tests/testthat/test-transmute.R:197:12
#>     tests/testthat/test-transmute.R:301:19
#>     tests/testthat/test-transmute.R:312:12
#> 
#>   ✖ fix this R CMD check WARNING: LaTeX errors when creating PDF
#>     version. This typically indicates Rd problems. LaTeX errors found:
#>     ! LaTeX Error: File `inconsolata.sty' not found. Type X to quit or
#>     <RETURN> to proceed, or enter new name. (Default extension: sty) !
#>     Emergency stop. <read *> l.297 ^^M !  ==> Fatal error occurred, no
#>     output PDF file produced!
#> ────────────────────────────────────────────────────────────────────────────────
```

#### **comments:**

-   As noted by @ there are still issues in the unit test of the
    function with a coverage of 35 %. The errors of 80 character are
    unovoidable as are related to urls.
    <!-- record comments on goodpractice here -->

## Check package metadata files

### inspect

-   #### [README](https://github.com/wilsonfreitas/rb3)

-   #### [DESCRIPTION](https://github.com/wilsonfreitas/rb3/blob/master/DESCRIPTION)

-   #### [NAMESPACE](https://github.com/wilsonfreitas/rb3/blob/master/NAMESPACE)

### spell check

``` r
devtools::spell_check(pkg_dir)
#> DESCRIPTION does not contain 'Language' field. Defaulting to 'en-US'.
#>   WORD           FOUND IN
#> ’s           README.md:42
#> accross        rb3-package.Rd:22
#>                NEWS.md:37
#> addin          display_template.Rd:14
#>                show_templates.Rd:14
#> Addin          display_template.Rd:10
#>                show_templates.Rd:10
#> aditional      download_marketdata.Rd:17
#> BDR            README.md:238
#>                README.rmd:178
#> bdrs           cotahist_get.Rd:30
#> BDRs           cotahist-extracts.Rd:52
#>                README.md:32,236
#>                README.rmd:36,176
#> bizdays        NEWS.md:43
#> BMF            read_marketdata.Rd:36
#> Bovespa        read_marketdata.Rd:36
#> brazilian      README.md:210
#>                README.rmd:165
#>                B3-Indexes.Rmd:102
#> cachedir       cachedir.Rd:19
#>                cotahist_get.Rd:22
#>                download_marketdata.Rd:12
#>                futures_get.Rd:25
#>                index_by_segment_get.Rd:12
#>                index_comp_get.Rd:12
#>                index_get.Rd:22
#>                index_weights_get.Rd:12
#>                indexes_get.Rd:10
#>                indexes_last_update.Rd:10
#>                indexreport_get.Rd:29
#>                yc_get.Rd:49
#> cdi            NEWS.md:18
#> CDI            cdi-idi.Rd:7,14,17
#> Codecov        README.md:12
#>                README.rmd:20
#> codeCVM        NEWS.md:54
#> codemeta       NEWS.md:44
#> compositon     B3-Indexes.Rmd:37
#> compostion     B3-Indexes.Rmd:37
#> cotahist       cotahist-extracts.Rd:46
#>                cotahist-options-superset.Rd:14
#>                NEWS.md:59
#> COTAHIST       cotahist_get.Rd:5,38
#>                cotahist-extracts.Rd:17,44,52
#>                README.md:316
#>                README.rmd:211
#> Cupom          yc_get.Rd:64
#>                Fetching-historical-yield-curve.Rmd:96
#> DAP            Fetching-historical-future-rates.Rmd:81
#> DAPF           Fetching-historical-future-rates.Rmd:115
#> de             README.md:212
#>                README.rmd:167
#> depositary     README.md:238
#>                README.rmd:178
#> downloader     NEWS.md:81
#> ETFs           cotahist_get.Rd:30
#>                cotahist-extracts.Rd:52
#> FEV            NEWS.md:10
#> FII            README.md:30,212
#>                README.rmd:34,167
#> FIIs           README.md:210
#>                README.rmd:165
#> fixedincome    NEWS.md:27
#> formated       cotahist_get.Rd:16,17
#> Fundo          README.md:212
#>                README.rmd:167
#> Github         README.md:55
#>                README.rmd:57
#> IBOVESPA       B3-Indexes.Rmd:37,102
#> IBr            B3-Indexes.Rmd:46
#> idi            NEWS.md:18
#> IDI            cdi-idi.Rd:7,14,18
#> Imobiliário   README.md:212
#>                README.rmd:167
#> importFrom     NEWS.md:36
#> intraday       NEWS.md:33,34,35
#> Investimento   README.md:212
#>                README.rmd:167
#> IPCA           yc_get.Rd:65,78,84
#>                Fetching-historical-yield-curve.Rmd:63
#> JSON           NEWS.md:81
#> limpo          yc_get.Rd:64
#> Limpo          Fetching-historical-yield-curve.Rmd:96
#> marketdata     convert_to.Rd:40
#>                read_marketdata.Rd:38
#> md             NEWS.md:44
#> OHLC           indexreport_get.Rd:36
#> oscilation     indexreport_get.Rd:36
#> pkgdown        README.md:50
#>                README.rmd:52
#> practioneers   README.md:42
#>                README.rmd:44
#> Pre            yc_get.Rd:63
#>                Fetching-historical-yield-curve.Rmd:30
#> rb             cachedir.Rd:5,10,13
#>                rb3-package.Rd:12,14,19,36
#>                NEWS.md:1,12,20,29,40,74,83
#>                README.md:4,38,42,55,343
#>                README.rmd:16,40,44,57,224
#> rcmdcheck      README.md:14
#>                README.rmd:21
#> refdate        NEWS.md:10
#> Reits          README.md:30
#>                README.rmd:34
#> REITs          README.md:210
#>                README.rmd:165
#> ropensci       NEWS.md:44,76
#> rOpenSci       README.md:19
#>                README.rmd:24
#> RStudio        display_template.Rd:13
#>                show_templates.Rd:13
#> SMLL           B3-Indexes.Rmd:120
#> theorical      index_weights_get.Rd:18
#> throught       B3-Indexes.Rmd:37
#> tibble         index_get.Rd:27
#>                yc_get.Rd:56
#> UNITs          cotahist-extracts.Rd:53
#> valueable      cotahist_get.Rd:26
#> webscraping    README.md:36
#>                README.rmd:40
#> YAML           README.md:343
#>                README.rmd:224
#> yc             NEWS.md:42
#> yeild          README.md:71
#>                README.rmd:73
#> YYYY           futures_get.Rd:19,21,32
#>                indexreport_get.Rd:23,25,33
#>                yc_get.Rd:43,45,53
```

#### **comments:**

-   There are minor typos in english documentation.

<!-- record comments on metadata files here -->

------------------------------------------------------------------------

## Check documentation

online documentation: **<https://wilsonfreitas.github.io/rb3/>**

-   Is the
    [documentation](https://ropensci.github.io/dev_guide/building.html#documentation)
    (installation instructions/vignettes/examples/demos) clear and
    sufficient?

### test `rb3` function help files:

``` r
help(package = "rb3")
```

#### **comments:**

<!-- record comments on help files here -->

------------------------------------------------------------------------

### test `rb3` vignettes:

``` r
vignette(package = "rb3")
#> no vignettes found
```

#### **comments:**

<!-- record comments on vignettes here -->

------------------------------------------------------------------------

## Test functionality:

-   Are there **user interface improvements** that could be made?
-   Are there **performance improvements** that could be made?

``` r
library("rb3")
```

``` r
exports <-ls("package:rb3")
exports
#>   [1] "%or%"                                    
#>   [2] "add.bizdays"                             
#>   [3] "alert"                                   
#>   [4] "alert_fun"                               
#>   [5] "apply_rule"                              
#>   [6] "apply_rule.class_rule"                   
#>   [7] "apply_rule.predicate_rule"               
#>   [8] "apply_rule.regex_rule"                   
#>   [9] "apply_rules"                             
#>  [10] "arrange"                                 
#>  [11] "as_dbl"                                  
#>  [12] "as_tibble"                               
#>  [13] "as.data.frame.fields"                    
#>  [14] "ascii"                                   
#>  [15] "base64_datetime_download"                
#>  [16] "base64encode"                            
#>  [17] "bind_rows"                               
#>  [18] "bizdayse"                                
#>  [19] "bizseq"                                  
#>  [20] "cachedir"                                
#>  [21] "cdi_get"                                 
#>  [22] "check_parameters"                        
#>  [23] "ck_if_null"                              
#>  [24] "clearcache"                              
#>  [25] "cli_alert_danger"                        
#>  [26] "cli_alert_info"                          
#>  [27] "cli_alert_success"                       
#>  [28] "cli_alert_warning"                       
#>  [29] "cli_progress_along"                      
#>  [30] "code2month"                              
#>  [31] "code2month_newcode"                      
#>  [32] "code2month_oldcode"                      
#>  [33] "cols_number"                             
#>  [34] "company_cash_dividends_download"         
#>  [35] "company_cash_dividends_reader"           
#>  [36] "company_details_download"                
#>  [37] "company_details_reader"                  
#>  [38] "company_listed_supplement_download"      
#>  [39] "company_listed_supplement_reader"        
#>  [40] "composite"                               
#>  [41] "content"                                 
#>  [42] "convert_to"                              
#>  [43] "copy_file_to_temp"                       
#>  [44] "cotahist_bdrs_get"                       
#>  [45] "cotahist_equity_get"                     
#>  [46] "cotahist_equity_options_get"             
#>  [47] "cotahist_equity_options_superset"        
#>  [48] "cotahist_etfs_get"                       
#>  [49] "cotahist_fiagros_get"                    
#>  [50] "cotahist_fidcs_get"                      
#>  [51] "cotahist_fiis_get"                       
#>  [52] "cotahist_funds_options_get"              
#>  [53] "cotahist_get"                            
#>  [54] "cotahist_get_symbols"                    
#>  [55] "cotahist_index_options_get"              
#>  [56] "cotahist_indexes_get"                    
#>  [57] "cotahist_options_by_symbol_superset"     
#>  [58] "cotahist_units_get"                      
#>  [59] "csv_read_file"                           
#>  [60] "curve_download"                          
#>  [61] "curve_read"                              
#>  [62] "datetime_download"                       
#>  [63] "digest"                                  
#>  [64] "display_template"                        
#>  [65] "download_marketdata"                     
#>  [66] "field"                                   
#>  [67] "fields"                                  
#>  [68] "fields_description"                      
#>  [69] "fields_handlers"                         
#>  [70] "fields_names"                            
#>  [71] "fields_widths"                           
#>  [72] "Filename"                                
#>  [73] "filter"                                  
#>  [74] "filter_equity_data"                      
#>  [75] "flatten_names"                           
#>  [76] "following"                               
#>  [77] "format_equity"                           
#>  [78] "format_options"                          
#>  [79] "fromJSON"                                
#>  [80] "futures_get"                             
#>  [81] "futures_mget"                            
#>  [82] "fwf_read_file"                           
#>  [83] "GET"                                     
#>  [84] "get_single_indexreport"                  
#>  [85] "get_single_marketdata"                   
#>  [86] "get_single_yc"                           
#>  [87] "get_single_yc_ipca"                      
#>  [88] "get_single_yc_usd"                       
#>  [89] "getdate"                                 
#>  [90] "getFromNamespace"                        
#>  [91] "getNodeSet"                              
#>  [92] "hasName"                                 
#>  [93] "headers"                                 
#>  [94] "html_element"                            
#>  [95] "html_nodes"                              
#>  [96] "html_table"                              
#>  [97] "html_text"                               
#>  [98] "ibovespa_index_get"                      
#>  [99] "idi_get"                                 
#> [100] "index_by_segment_get"                    
#> [101] "index_comp_get"                          
#> [102] "index_get"                               
#> [103] "index_get_from_file"                     
#> [104] "index_weights_get"                       
#> [105] "indexes_get"                             
#> [106] "indexes_last_update"                     
#> [107] "indexreport_get"                         
#> [108] "indexreport_mget"                        
#> [109] "indexreport_reader"                      
#> [110] "inner_join"                              
#> [111] "is"                                      
#> [112] "iter_rules"                              
#> [113] "json_read_file"                          
#> [114] "just_download_data"                      
#> [115] "left_join"                               
#> [116] "library.dynam"                           
#> [117] "library.dynam.unload"                    
#> [118] "load_builtin_calendars"                  
#> [119] "load_templates"                          
#> [120] "log_map_process_along"                   
#> [121] "map"                                     
#> [122] "map_chr"                                 
#> [123] "map_dfr"                                 
#> [124] "map_int"                                 
#> [125] "map_lgl"                                 
#> [126] "MarketData"                              
#> [127] "match_class"                             
#> [128] "match_predicate"                         
#> [129] "match_regex"                             
#> [130] "maturity2date"                           
#> [131] "maturity2date_newcode"                   
#> [132] "maturity2date_oldcode"                   
#> [133] "mcsv_read_file"                          
#> [134] "mfwf_read_file"                          
#> [135] "mutate"                                  
#> [136] "new"                                     
#> [137] "new_field"                               
#> [138] "new_part"                                
#> [139] "new_template"                            
#> [140] "options_open_interest_read"              
#> [141] "parse_columns"                           
#> [142] "parse_text"                              
#> [143] "parse_url"                               
#> [144] "parser_generic"                          
#> [145] "parsers"                                 
#> [146] "pass_thru_handler"                       
#> [147] "pb_bar"                                  
#> [148] "pb_current"                              
#> [149] "pb_eta_str"                              
#> [150] "pb_percent"                              
#> [151] "pb_spin"                                 
#> [152] "pb_total"                                
#> [153] "pivot_longer"                            
#> [154] "POST"                                    
#> [155] "preceding"                               
#> [156] "pricereport_reader"                      
#> [157] "print"                                   
#> [158] "print.fields"                            
#> [159] "print.parts"                             
#> [160] "proto"                                   
#> [161] "query_cdi"                               
#> [162] "read_csv"                                
#> [163] "read_excel"                              
#> [164] "read_file"                               
#> [165] "read_fwf"                                
#> [166] "read_html"                               
#> [167] "read_marketdata"                         
#> [168] "read_rds"                                
#> [169] "read.table"                              
#> [170] "registry"                                
#> [171] "rule_result"                             
#> [172] "save_resource"                           
#> [173] "select"                                  
#> [174] "settlement_prices_download"              
#> [175] "settlement_prices_read"                  
#> [176] "show_templates"                          
#> [177] "simple_download"                         
#> [178] "single_futures_get"                      
#> [179] "single_index_get"                        
#> [180] "slot"                                    
#> [181] "status_code"                             
#> [182] "stock_indexes_composition_download"      
#> [183] "stock_indexes_composition_reader"        
#> [184] "stock_indexes_current_portfolio_download"
#> [185] "stock_indexes_json_reader"               
#> [186] "stock_indexes_statistics_download"       
#> [187] "stock_indexes_theo_portfolio_download"   
#> [188] "str_c"                                   
#> [189] "str_detect"                              
#> [190] "str_ends"                                
#> [191] "str_glue"                                
#> [192] "str_length"                              
#> [193] "str_match"                               
#> [194] "str_pad"                                 
#> [195] "str_replace"                             
#> [196] "str_replace_all"                         
#> [197] "str_split"                               
#> [198] "str_starts"                              
#> [199] "str_sub"                                 
#> [200] "str_to_lower"                            
#> [201] "str_trim"                                
#> [202] "system.file"                             
#> [203] "take"                                    
#> [204] "take.list"                               
#> [205] "tibble"                                  
#> [206] "to_date"                                 
#> [207] "to_date_handler"                         
#> [208] "to_datetime"                             
#> [209] "to_dbl"                                  
#> [210] "to_factor_handler"                       
#> [211] "to_int"                                  
#> [212] "to_numeric_handler"                      
#> [213] "to_strtime_handler"                      
#> [214] "to_time_handler"                         
#> [215] "toJSON"                                  
#> [216] "transmute_regex"                         
#> [217] "transmuter"                              
#> [218] "trim_fields"                             
#> [219] "unfactor"                                
#> [220] "unformat"                                
#> [221] "unzip"                                   
#> [222] "unzip_recursive"                         
#> [223] "url_encoded_download"                    
#> [224] "width"                                   
#> [225] "write_rds"                               
#> [226] "write.table"                             
#> [227] "xmlInternalTreeParse"                    
#> [228] "xmlValue"                                
#> [229] "yaml.load_file"                          
#> [230] "yc_get"                                  
#> [231] "yc_ipca_get"                             
#> [232] "yc_ipca_mget"                            
#> [233] "yc_ipca_superset"                        
#> [234] "yc_mget"                                 
#> [235] "yc_superset"                             
#> [236] "yc_usd_get"                              
#> [237] "yc_usd_mget"                             
#> [238] "yc_usd_superset"
```

<!-- experiment with package functions -->

#### **comments:**

<!-- record comments on package experimentation here -->

------------------------------------------------------------------------

## Inspect code:

-   Does the package **comply with the [ROpenSci packaging
    guide](https://ropensci.github.io/dev_guide/building.html)**?
    -   good [function & variable
        naming?](https://ropensci.github.io/dev_guide/building.html#function-and-argument-naming)
    -   good [dependency
        management](https://ropensci.github.io/dev_guide/building.html#package-dependencies)?
-   Are there **improvements** that could be made to the [**code
    style?**](https://ropensci.github.io/dev_guide/building.html#code-style)
-   Is there **code duplication** in the package that should be reduced?

``` r
pkgreviewr::pkgreview_print_source("rb3")
#> ## %or%
#> function(value, other) {
#>   if (!is.null(value)) value else other
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## add.bizdays
#> function (dates, n, cal) 
#> UseMethod("add.bizdays")
#> <bytecode: 0x55b96bd787a0>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## alert
#> function(x = c("info", "success", "danger", "warning"), text, ...) {
#>   x <- match.arg(x)
#>   rb3_silent <- getOption("rb3.silent")
#>   if (!is.null(rb3_silent) && isTRUE(rb3_silent)) {
#>     # do nothing
#>   } else {
#>     f_ <- alert_fun(x)
#>     if (! is.null(f_)) {
#>       f_(str_glue(text, .envir = list(...)))
#>     }
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## alert_fun
#> function(x) {
#>   funcs <- list(
#>     info = cli_alert_info,
#>     danger = cli_alert_danger,
#>     success = cli_alert_success,
#>     warning = cli_alert_warning
#>   )
#>   func <- funcs[[x]]
#>   if (is.null(func)) {
#>     warning(paste0("Invalid call to alert function ", x))
#>     return(NULL)
#>   } else {
#>     func
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## apply_rule
#> function(rule, .data) {
#>   UseMethod("apply_rule")
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## apply_rule.class_rule
#> function(rule, .data) {
#>   if (!is(.data, rule$class)) {
#>     return(rule_result())
#>   }
#>   result <- rule$handler(.data)
#>   rule_result(TRUE, result)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## apply_rule.predicate_rule
#> function(rule, .data) {
#>   idx <- rule$predicate(.data)
#>   if (length(which(idx)) == 0) {
#>     return(rule_result())
#>   }
#>   result <- rule$handler(.data, idx)
#>   rule_result(TRUE, result)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## apply_rule.regex_rule
#> function(rule, .data) {
#>   if (!is(.data, "character")) {
#>     return(rule_result())
#>   }
#>   detect <- str_detect(.data, rule$regex)
#>   apply_to <- rule$apply_to(detect, na.rm = rule$na.rm)
#>   result <- if (apply_to) {
#>     rule$handler(
#>       .data,
#>       str_match(.data, rule$regex)
#>     )
#>   }
#>   rule_result(apply_to, result)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## apply_rules
#> function(x, data, ...) standardGeneric("apply_rules")
#> <environment: 0x55b97617a2b0>
#> attr(,"generic")
#> [1] "apply_rules"
#> attr(,"generic")attr(,"package")
#> [1] "rb3"
#> attr(,"package")
#> [1] "rb3"
#> attr(,"group")
#> list()
#> attr(,"valueClass")
#> character(0)
#> attr(,"signature")
#> [1] "x"    "data"
#> attr(,"default")
#> `\001NULL\001`
#> attr(,"skeleton")
#> (function (x, data, ...) 
#> stop(gettextf("invalid call in method dispatch to '%s' (no default method)", 
#>     "apply_rules"), domain = NA))(x, data, ...)
#> attr(,"class")
#> [1] "standardGeneric"
#> attr(,"class")attr(,"package")
#> [1] "methods"
#> --- 
#>  
#> ## arrange
#> function (.data, ..., .by_group = FALSE) 
#> {
#>     UseMethod("arrange")
#> }
#> <bytecode: 0x55b96b194640>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## as_dbl
#> function(x, dec = NULL, thousands = NULL, percent = FALSE) {
#>   .func <- to_dbl(dec, thousands, percent)
#>   .func(x)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## as_tibble
#> function (x, ..., .rows = NULL, .name_repair = c("check_unique", 
#>     "unique", "universal", "minimal"), rownames = pkgconfig::get_config("tibble::rownames", 
#>     NULL)) 
#> {
#>     UseMethod("as_tibble")
#> }
#> <bytecode: 0x55b96a73db38>
#> <environment: namespace:tibble>
#> --- 
#>  
#> ## as.data.frame.fields
#> function(x, ...) {
#>   data.frame(
#>     `Field name` = fields_names(x),
#>     `Description` = fields_description(x),
#>     `Width` = fields_widths(x),
#>     `Type` = map_chr(fields_handlers(x), function(y) attr(y, "type")),
#>     row.names = seq_along(x),
#>     check.names = FALSE
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## ascii
#> function (x, ...) 
#> {
#>     UseMethod("ascii")
#> }
#> <bytecode: 0x55b9761c4a30>
#> <environment: namespace:ascii>
#> --- 
#>  
#> ## base64_datetime_download
#> function(., dest, ...) {
#>   if (!datetime_download(., dest, ...)) {
#>     return(FALSE)
#>   }
#>   b64 <- scan(dest, "")
#>   txt <- rawToChar(base64enc::base64decode(b64))
#>   writeBin(txt, dest)
#>   TRUE
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## base64encode
#> function (what, linewidth, newline) 
#> {
#>     linewidth <- if (missing(linewidth) || !is.numeric(linewidth) || 
#>         length(linewidth) < 1L) 
#>         0L
#>     else as.integer(linewidth[1L])
#>     if (is.na(linewidth)) 
#>         linewidth <- 0L
#>     else if (linewidth > 0L && linewidth < 4L) 
#>         linewidth <- 4L
#>     if (missing(newline)) 
#>         newline <- NULL
#>     fi <- NULL
#>     if (is.character(what)) {
#>         what <- file(what, "rb")
#>         on.exit(close(what))
#>     }
#>     if (inherits(what, "connection")) {
#>         slice <- 65535L
#>         if (linewidth > 0L) {
#>             if (linewidth%%4L > 0) 
#>                 linewidth <- linewidth - linewidth%%4L
#>             bw <- as.integer(linewidth/4L) * 3L
#>             if (slice%%bw > 0L) 
#>                 slice <- slice + (bw - (slice%%bw))
#>         }
#>         l <- list()
#>         while (length(r <- readBin(what, raw(0), slice))) l <- c(l, 
#>             .Call(B64_encode, r, linewidth, newline))
#>         if (linewidth > 0L && is.null(newline)) 
#>             unlist(l)
#>         else paste(unlist(l), collapse = if (is.null(newline)) 
#>             ""
#>         else newline)
#>     }
#>     else .Call(B64_encode, as.raw(what), linewidth, newline)
#> }
#> <bytecode: 0x55b97db7bc58>
#> <environment: namespace:base64enc>
#> --- 
#>  
#> ## bind_rows
#> function (..., .id = NULL) 
#> {
#>     dots <- list2(...)
#>     is_flattenable <- function(x) vec_is_list(x) && !is_named(x)
#>     if (length(dots) == 1 && is_bare_list(dots[[1]])) {
#>         dots <- dots[[1]]
#>     }
#>     dots <- flatten_if(dots, is_flattenable)
#>     dots <- discard(dots, is.null)
#>     if (is_named(dots) && !all(map_lgl(dots, dataframe_ish))) {
#>         return(as_tibble(dots))
#>     }
#>     for (i in seq_along(dots)) {
#>         .x <- dots[[i]]
#>         if (!is.data.frame(.x) && !vec_is(.x)) {
#>             msg <- glue("Argument {i} must be a data frame or a named atomic vector.")
#>             abort(msg)
#>         }
#>         if (is.null(names(.x))) {
#>             msg <- glue("Argument {i} must have names.")
#>             abort(msg)
#>         }
#>     }
#>     if (!is_null(.id)) {
#>         if (!is_string(.id)) {
#>             msg <- glue("`.id` must be a scalar string, not {friendly_type_of(.id)} of length {length(.id)}.")
#>             abort(msg)
#>         }
#>         if (!is_named(dots)) {
#>             names(dots) <- seq_along(dots)
#>         }
#>     }
#>     if (!length(dots)) {
#>         return(tibble())
#>     }
#>     first <- dots[[1L]]
#>     dots <- map(dots, function(.x) {
#>         if (vec_is_list(.x)) {
#>             .x <- vctrs::data_frame(!!!.x, .name_repair = "minimal")
#>         }
#>         .x
#>     })
#>     if (is.null(.id)) {
#>         names(dots) <- NULL
#>     }
#>     out <- fix_call(vec_rbind(!!!dots, .names_to = .id))
#>     if (length(dots)) {
#>         if (is.data.frame(first)) {
#>             out <- dplyr_reconstruct(out, first)
#>         }
#>         else {
#>             out <- as_tibble(out)
#>         }
#>     }
#>     out
#> }
#> <bytecode: 0x55b9734ea680>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## bizdayse
#> function (dates, curd, cal) 
#> UseMethod("bizdayse")
#> <bytecode: 0x55b96bd4a570>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## bizseq
#> function (from, to, cal) 
#> UseMethod("bizseq")
#> <bytecode: 0x55b96bd42288>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## cachedir
#> function() {
#>   cache_folder <- getOption("rb3.cachedir")
#>   cache_folder <- if (is.null(cache_folder)) {
#>     file.path(tempdir(), "rb3-cache")
#>   } else {
#>     cache_folder
#>   }
#> 
#>   if (!dir.exists(cache_folder)) {
#>     dir.create(cache_folder, recursive = TRUE)
#>   }
#> 
#>   cache_folder
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cdi_get
#> function() {
#>   dx <- query_cdi()
#>   tibble(
#>     refdate = dx$dataTaxa,
#>     CDI = dx$taxa
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## check_parameters
#> function(..., arg_name) {
#>   args <- list(...)
#>   if (!hasName(args, arg_name)) {
#>     alert("danger", "{arg_name} argument not provided", arg_name = arg_name)
#>     FALSE
#>   } else {
#>     TRUE
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## ck_if_null
#> function(x) {
#>   if (is.null(x)) {
#>     ""
#>   } else {
#>     x
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## clearcache
#> function() {
#>   cache_folder <- cachedir()
#>   unlink(cache_folder, recursive = TRUE)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cli_alert_danger
#> function (text, id = NULL, class = NULL, wrap = FALSE, .envir = parent.frame()) 
#> {
#>     cli__message("alert_danger", list(text = glue_cmd(text, .envir = .envir, 
#>         .call = sys.call()), id = id, class = class, wrap = wrap))
#> }
#> <bytecode: 0x55b976661b60>
#> <environment: namespace:cli>
#> --- 
#>  
#> ## cli_alert_info
#> function (text, id = NULL, class = NULL, wrap = FALSE, .envir = parent.frame()) 
#> {
#>     cli__message("alert_info", list(text = glue_cmd(text, .envir = .envir, 
#>         .call = sys.call()), id = id, class = class, wrap = wrap))
#> }
#> <bytecode: 0x55b976658ac0>
#> <environment: namespace:cli>
#> --- 
#>  
#> ## cli_alert_success
#> function (text, id = NULL, class = NULL, wrap = FALSE, .envir = parent.frame()) 
#> {
#>     cli__message("alert_success", list(text = glue_cmd(text, 
#>         .envir = .envir, .call = sys.call()), id = id, class = class, 
#>         wrap = wrap))
#> }
#> <bytecode: 0x55b9766533f0>
#> <environment: namespace:cli>
#> --- 
#>  
#> ## cli_alert_warning
#> function (text, id = NULL, class = NULL, wrap = FALSE, .envir = parent.frame()) 
#> {
#>     cli__message("alert_warning", list(text = glue_cmd(text, 
#>         .envir = .envir, .call = sys.call()), id = id, class = class, 
#>         wrap = wrap))
#> }
#> <bytecode: 0x55b97664fc40>
#> <environment: namespace:cli>
#> --- 
#>  
#> ## cli_progress_along
#> function (x, name = NULL, total = length(x), ..., .envir = parent.frame()) 
#> {
#>     name
#>     total
#>     .envir
#>     list(...)
#>     if (getRversion() < "3.5.0") 
#>         return(seq_along(x))
#>     id <- cli_progress_bar(name = name, total = total, ..., .auto_close = FALSE, 
#>         .envir = .envir)
#>     closeenv <- sys.frame(-1)
#>     if (format(closeenv) != clienv$globalenv) {
#>         defer(cli_progress_done(id = id, .envir = .envir, result = "auto"), 
#>             envir = closeenv)
#>     }
#>     sax <- seq_along(x)
#>     clienv$progress[[id]]$caller <- .envir
#>     .Call(clic_progress_along, sax, clienv$progress[[id]])
#> }
#> <bytecode: 0x55b97664ad50>
#> <environment: namespace:cli>
#> --- 
#>  
#> ## code2month
#> function(x) {
#>   ifelse(
#>     str_length(x) == 1,
#>     code2month_newcode(x),
#>     code2month_oldcode(x)
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## code2month_newcode
#> function(x) {
#>   m <- c(
#>     F = 1, G = 2, H = 3, J = 4, K = 5, M = 6,
#>     N = 7, Q = 8, U = 9, V = 10, X = 11, Z = 12
#>   )
#>   m[x] |> unname()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## code2month_oldcode
#> function(x) {
#>   m <- c(
#>     JAN = 1, FEV = 2, MAR = 3, ABR = 4, MAI = 5, JUN = 6,
#>     JUL = 7, AGO = 8, SET = 9, OUT = 10, NOV = 11, DEZ = 12
#>   )
#>   m[x] |> unname()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cols_number
#> ACC BRP DCO DIC DIM DOC DOL EUC EUR INP JPY LIB PTX SDE SLP APR  DP PRE TFP  TP 
#>   2   2   2   2   2   2   2   2   2   2   2   2   2   2   2   3   3   3   3   3 
#>  TR 
#>   3 
#> --- 
#>  
#> ## company_cash_dividends_download
#> function(., dest, ...) {
#>   if (!check_parameters(..., arg_name = "trading_name")) {
#>     return(FALSE)
#>   }
#>   args <- list(...)
#>   trading_name <- str_replace_all(args$trading_name, "[^A-Z0-9 ]+", "")
#>   url_encoded_download(., dest,
#>     tradingName = trading_name, language = "pt-br",
#>     pageNumber = 1, pageSize = 9999
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## company_cash_dividends_reader
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   if (length(jason$results) == 0)  {
#>     return(NULL)
#>   }
#>   df <- as.data.frame(jason[["results"]])
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## company_details_download
#> function(., dest, ...) {
#>   if (!check_parameters(..., arg_name = "code_cvm")) {
#>     return(FALSE)
#>   }
#>   args <- list(...)
#>   url_encoded_download(., dest,
#>     codeCVM = args$code_cvm, language = "pt-br"
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## company_details_reader
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   l <- list()
#>   for (part_name in names(.$parts)) {
#>     part <- .$parts[[part_name]]
#>     if (part_name == "Info") {
#>       df <- tibble(
#>         issuingCompany = ck_if_null(jason$issuingCompany),
#>         companyName = ck_if_null(jason$companyName),
#>         tradingName = ck_if_null(jason$tradingName),
#>         cnpj = ck_if_null(jason$cnpj),
#>         industryClassification = ck_if_null(jason$industryClassification),
#>         industryClassificationEng = ck_if_null(jason$industryClassificationEng),
#>         activity = ck_if_null(jason$activity),
#>         website = ck_if_null(jason$website),
#>         hasQuotation = ck_if_null(jason$hasQuotation),
#>         status = ck_if_null(jason$status),
#>         marketIndicator = ck_if_null(jason$marketIndicator),
#>         market = ck_if_null(jason$market),
#>         institutionCommon = ck_if_null(jason$institutionCommon),
#>         institutionPreferred = ck_if_null(jason$institutionPreferred),
#>         code = ck_if_null(jason$code),
#>         codeCVM = ck_if_null(jason$codeCVM),
#>         lastDate = ck_if_null(jason$lastDate),
#>         hasEmissions = ck_if_null(jason$hasEmissions),
#>         hasBDR = ck_if_null(jason$hasBDR),
#>         typeBDR = ck_if_null(jason$typeBDR),
#>         describleCategoryBVMF = ck_if_null(jason$describleCategoryBVMF),
#>       )
#>     } else {
#>       df <- as.data.frame(jason[[part$name]])
#>     }
#>     if (length(df) == 0) {
#>       next
#>     }
#>     colnames(df) <- part$colnames
#>     l[[part_name]] <- if (parse_fields) {
#>       parse_columns(df, part$colnames, part$handlers, .$.parser())
#>     } else {
#>       df
#>     }
#>   }
#>   class(l) <- "parts"
#>   l
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## company_listed_supplement_download
#> function(., dest, ...) {
#>   if (!check_parameters(..., arg_name = "company_name")) {
#>     return(FALSE)
#>   }
#>   args <- list(...)
#>   url_encoded_download(., dest,
#>     issuingCompany = args$company_name, language = "pt-br"
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## company_listed_supplement_reader
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   l <- list()
#>   for (part_name in names(.$parts)) {
#>     part <- .$parts[[part_name]]
#>     if (part_name == "Info") {
#>       df <- tibble(
#>         stockCapital = ck_if_null(jason$stockCapital),
#>         segment = ck_if_null(jason$segment),
#>         quotedPerSharSince = ck_if_null(jason$quotedPerSharSince),
#>         commonSharesForm = ck_if_null(jason$commonSharesForm),
#>         preferredSharesForm = ck_if_null(jason$preferredSharesForm),
#>         hasCommom = ck_if_null(jason$hasCommom),
#>         hasPreferred = ck_if_null(jason$hasPreferred),
#>         code = ck_if_null(jason$code),
#>         codeCVM = ck_if_null(jason$codeCVM),
#>         totalNumberShares = ck_if_null(jason$totalNumberShares),
#>         numberCommonShares = ck_if_null(jason$numberCommonShares),
#>         numberPreferredShares = ck_if_null(jason$numberPreferredShares),
#>         roundLot = ck_if_null(jason$roundLot),
#>         tradingName = ck_if_null(jason$tradingName),
#>       )
#>     } else {
#>       df <- as.data.frame(jason[[part$name]][[1]])
#>     }
#>     if (length(df) == 0) {
#>       next
#>     }
#>     colnames(df) <- part$colnames
#>     l[[part_name]] <- if (parse_fields) {
#>       parse_columns(df, part$colnames, part$handlers, .$.parser())
#>     } else {
#>       df
#>     }
#>   }
#>   class(l) <- "parts"
#>   l
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## composite
#> function(...) {
#>   fs <- list(...)
#>   function(...) Reduce(function(x, f) f(x), fs, ...)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## content
#> function (x, as = NULL, type = NULL, encoding = NULL, ...) 
#> {
#>     stopifnot(is.response(x))
#>     type <- type %||% x$headers[["Content-Type"]] %||% mime::guess_type(x$url, 
#>         empty = "application/octet-stream")
#>     as <- as %||% parseability(type)
#>     as <- match.arg(as, c("raw", "text", "parsed"))
#>     if (is.path(x$content)) {
#>         raw <- readBin(x$content, "raw", file.info(x$content)$size)
#>     }
#>     else {
#>         raw <- x$content
#>     }
#>     switch(as, raw = raw, text = parse_text(raw, type, encoding), 
#>         parsed = parse_auto(raw, type, encoding, ...))
#> }
#> <bytecode: 0x55b97305ecb8>
#> <environment: namespace:httr>
#> --- 
#>  
#> ## convert_to
#> function(filename, template = NULL, parse_fields = TRUE,
#>                        format = "csv", destdir = NULL) {
#>   template <- .retrieve_template(filename, template)
#>   fname <- Filename(name = filename)
#>   df <- template$read_file(filename, parse_fields)
#>   new_filename <- fname$changeExt(paste0(".", format), destdir)
#>   if (format == "csv") {
#>     write.table(df,
#>       file = new_filename, sep = ",", dec = ".",
#>       row.names = FALSE
#>     )
#>   } else if (format == "json") {
#>     writeLines(toJSON(df), new_filename)
#>   }
#>   new_filename
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## copy_file_to_temp
#> function(f_name) {
#>   folder <- tempdir()
#>   f_dest <- file.path(folder, basename(f_name))
#>   if (file.copy(f_name, f_dest, overwrite = TRUE)) {
#>     f_dest
#>   } else {
#>     stop("Can't copy file to tempdir")
#>   }
#> }
#> <environment: package:rb3>
#> --- 
#>  
#> ## cotahist_bdrs_get
#> function(x) {
#>   filter_equity_data(x, 10, "BDR") |> format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_equity_get
#> function(x) {
#>   filter_equity_data(x, 10, c("UNT", "CDA", "ACN")) |> format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_equity_options_get
#> function(x) {
#>   filter_equity_data(x, c(70, 80), c("ACN", "UNT", "CDA")) |> format_options()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_equity_options_superset
#> function(ch, yc) {
#>   eqs <- filter_equity_data(ch, 10, c("UNT", "CDA", "ACN")) |>
#>     format_equity(TRUE)
#>   eqs_opts <- filter_equity_data(ch, c(70, 80), c("UNT", "CDA", "ACN")) |>
#>     format_options(TRUE)
#>   inner_join(eqs_opts, eqs, by = "cod_isin", suffix = c("", ".underlying")) |>
#>     select(-c(.data$refdate.underlying, .data$cod_isin)) |>
#>     mutate(
#>       fixing_maturity_date = following(.data$maturity_date, "Brazil/ANBIMA")
#>     ) |>
#>     inner_join(yc |> select(.data$refdate, .data$forward_date, .data$r_252),
#>       by = c("refdate", "fixing_maturity_date" = "forward_date")
#>     )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_etfs_get
#> function(x) {
#>   filter_equity_data(x, 10, "CTF") |>
#>     filter(.data$cod_bdi == 14, str_starts(.data$especificacao, "CI")) |>
#>     format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_fiagros_get
#> function(x) {
#>   filter_equity_data(x, 10, "CTF") |>
#>     filter(.data$cod_bdi == 13) |>
#>     format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_fidcs_get
#> function(x) {
#>   filter_equity_data(x, 10, "CTF") |>
#>     filter(
#>       .data$cod_bdi == 14, str_starts(.data$especificacao, "FIDC")
#>     ) |>
#>     format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_fiis_get
#> function(x) {
#>   filter_equity_data(x, 10, "CTF") |>
#>     filter(.data$cod_bdi %in% c(5, 12)) |>
#>     format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_funds_options_get
#> function(x) {
#>   filter_equity_data(x, c(70, 80), "CTF") |> format_options()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_get
#> function(refdate,
#>                          type = c("yearly", "monthly", "daily"),
#>                          cache_folder = cachedir(),
#>                          do_cache = TRUE) {
#>   type <- match.arg(type)
#>   tpl <- switch(type,
#>     yearly = "COTAHIST_YEARLY",
#>     monthly = "COTAHIST_MONTHLY",
#>     daily = "COTAHIST_DAILY"
#>   )
#>   refdate <- as.Date(refdate)
#>   fname <- download_marketdata(tpl, cache_folder, do_cache, refdate = refdate)
#>   if (!is.null(fname)) {
#>     read_marketdata(fname, tpl)
#>   } else {
#>     alert("danger", "Failed {tpl} download for reference date {refdate}",
#>       tpl = tpl, refdate = refdate
#>     )
#>     NULL
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_get_symbols
#> function(x, symbols) {
#>   x[["HistoricalPrices"]] |>
#>     filter(.data$cod_negociacao %in% symbols) |>
#>     format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_index_options_get
#> function(x) {
#>   filter_equity_data(x, c(70, 80), "IND") |> format_options()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_indexes_get
#> function(x) {
#>   filter_equity_data(x, 10, "IND") |> format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_options_by_symbol_superset
#> function(symbol, ch, yc) {
#>   eqs <- ch[["HistoricalPrices"]] |>
#>     filter(.data$cod_negociacao == symbol) |>
#>     format_equity(TRUE)
#>   eqs_opts <- ch[["HistoricalPrices"]] |>
#>     filter(.data$tipo_mercado %in% c(70, 80)) |>
#>     format_options(TRUE) |>
#>     filter(.data$cod_isin == eqs$cod_isin[1])
#>   inner_join(eqs_opts, eqs,
#>     by = c("refdate", "cod_isin"),
#>     suffix = c("", ".underlying")
#>   ) |>
#>     select(-c(.data$cod_isin)) |>
#>     mutate(
#>       fixing_maturity_date = following(.data$maturity_date, "Brazil/ANBIMA")
#>     ) |>
#>     inner_join(yc |> select(.data$refdate, .data$forward_date, .data$r_252),
#>       by = c("refdate", "fixing_maturity_date" = "forward_date")
#>     )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## cotahist_units_get
#> function(x) {
#>   filter_equity_data(x, 10, c("UNT", "CDA")) |> format_equity()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## csv_read_file
#> function(., filename, parse_fields = TRUE) {
#>   skip <- try(.$skip, TRUE)
#>   skip <- if (is(skip, "try-error")) 0 else skip
#>   comment <- try(.$comment, TRUE)
#>   comment <- if (is(comment, "try-error")) "#" else comment
#>   df <- read.table(filename,
#>     col.names = .$colnames, sep = .$separator, skip = skip,
#>     comment.char = comment, as.is = TRUE, stringsAsFactors = FALSE
#>   )
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## curve_download
#> function(., dest, ...) {
#>   params <- list(...)
#>   if (is.null(params$refdate)) {
#>     msg <- "refdate argument not provided - download can't be done"
#>     alert("danger", msg)
#>     return(FALSE)
#>   }
#>   curve_name <- if (is.null(params$curve_name)) {
#>     "PRE"
#>   } else {
#>     params$curve_name
#>   }
#>   url <- parse_url(.$downloader$url)
#>   url$query <- list(
#>     Data = format(as.Date(params$refdate), "%d/%m/%Y"),
#>     Data1 = format(as.Date(params$refdate), "%Y%m%d"),
#>     slcTaxa = curve_name
#>   )
#>   res <- GET(url)
#>   if (status_code(res) != 200) {
#>     return(FALSE)
#>   }
#>   enc <- if (is.null(.$downloader$encoding)) "utf8" else .$downloader$encoding
#>   save_resource(res, enc, dest)
#>   TRUE
#> }
#> <bytecode: 0x55b97bfd5910>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## curve_read
#> function(., filename, parse_fields = TRUE) {
#>   text <- read_file(filename)
#> 
#>   char_vec <- read_html(text) |>
#>     html_nodes("td") |>
#>     html_text()
#> 
#>   if (length(char_vec) == 0) {
#>     return(NULL)
#>   }
#> 
#>   ctx <- str_match(text, "\"([A-Z]+)\"\\s+selected")
#>   curve_name <- ctx[1, 2]
#> 
#>   mtx <- str_match(text, "Atualizado em: (\\d{2}/\\d{2}/\\d{4})")
#>   refdate <- mtx[1, 2] |> as.Date("%d/%m/%Y")
#> 
#>   if (cols_number[curve_name] == 2) {
#>     idx1 <- seq(1, length(char_vec), by = 2)
#>     idx2 <- seq(2, length(char_vec), by = 2)
#> 
#>     cur_days <- char_vec[idx1]
#>     col1 <- char_vec[idx2]
#>     col2 <- NA
#>   } else {
#>     idx1 <- seq(1, length(char_vec), by = 3)
#>     idx2 <- seq(2, length(char_vec), by = 3)
#>     idx3 <- seq(3, length(char_vec), by = 3)
#> 
#>     cur_days <- char_vec[idx1]
#>     col1 <- char_vec[idx2]
#>     col2 <- char_vec[idx3]
#>   }
#> 
#>   df <- tibble(
#>     refdate,
#>     cur_days,
#>     col1,
#>     col2
#>   )
#> 
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <bytecode: 0x55b970482840>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## datetime_download
#> function(., dest, ...) {
#>   params <- list(...)
#>   if (is.null(params$refdate)) {
#>     msg <- "refdate argument not provided - download can't be done"
#>     alert("danger", msg)
#>     return(FALSE)
#>   }
#>   url <- strftime(params$refdate, .$downloader$url)
#>   enc <- if (is.null(.$downloader$encoding)) "utf8" else .$downloader$encoding
#>   just_download_data(url, enc, dest)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## digest
#> function (object, algo = c("md5", "sha1", "crc32", "sha256", 
#>     "sha512", "xxhash32", "xxhash64", "murmur32", "spookyhash", 
#>     "blake3"), serialize = TRUE, file = FALSE, length = Inf, 
#>     skip = "auto", ascii = FALSE, raw = FALSE, seed = 0, errormode = c("stop", 
#>         "warn", "silent"), serializeVersion = .getSerializeVersion()) 
#> {
#>     algo <- match.arg(algo, c("md5", "sha1", "crc32", "sha256", 
#>         "sha512", "xxhash32", "xxhash64", "murmur32", "spookyhash", 
#>         "blake3"))
#>     errormode <- match.arg(errormode, c("stop", "warn", "silent"))
#>     if (is.infinite(length)) {
#>         length <- -1
#>     }
#>     if (is.character(file) && missing(object)) {
#>         object <- file
#>         file <- TRUE
#>     }
#>     is_streaming_algo <- algo == "spookyhash"
#>     if (is_streaming_algo && !serialize) {
#>         .errorhandler(paste0(algo, " algorithm is not available without serialization."), 
#>             mode = errormode)
#>     }
#>     if (serialize && !file) {
#>         if (!is_streaming_algo) {
#>             object <- if (.hasNoSharing()) 
#>                 serialize(object, connection = NULL, ascii = ascii, 
#>                   nosharing = TRUE, version = serializeVersion)
#>             else serialize(object, connection = NULL, ascii = ascii, 
#>                 version = serializeVersion)
#>         }
#>         if (is.character(skip) && skip == "auto") 
#>             skip <- set_skip(object, ascii)
#>     }
#>     else if (!is.character(object) && !inherits(object, "raw") && 
#>         !is_streaming_algo) {
#>         return(.errorhandler(paste("Argument object must be of type character", 
#>             "or raw vector if serialize is FALSE"), mode = errormode))
#>     }
#>     if (file && !is.character(object)) 
#>         return(.errorhandler("file=TRUE can only be used with a character object", 
#>             mode = errormode))
#>     if (file && is_streaming_algo) 
#>         return(.errorhandler(paste0(algo, " algorithm can not be used with files."), 
#>             mode = errormode))
#>     algoint <- algo_int(algo)
#>     if (file) {
#>         algoint <- algoint + 100
#>         object <- path.expand(object)
#>         if (.isWindows()) 
#>             object <- enc2utf8(object)
#>         check_file(object, errormode)
#>     }
#>     if (is.character(skip)) 
#>         skip <- 0
#>     if (!is_streaming_algo) {
#>         val <- .Call(digest_impl, object, as.integer(algoint), 
#>             as.integer(length), as.integer(skip), as.integer(raw), 
#>             as.integer(seed))
#>     }
#>     else if (algo == "spookyhash") {
#>         val <- paste(.Call(spookydigest_impl, object, skip, 0, 
#>             0, serializeVersion, NULL), collapse = "")
#>     }
#>     if ((algoint == 3 || algoint == 103) && .getCRC32PreferOldOutput()) {
#>         val <- sub("^0+", "", val)
#>     }
#>     return(val)
#> }
#> <bytecode: 0x55b973f80fa8>
#> <environment: namespace:digest>
#> --- 
#>  
#> ## display_template
#> function() {
#>   classes_ <- MarketData$show_templates()[["Class Name"]]
#>   ui <- miniUI::miniPage(
#>     miniUI::miniTitleBar("rb3 View Template"),
#>     miniUI::miniContentPanel(
#>       shiny::selectInput("templateClass",
#>         label = shiny::h3("Template Classes"),
#>         choices = classes_,
#>         selected = 1
#>       ),
#>       shiny::hr(),
#>       shiny::uiOutput("templateOutput")
#>     )
#>   )
#> 
#> 
#>   server <- function(input, output, session) {
#>     output$templateOutput <- shiny::renderUI({
#>       tpl_ <- MarketData$retrieve_template(input$templateClass)
#> 
#>       elm <- list(
#>         shiny::tags$p("Template ID: ", tpl_$id),
#>         shiny::tags$p("Filename: ", tpl_$filename),
#>         shiny::tags$p("File type: ", tpl_$filetype)
#>       )
#> 
#>       if (is(tpl_$fields, "fields")) {
#>         elm[[length(elm) + 1]] <- shiny::HTML(
#>           print(xtable::xtable(as.data.frame(tpl_$fields)),
#>             type = "html", print.results = FALSE,
#>             html.table.attributes =
#>               'class="data table table-bordered table-condensed"'
#>           )
#>         )
#>       } else {
#>         parts_names <- names(tpl_$parts)
#>         ix <- 0
#>         for (nx in parts_names) {
#>           ix <- ix + 1
#>           elm[[length(elm) + 1]] <- shiny::tags$p(
#>             sprintf("Part %d: %s\n", ix, nx)
#>           )
#>           elm[[length(elm) + 1]] <- shiny::HTML(
#>             print(xtable::xtable(as.data.frame(tpl_$parts[[nx]]$fields)),
#>               type = "html", print.results = FALSE,
#>               html.table.attributes =
#>                 'class="data table table-bordered table-condensed"'
#>             )
#>           )
#>         }
#>       }
#>       do.call(shiny::tags$div, elm)
#>     })
#>   }
#> 
#>   app <- shiny::shinyApp(ui = ui, server = server)
#>   viewer <- shiny::dialogViewer("rb3 Show Templates",
#>     width = 1200,
#>     height = 900
#>   )
#> 
#>   shiny::runGadget(app, viewer = viewer, stopOnCancel = TRUE)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## download_marketdata
#> function(template,
#>                                 cache_folder = cachedir(),
#>                                 do_cache = TRUE, ...) {
#>   template <- .retrieve_template(NULL, template)
#>   x <- list(...)
#>   code_ <- digest(x)
#> 
#>   cache_folder <- file.path(cache_folder, template$id)
#>   if (!dir.exists(cache_folder)) {
#>     dir.create(cache_folder, recursive = TRUE)
#>   }
#> 
#>   dest <- file.path(
#>     cache_folder,
#>     str_glue("{c}.{template$downloader$format}", c = code_)
#>   )
#> 
#>   if (file.exists(dest) && do_cache) {
#>     fname <- unzip_recursive(dest)
#>     return(fname)
#>   }
#> 
#>   if (template$download_marketdata(dest, ...)) {
#>     fname <- unzip_recursive(dest)
#>     return(fname)
#>   } else {
#>     return(NULL)
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## field
#> function(name, description, ...) {
#>   if (missing(description)) {
#>     attr(name, "description") <- ""
#>     parms <- list(...)
#>   } else {
#>     if (is(description, "character")) {
#>       attr(name, "description") <- description
#>       parms <- list(...)
#>     } else {
#>       attr(name, "description") <- ""
#>       parms <- list(description, ...)
#>       warning(
#>         "description invalid type: ",
#>         paste(class(description), collapse = ", ")
#>       )
#>     }
#>   }
#> 
#>   classes <- lapply(parms, function(x) {
#>     if (is(x, "width")) {
#>       "width"
#>     } else if (is(x, "handler")) {
#>       "handler"
#>     } else {
#>       NULL
#>     }
#>   })
#> 
#>   if (any(classes == "width")) {
#>     attr(name, "width") <- parms[[which(classes == "width")[1]]]
#>   } else {
#>     attr(name, "width") <- 0
#>   }
#> 
#>   if (any(classes == "handler")) {
#>     attr(name, "handler") <- parms[[which(classes == "handler")[1]]]
#>   } else {
#>     attr(name, "handler") <- pass_thru_handler()
#>   }
#> 
#>   class(name) <- "field"
#>   name
#> }
#> <bytecode: 0x55b97c2f3028>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fields
#> function(...) {
#>   that <- list(...)
#>   class(that) <- "fields"
#>   that
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fields_description
#> function(fields) {
#>   map_chr(fields, function(x) attr(x, "description"))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fields_handlers
#> function(fields) {
#>   handlers <- lapply(fields, function(x) attr(x, "handler"))
#>   names(handlers) <- fields_names(fields)
#>   handlers
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fields_names
#> function(fields) {
#>   map_chr(fields, function(x) as.character(x))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fields_widths
#> function(fields) {
#>   map_int(fields, function(x) as.integer(attr(x, "width")))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## Filename
#> new("refObjectGenerator", .Data = function (...) 
#> new("Filename", ...), generator = new("refGeneratorSlot", .xData = <environment>), 
#>     className = "Filename", package = "rb3")
#> <environment: namespace:rb3>
#> attr(,"className")
#> [1] "Filename"
#> attr(,"className")attr(,"package")
#> [1] "rb3"
#> attr(,"package")
#> [1] "rb3"
#> attr(,"generator")
#> Reference class object of class "refGeneratorSlot"
#> Field "def":
#> Reference Class "Filename":
#> 
#> Class fields:
#>                 
#> Name:       name
#> Class: character
#> 
#> Class Methods: 
#>      "exists", "getBasename", "getDirname", "changeExt", "getFilenameSansExt", 
#>      "getExt", "initialize", "field", "trace", "getRefClass", "initFields", 
#>      "copy", "callSuper", ".objectPackage", "export", "untrace", "getClass", 
#>      "show", "usingMethods", ".objectParent", "import"
#> 
#> Reference Superclasses: 
#>      "envRefClass"
#> 
#> Field "className":
#> [1] "Filename"
#> attr(,"class")
#> [1] "refObjectGenerator"
#> attr(,"class")attr(,"package")
#> [1] "methods"
#> --- 
#>  
#> ## filter
#> function (.data, ..., .preserve = FALSE) 
#> {
#>     UseMethod("filter")
#> }
#> <bytecode: 0x55b96afc23a8>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## filter_equity_data
#> function(x, instrument_market, security_category) {
#>   x[["HistoricalPrices"]] |>
#>     filter(
#>       .data$tipo_mercado %in% instrument_market,
#>       str_sub(.data$cod_isin, 7, 9) %in% security_category
#>     )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## flatten_names
#> function(nx) {
#>   for (ix in seq_along(nx)) {
#>     if (nx[ix] != "") {
#>       last_name <- nx[ix]
#>     }
#>     nx[ix] <- last_name
#>   }
#>   x <- nx |> str_match("^...")
#>   as.vector(x)
#> }
#> <bytecode: 0x55b978b88918>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## following
#> function (dates, cal) 
#> UseMethod("following")
#> <bytecode: 0x55b96bd3bfe8>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## format_equity
#> function(df, with_isin = FALSE) {
#>   df[["refdate"]] <- df[["data_referencia"]]
#>   df[["symbol"]] <- df[["cod_negociacao"]]
#>   df[["open"]] <- df[["preco_abertura"]]
#>   df[["high"]] <- df[["preco_max"]]
#>   df[["low"]] <- df[["preco_min"]]
#>   df[["close"]] <- df[["preco_ult"]]
#>   df[["average"]] <- df[["preco_med"]]
#>   df[["best_bid"]] <- df[["preco_melhor_oferta_compra"]]
#>   df[["best_ask"]] <- df[["preco_melhor_oferta_venda"]]
#>   df[["volume"]] <- df[["volume_titulos_negociados"]]
#>   df[["traded_contracts"]] <- df[["qtd_titulos_negociados"]]
#>   df[["transactions_quantity"]] <- df[["qtd_negocios"]]
#>   df[["distribution_id"]] <- df[["num_dist"]]
#>   isin <- if (with_isin) "cod_isin" else NULL
#>   cols <- c(
#>     "refdate", "symbol", "open", "high", "low", "close", "average",
#>     "best_bid", "best_ask", "volume", "traded_contracts",
#>     "transactions_quantity", "distribution_id", isin
#>   )
#>   df[, cols]
#> }
#> <bytecode: 0x55b97321bea8>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## format_options
#> function(df, with_isin = FALSE) {
#>   df[["refdate"]] <- df[["data_referencia"]]
#>   df[["symbol"]] <- df[["cod_negociacao"]]
#>   df[["open"]] <- df[["preco_abertura"]]
#>   df[["high"]] <- df[["preco_max"]]
#>   df[["low"]] <- df[["preco_min"]]
#>   df[["close"]] <- df[["preco_ult"]]
#>   df[["average"]] <- df[["preco_med"]]
#>   df[["type"]] <- factor(df[["tipo_mercado"]], c(70, 80), c("Call", "Put"))
#>   df[["strike"]] <- df[["preco_exercicio"]]
#>   df[["maturity_date"]] <- df[["data_vencimento"]]
#>   df[["volume"]] <- df[["volume_titulos_negociados"]]
#>   df[["traded_contracts"]] <- df[["qtd_titulos_negociados"]]
#>   df[["transactions_quantity"]] <- df[["qtd_negocios"]]
#>   df[["distribution_id"]] <- df[["num_dist"]]
#>   isin <- if (with_isin) "cod_isin" else NULL
#>   cols <- c(
#>     "refdate", "symbol", "type", "strike", "maturity_date",
#>     "open", "high", "low", "close", "average", "volume", "traded_contracts",
#>     "transactions_quantity", "distribution_id", isin
#>   )
#>   df[, cols]
#> }
#> <bytecode: 0x55b97ca5c2d0>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fromJSON
#> function (txt, simplifyVector = TRUE, simplifyDataFrame = simplifyVector, 
#>     simplifyMatrix = simplifyVector, flatten = FALSE, ...) 
#> {
#>     if (!is.character(txt) && !inherits(txt, "connection")) {
#>         stop("Argument 'txt' must be a JSON string, URL or file.")
#>     }
#>     if (is.character(txt) && length(txt) == 1 && nchar(txt, type = "bytes") < 
#>         2084 && !validate(txt)) {
#>         if (grepl("^https?://", txt, useBytes = TRUE)) {
#>             txt <- if (R.version$major < 4) {
#>                 base::url(txt)
#>             }
#>             else {
#>                 base::url(txt, headers = c(Accept = "application/json, text/*, */*"))
#>             }
#>         }
#>         else if (file.exists(txt)) {
#>             txt <- file(txt)
#>         }
#>     }
#>     parse_and_simplify(txt = txt, simplifyVector = simplifyVector, 
#>         simplifyDataFrame = simplifyDataFrame, simplifyMatrix = simplifyMatrix, 
#>         flatten = flatten, ...)
#> }
#> <bytecode: 0x55b97107d208>
#> <environment: namespace:jsonlite>
#> --- 
#>  
#> ## futures_get
#> function(refdate = Sys.Date(),
#>                         cache_folder = cachedir(),
#>                         do_cache = TRUE) {
#>   single_futures_get(1, as.Date(refdate), cache_folder, do_cache)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## futures_mget
#> function(first_date = Sys.Date() - 5,
#>                          last_date = Sys.Date(),
#>                          by = 1,
#>                          cache_folder = cachedir(),
#>                          do_cache = TRUE) {
#>   first_date <- as.Date(first_date)
#>   last_date <- as.Date(last_date)
#>   date_vec <- bizseq(first_date, last_date, "Brazil/BMF")
#>   date_vec <- date_vec[seq(1, length(date_vec), by = by)]
#>   df <- bind_rows(
#>     log_map_process_along(date_vec, single_futures_get,
#>       "Fetching data points",
#>       date_vec = date_vec,
#>       cache_folder = cache_folder,
#>       do_cache = do_cache
#>     )
#>   )
#>   return(df)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## fwf_read_file
#> function(., filename, parse_fields = TRUE) {
#>   df <- read_fwf(filename, .$widths, colnames = .$colnames)
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## GET
#> function (url = NULL, config = list(), ..., handle = NULL) 
#> {
#>     hu <- handle_url(handle, url, ...)
#>     req <- request_build("GET", hu$url, as.request(config), ...)
#>     request_perform(req, hu$handle$handle)
#> }
#> <bytecode: 0x55b97320b990>
#> <environment: namespace:httr>
#> --- 
#>  
#> ## get_single_indexreport
#> function(idx_date,
#>                                    date_vec,
#>                                    cache_folder,
#>                                    do_cache) {
#>   df <- get_single_marketdata(
#>     "IndexReport", idx_date, date_vec, cache_folder, do_cache
#>   )
#>   if (!is.null(df)) {
#>     cols <- c(
#>       "refdate", "symbol", "open", "high", "low", "close", "average",
#>       "oscillation"
#>     )
#>     df[, cols]
#>   } else {
#>     NULL
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## get_single_marketdata
#> function(template,
#>                                   idx_date,
#>                                   date_vec,
#>                                   cache_folder,
#>                                   do_cache, ...) {
#>   refdate <- date_vec[idx_date]
#>   fname <- download_marketdata(template, cache_folder, do_cache,
#>     refdate = refdate, ...
#>   )
#>   if (!is.null(fname)) {
#>     read_marketdata(fname, template, TRUE, do_cache)
#>   } else {
#>     alert("danger", "Error: no data found for date {refdate}",
#>       refdate = refdate
#>     )
#>     return(NULL)
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## get_single_yc
#> function(idx_date,
#>                           date_vec,
#>                           cache_folder,
#>                           do_cache) {
#>   tpl_name <- "TaxasReferenciais"
#>   tpl <- .retrieve_template(NULL, tpl_name)
#>   refdate <- date_vec[idx_date]
#>   fname <- download_marketdata(tpl_name, cache_folder, do_cache,
#>     refdate = refdate,
#>     curve_name = "PRE"
#>   )
#>   if (!is.null(fname)) {
#>     df <- read_marketdata(fname, tpl_name, TRUE, do_cache)
#>     if (!is.null(df)) {
#>       tibble(
#>         refdate = df$refdate,
#>         cur_days = df$cur_days,
#>         biz_days = bizdayse(refdate, .data$cur_days, tpl$calendar),
#>         forward_date = add.bizdays(
#>           refdate,
#>           .data$biz_days, tpl$calendar
#>         ),
#>         r_252 = df$col1 / 100,
#>         r_360 = df$col2 / 100
#>       )
#>     } else {
#>       NULL
#>     }
#>   } else {
#>     alert("danger", "Error: no data found for date {refdate}",
#>       refdate = refdate
#>     )
#>     return(NULL)
#>   }
#> }
#> <bytecode: 0x55b9739a9318>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## get_single_yc_ipca
#> function(idx_date,
#>                                date_vec,
#>                                cache_folder,
#>                                do_cache) {
#>   tpl_name <- "TaxasReferenciais"
#>   tpl <- .retrieve_template(NULL, tpl_name)
#>   refdate <- date_vec[idx_date]
#>   fname <- download_marketdata(tpl_name, cache_folder, do_cache,
#>     refdate = refdate,
#>     curve_name = "DIC"
#>   )
#>   if (!is.null(fname)) {
#>     df <- read_marketdata(fname, tpl_name, TRUE, do_cache)
#>     if (!is.null(df)) {
#>       tibble(
#>         refdate = df$refdate,
#>         cur_days = df$cur_days,
#>         biz_days = bizdayse(refdate, .data$cur_days, tpl$calendar),
#>         forward_date = add.bizdays(
#>           refdate,
#>           .data$biz_days, tpl$calendar
#>         ),
#>         r_252 = df$col1 / 100
#>       )
#>     } else {
#>       NULL
#>     }
#>   } else {
#>     alert("danger", "Error: no data found for date {refdate}",
#>       refdate = refdate
#>     )
#>     return(NULL)
#>   }
#> }
#> <bytecode: 0x55b97734f928>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## get_single_yc_usd
#> function(idx_date,
#>                               date_vec,
#>                               cache_folder,
#>                               do_cache) {
#>   tpl_name <- "TaxasReferenciais"
#>   tpl <- .retrieve_template(NULL, tpl_name)
#>   refdate <- date_vec[idx_date]
#>   fname <- download_marketdata(tpl_name, cache_folder, do_cache,
#>     refdate = refdate,
#>     curve_name = "DOC"
#>   )
#>   if (!is.null(fname)) {
#>     df <- read_marketdata(fname, tpl_name, TRUE, do_cache)
#>     if (!is.null(df)) {
#>       tibble(
#>         refdate = df$refdate,
#>         cur_days = df$cur_days,
#>         biz_days = bizdayse(refdate, .data$cur_days, tpl$calendar),
#>         forward_date = add.bizdays(
#>           refdate,
#>           .data$biz_days, tpl$calendar
#>         ),
#>         r_360 = df$col1 / 100
#>       )
#>     } else {
#>       NULL
#>     }
#>   } else {
#>     alert("danger", "Error: no data found for date {refdate}",
#>       refdate = refdate
#>     )
#>     return(NULL)
#>   }
#> }
#> <bytecode: 0x55b971c41518>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## getdate
#> function (expr, ref, cal = bizdays.options$get("default.calendar")) 
#> {
#>     cal <- check_calendar(cal)
#>     ref <- ref(ref)
#>     tok <- strsplit(expr, "\\s+")[[1]]
#>     if (length(tok) != 2) {
#>         stop("Invalid expr", expr)
#>     }
#>     n <- getnth_(tok[1])
#>     if (tok[2] == "day") {
#>         getnthday(ref, n, FALSE, cal)
#>     }
#>     else if (tok[2] == "bizday") {
#>         getnthday(ref, n, TRUE, cal)
#>     }
#>     else if (tok[2] %in% WEEKDAYS) {
#>         wday <- which(tok[2] == WEEKDAYS)
#>         getnthweekday(ref, n, wday, cal)
#>     }
#>     else {
#>         stop("Invalid expr", expr)
#>     }
#> }
#> <bytecode: 0x55b9796a4460>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## getFromNamespace
#> function (x, ns, pos = -1, envir = as.environment(pos)) 
#> {
#>     if (missing(ns)) {
#>         nm <- attr(envir, "name", exact = TRUE)
#>         if (is.null(nm) || !startsWith(nm, "package:")) 
#>             stop("environment specified is not a package")
#>         ns <- asNamespace(substring(nm, 9L))
#>     }
#>     else ns <- asNamespace(ns)
#>     get(x, envir = ns, inherits = FALSE)
#> }
#> <bytecode: 0x55b968634928>
#> <environment: namespace:utils>
#> --- 
#>  
#> ## getNodeSet
#> function (doc, path, namespaces = xmlNamespaceDefinitions(doc, 
#>     simplify = TRUE), fun = NULL, sessionEncoding = CE_NATIVE, 
#>     addFinalizer = NA, ...) 
#> {
#>     xpathApply(doc, path, fun, ..., namespaces = namespaces, 
#>         sessionEncoding = sessionEncoding, addFinalizer = addFinalizer)
#> }
#> <bytecode: 0x55b97941dc38>
#> <environment: namespace:XML>
#> --- 
#>  
#> ## hasName
#> function (x, name) 
#> match(name, names(x), nomatch = 0L) > 0L
#> <bytecode: 0x55b97c3db2d0>
#> <environment: namespace:utils>
#> --- 
#>  
#> ## headers
#> function (x) 
#> UseMethod("headers")
#> <bytecode: 0x55b96c793740>
#> <environment: namespace:httr>
#> --- 
#>  
#> ## html_element
#> function (x, css, xpath) 
#> {
#>     UseMethod("html_element")
#> }
#> <bytecode: 0x55b96c27ddd0>
#> <environment: namespace:rvest>
#> --- 
#>  
#> ## html_nodes
#> function (...) 
#> {
#>     html_elements(...)
#> }
#> <bytecode: 0x55b97635a238>
#> <environment: namespace:rvest>
#> --- 
#>  
#> ## html_table
#> function (x, header = NA, trim = TRUE, fill = deprecated(), dec = ".", 
#>     na.strings = "NA", convert = TRUE) 
#> {
#>     UseMethod("html_table")
#> }
#> <bytecode: 0x55b96c2222c8>
#> <environment: namespace:rvest>
#> --- 
#>  
#> ## html_text
#> function (x, trim = FALSE) 
#> {
#>     xml_text(x, trim = trim)
#> }
#> <bytecode: 0x55b9763597b8>
#> <environment: namespace:rvest>
#> --- 
#>  
#> ## ibovespa_index_get
#> function(first_date, last_date = as.Date("1997-12-31")) {
#>   f <- system.file("extdata/IBOV.rds", package = "rb3")
#>   read_rds(f) |> filter(.data$refdate >= first_date, .data$refdate <= last_date)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## idi_get
#> function() {
#>   dx <- query_cdi()
#>   tibble(
#>     refdate = dx$dataIndice,
#>     IDI = dx$indice
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## index_by_segment_get
#> function(index_name,
#>                                  cache_folder = cachedir(),
#>                                  do_cache = TRUE) {
#>   f <- download_marketdata("GetPortfolioDay",
#>     cache_folder = cache_folder,
#>     do_cache = do_cache,
#>     index_name = index_name
#>   )
#>   pp <- read_marketdata(f, "GetPortfolioDay", do_cache = do_cache)
#>   df <- pp$Results[, c("code", "segment", "part", "part_acum", "theoricalQty")]
#>   colnames(df) <- c("symbol", "segment", "weight", "segment_weight", "position")
#>   df$weight <- df$weight / 100
#>   df$segment_weight <- df$segment_weight / 100
#>   df$refdate <- pp$Header$date
#> 
#>   df
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## index_comp_get
#> function(index_name,
#>                            cache_folder = cachedir(),
#>                            do_cache = TRUE) {
#>   f <- download_marketdata("GetTheoricalPortfolio", cache_folder, do_cache,
#>     index_name = index_name
#>   )
#>   df <- read_marketdata(
#>     f, "GetTheoricalPortfolio", TRUE,
#>     do_cache
#>   )
#>   df$Results$code
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## index_get
#> function(index_name, first_date,
#>                       last_date = Sys.Date(),
#>                       cache_folder = cachedir(),
#>                       do_cache = TRUE) {
#>   start_year <- format(first_date, "%Y") |> as.integer()
#>   end_year <- format(last_date, "%Y") |> as.integer()
#>   if (index_name == "IBOV") {
#>     if (start_year > 1997) {
#>       year <- seq(start_year, end_year)
#>       map_dfr(year, \(year) single_index_get(
#>         index_name, year, cache_folder,
#>         do_cache
#>       ))
#>     } else {
#>       if (end_year <= 1997) {
#>         df <- ibovespa_index_get(first_date, last_date)
#>       } else {
#>         df1 <- ibovespa_index_get(first_date, as.Date("1997-12-31"))
#>         year <- seq(1998, end_year)
#>         df2 <- map_dfr(year, \(year) single_index_get(
#>           index_name, year,
#>           cache_folder, do_cache
#>         )) |>
#>           filter(.data$refdate <= last_date)
#>         df <- bind_rows(df1, df2) |> arrange(.data$refdate)
#>       }
#>     }
#>   } else {
#>     year <- seq(start_year, end_year)
#>     df <- map_dfr(year, \(year) single_index_get(
#>       index_name, year,
#>       cache_folder, do_cache
#>     ))
#>     if (any(dim(df) == 0)) {
#>       return(NULL)
#>     } else {
#>       df |>
#>         filter(.data$refdate <= last_date, .data$refdate >= first_date)
#>     }
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## index_get_from_file
#> function(year) {
#>   index_data <- read_excel("./examples/IBOVDIA.XLS",
#>     sheet = as.character(year), skip = 1, range = "A3:M33",
#>     col_names = c("day", 1:12),
#>   )
#> 
#>   pivot_longer(index_data, "1":"12", names_to = "month") |>
#>     mutate(
#>       month = as.integer(.data$month),
#>       year = year,
#>       refdate = ISOdate(.data$year, .data$month, .data$day) |> as.Date(),
#>       index_name = "IBOV"
#>     ) |>
#>     filter(!is.na(.data$value)) |>
#>     arrange(.data$refdate) |>
#>     select(.data$refdate, .data$index_name, .data$value)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## index_weights_get
#> function(index_name,
#>                               cache_folder = cachedir(),
#>                               do_cache = TRUE) {
#>   f <- download_marketdata("GetTheoricalPortfolio", cache_folder, do_cache,
#>     index_name = index_name
#>   )
#>   df <- read_marketdata(
#>     f, "GetTheoricalPortfolio", TRUE,
#>     do_cache
#>   )
#>   ds <- df$Results[, c("code", "part", "theoricalQty")]
#>   colnames(ds) <- c("symbol", "weight", "position")
#>   ds$weight <- ds$weight / 100
#>   ds
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## indexes_get
#> function(cache_folder = cachedir(),
#>                         do_cache = TRUE) {
#>   f <- download_marketdata("GetStockIndex",
#>     cache_folder = cache_folder, do_cache = do_cache
#>   )
#>   df <- read_marketdata(f, "GetStockIndex", do_cache = do_cache)
#>   str_split(df$Results$indexes, ",") |>
#>     unlist() |>
#>     unique() |>
#>     sort()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## indexes_last_update
#> function(cache_folder = cachedir(),
#>                                 do_cache = TRUE) {
#>   f <- download_marketdata("GetStockIndex",
#>     cache_folder = cache_folder, do_cache = do_cache
#>   )
#>   df <- read_marketdata(f, "GetStockIndex", do_cache = do_cache)
#>   df$Header$update
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## indexreport_get
#> function(refdate = Sys.Date(),
#>                             cache_folder = cachedir(),
#>                             do_cache = TRUE) {
#>   get_single_indexreport(1, as.Date(refdate), cache_folder, do_cache)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## indexreport_mget
#> function(first_date = Sys.Date() - 5,
#>                              last_date = Sys.Date(),
#>                              by = 1,
#>                              cache_folder = cachedir(),
#>                              do_cache = TRUE) {
#>   first_date <- as.Date(first_date)
#>   last_date <- as.Date(last_date)
#>   tpl <- .retrieve_template(NULL, "IndexReport")
#>   date_vec <- bizseq(first_date, last_date, tpl$calendar)
#>   date_vec <- date_vec[seq(1, length(date_vec), by = by)]
#> 
#>   bind_rows(
#>     log_map_process_along(date_vec, get_single_indexreport,
#>       "Fetching data points",
#>       date_vec = date_vec,
#>       cache_folder = cache_folder,
#>       do_cache = do_cache
#>     )
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## indexreport_reader
#> function(., filename, parse_fields = TRUE) {
#>   doc <- xmlInternalTreeParse(filename)
#> 
#>   indxrpt <- getNodeSet(doc, "//d:IndxRpt", c(d = "urn:bvmf.218.01.xsd"))
#>   refdate_ <- xmlValue(indxrpt[[1]][["TradDt"]][["Dt"]])
#> 
#>   indxs <- getNodeSet(doc, "//d:IndxInf", c(d = "urn:bvmf.218.01.xsd"))
#> 
#>   df <- map_dfr(indxs, function(node) {
#>     inf_node <- node[["SctyInf"]]
#> 
#>     tibble(
#>       refdate = refdate_,
#>       symbol = xmlValue(inf_node[["SctyId"]][["TckrSymb"]]),
#>       security_id = xmlValue(inf_node[["FinInstrmId"]][["OthrId"]][["Id"]]),
#>       security_proprietary = xmlValue(
#>         inf_node[["FinInstrmId"]][["OthrId"]][["Tp"]][["Prtry"]]
#>       ),
#>       security_market = xmlValue(
#>         inf_node[["FinInstrmId"]][["PlcOfListg"]][["MktIdrCd"]]
#>       ),
#>       asset_desc = xmlValue(node[["AsstDesc"]]),
#>       settlement_price = xmlValue(node[["SttlmVal"]]),
#>       open = xmlValue(inf_node[["OpngPric"]]),
#>       min = xmlValue(inf_node[["MinPric"]]),
#>       max = xmlValue(inf_node[["MaxPric"]]),
#>       average = xmlValue(inf_node[["TradAvrgPric"]]),
#>       close = xmlValue(inf_node[["ClsgPric"]]),
#>       last_price = xmlValue(inf_node[["IndxVal"]]),
#>       oscillation_val = xmlValue(inf_node[["OscnVal"]]),
#>       rising_shares_number = xmlValue(node[["RsngShrsNb"]]),
#>       falling_shares_number = xmlValue(node[["FlngShrsNb"]]),
#>       stable_shares_number = xmlValue(node[["StblShrsNb"]])
#>     )
#>   })
#> 
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <bytecode: 0x55b9763f1dd8>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## inner_join
#> function (x, y, by = NULL, copy = FALSE, suffix = c(".x", ".y"), 
#>     ..., keep = FALSE) 
#> {
#>     UseMethod("inner_join")
#> }
#> <bytecode: 0x55b96ad4fc30>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## is
#> function (object, class2) 
#> {
#>     class1 <- class(object)
#>     S3Case <- length(class1) > 1L
#>     if (S3Case) 
#>         class1 <- class1[[1L]]
#>     if (missing(class2)) 
#>         return(extends(class1))
#>     stopifnot(length(class2) == 1L)
#>     class1Def <- getClassDef(class1)
#>     class2Def <- NULL
#>     if (!is.character(class2)) {
#>         class2Def <- class2
#>         class2 <- class2Def@className
#>     }
#>     if (is.null(class1Def)) 
#>         return(inherits(object, class2))
#>     if (is.null(class2Def)) {
#>         class2Def <- getClassDef(class2, .classDefEnv(class1Def), 
#>             if (!is.null(package <- packageSlot(class2))) 
#>                 package
#>             else getPackageName(topenv(parent.frame())))
#>     }
#>     S3Case <- S3Case || (is.object(object) && !isS4(object))
#>     S3Case <- S3Case && (is.null(class2Def) || class2 %in% .BasicClasses || 
#>         extends(class2Def, "oldClass"))
#>     if (S3Case) 
#>         inherits(object, class2)
#>     else if (.identC(class1, class2) || .identC(class2, "ANY")) 
#>         TRUE
#>     else {
#>         if (!is.null(contained <- class1Def@contains[[class2]])) 
#>             contained@simple || contained@test(object)
#>         else if (is.null(class2Def)) 
#>             FALSE
#>         else if (!.identC(class(class2Def), "classRepresentation") && 
#>             isClassUnion(class2Def)) 
#>             any(c(class1, names(class1Def@contains)) %in% names(class2Def@subclasses))
#>         else {
#>             ext <- class2Def@subclasses[[class1]]
#>             !is.null(ext) && (ext@simple || ext@test(object))
#>         }
#>     }
#> }
#> <bytecode: 0x55b96958e850>
#> <environment: namespace:methods>
#> --- 
#>  
#> ## iter_rules
#> function(rules) {
#>   idx <- take(rules, "priority")
#>   idx <- order(idx)
#>   rules[idx]
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## json_read_file
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   df <- as.data.frame(jason)
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## just_download_data
#> function(url, encoding, dest) {
#>   res <- GET(url)
#>   if (status_code(res) != 200 || !.safecontent(res)) {
#>     return(FALSE)
#>   }
#>   save_resource(res, encoding, dest)
#>   TRUE
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## left_join
#> function (x, y, by = NULL, copy = FALSE, suffix = c(".x", ".y"), 
#>     ..., keep = FALSE) 
#> {
#>     UseMethod("left_join")
#> }
#> <bytecode: 0x55b96ad4ac50>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## library.dynam
#> function (chname, package, lib.loc, verbose = getOption("verbose"), 
#>     file.ext = .Platform$dynlib.ext, ...) 
#> {
#>     dll_list <- .dynLibs()
#>     if (missing(chname) || !nzchar(chname)) 
#>         return(dll_list)
#>     package
#>     lib.loc
#>     r_arch <- .Platform$r_arch
#>     chname1 <- paste0(chname, file.ext)
#>     for (pkg in find.package(package, lib.loc, verbose = verbose)) {
#>         DLLpath <- if (nzchar(r_arch)) 
#>             file.path(pkg, "libs", r_arch)
#>         else file.path(pkg, "libs")
#>         file <- file.path(DLLpath, chname1)
#>         if (file.exists(file)) 
#>             break
#>         else file <- ""
#>     }
#>     if (file == "") 
#>         if (.Platform$OS.type == "windows") 
#>             stop(gettextf("DLL %s not found: maybe not installed for this architecture?", 
#>                 sQuote(chname)), domain = NA)
#>         else stop(gettextf("shared object %s not found", sQuote(chname1)), 
#>             domain = NA)
#>     file <- file.path(normalizePath(DLLpath, "/", TRUE), chname1)
#>     ind <- vapply(dll_list, function(x) x[["path"]] == file, 
#>         NA)
#>     if (length(ind) && any(ind)) {
#>         if (verbose) 
#>             if (.Platform$OS.type == "windows") 
#>                 message(gettextf("DLL %s already loaded", sQuote(chname1)), 
#>                   domain = NA)
#>             else message(gettextf("shared object '%s' already loaded", 
#>                 sQuote(chname1)), domain = NA)
#>         return(invisible(dll_list[[seq_along(dll_list)[ind]]]))
#>     }
#>     if (.Platform$OS.type == "windows") {
#>         PATH <- Sys.getenv("PATH")
#>         Sys.setenv(PATH = paste(gsub("/", "\\\\", DLLpath), PATH, 
#>             sep = ";"))
#>         on.exit(Sys.setenv(PATH = PATH))
#>     }
#>     if (verbose) 
#>         message(gettextf("now dyn.load(\"%s\") ...", file), domain = NA)
#>     dll <- if ("DLLpath" %in% ...names()) 
#>         dyn.load(file, ...)
#>     else dyn.load(file, DLLpath = DLLpath, ...)
#>     .dynLibs(c(dll_list, list(dll)))
#>     invisible(dll)
#> }
#> <bytecode: 0x55b968b4f108>
#> <environment: namespace:base>
#> --- 
#>  
#> ## library.dynam.unload
#> function (chname, libpath, verbose = getOption("verbose"), file.ext = .Platform$dynlib.ext) 
#> {
#>     dll_list <- .dynLibs()
#>     if (missing(chname) || nchar(chname, "c") == 0L) 
#>         if (.Platform$OS.type == "windows") 
#>             stop("no DLL was specified")
#>         else stop("no shared object was specified")
#>     libpath <- normalizePath(libpath, "/", TRUE)
#>     chname1 <- paste0(chname, file.ext)
#>     file <- if (nzchar(.Platform$r_arch)) 
#>         file.path(libpath, "libs", .Platform$r_arch, chname1)
#>     else file.path(libpath, "libs", chname1)
#>     pos <- which(vapply(dll_list, function(x) x[["path"]] == 
#>         file, NA))
#>     if (!length(pos)) 
#>         if (.Platform$OS.type == "windows") 
#>             stop(gettextf("DLL %s was not loaded", sQuote(chname1)), 
#>                 domain = NA)
#>         else stop(gettextf("shared object %s was not loaded", 
#>             sQuote(chname1)), domain = NA)
#>     if (!file.exists(file)) 
#>         if (.Platform$OS.type == "windows") 
#>             stop(gettextf("DLL %s not found", sQuote(chname1)), 
#>                 domain = NA)
#>         else stop(gettextf("shared object '%s' not found", sQuote(chname1)), 
#>             domain = NA)
#>     if (verbose) 
#>         message(gettextf("now dyn.unload(\"%s\") ...", file), 
#>             domain = NA)
#>     dyn.unload(file)
#>     .dynLibs(dll_list[-pos])
#>     invisible(dll_list[[pos]])
#> }
#> <bytecode: 0x55b975566910>
#> <environment: namespace:base>
#> --- 
#>  
#> ## load_builtin_calendars
#> function () 
#> {
#>     cal_dir <- system.file("extdata", package = "bizdays")
#>     fnames <- list.files(cal_dir, pattern = "json$", full.names = TRUE)
#>     lapply(fnames, load_calendar)
#>     bizdays.options$set(default.calendar = "actual")
#> }
#> <bytecode: 0x55b971275fd0>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## load_templates
#> function() {
#>   dir <- system.file("extdata/templates/",
#>     package = "rb3",
#>     mustWork = TRUE
#>   )
#>   files <- list.files(dir, full.names = TRUE)
#>   for (file in files) {
#>     tpl <- yaml.load_file(file)
#>     new_template(tpl)
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## log_map_process_along
#> function(x, func, msg, ...) {
#>   f_ <- paste(
#>     "{pb_spin}",
#>     "{msg}",
#>     "{pb_current}/{pb_total}",
#>     "|",
#>     "{pb_bar}",
#>     "{pb_percent}",
#>     "|",
#>     "{pb_eta_str}"
#>   )
#>   rb3_hide_progressbar <- getOption("rb3.silent")
#>   if (!is.null(rb3_hide_progressbar) && isTRUE(rb3_hide_progressbar)) {
#>     map(seq_along(x), func, ...)
#>   } else {
#>     map(cli_progress_along(x, format = f_), func, ...)
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## map
#> function (.x, .f, ...) 
#> {
#>     .f <- as_mapper(.f, ...)
#>     .Call(map_impl, environment(), ".x", ".f", "list")
#> }
#> <bytecode: 0x55b974ed17a8>
#> <environment: namespace:purrr>
#> --- 
#>  
#> ## map_chr
#> function (.x, .f, ...) 
#> {
#>     .f <- as_mapper(.f, ...)
#>     .Call(map_impl, environment(), ".x", ".f", "character")
#> }
#> <bytecode: 0x55b976e88940>
#> <environment: namespace:purrr>
#> --- 
#>  
#> ## map_dfr
#> function (.x, .f, ..., .id = NULL) 
#> {
#>     if (!is_installed("dplyr")) {
#>         abort("`map_df()` requires dplyr")
#>     }
#>     .f <- as_mapper(.f, ...)
#>     res <- map(.x, .f, ...)
#>     dplyr::bind_rows(res, .id = .id)
#> }
#> <bytecode: 0x55b9741008a0>
#> <environment: namespace:purrr>
#> --- 
#>  
#> ## map_int
#> function (.x, .f, ...) 
#> {
#>     .f <- as_mapper(.f, ...)
#>     .Call(map_impl, environment(), ".x", ".f", "integer")
#> }
#> <bytecode: 0x55b96bed7008>
#> <environment: namespace:purrr>
#> --- 
#>  
#> ## map_lgl
#> function (.x, .f, ...) 
#> {
#>     .f <- as_mapper(.f, ...)
#>     .Call(map_impl, environment(), ".x", ".f", "logical")
#> }
#> <bytecode: 0x55b977172248>
#> <environment: namespace:purrr>
#> --- 
#>  
#> ## MarketData
#> <environment: 0x55b973113ca8>
#> attr(,"class")
#> [1] "proto"       "environment"
#> --- 
#>  
#> ## match_class
#> function(class, handler, priority = NA, na.rm = TRUE) {
#>   structure(
#>     list(class = class, handler = handler, priority = priority, na.rm = na.rm),
#>     class = c("match_rule", "class_rule")
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## match_predicate
#> function(predicate, handler, priority = NA, na.rm = TRUE) {
#>   structure(
#>     list(
#>       predicate = predicate, handler = handler, priority = priority,
#>       na.rm = na.rm
#>     ),
#>     class = c("match_rule", "predicate_rule")
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## match_regex
#> function(regex, handler, priority = NA,
#>                         apply_to = c("any", "all"), na.rm = TRUE) {
#>   apply_to <- .apply_to(match.arg(apply_to))
#>   structure(
#>     list(
#>       regex = regex, handler = handler, priority = priority,
#>       apply_to = apply_to, na.rm = na.rm
#>     ),
#>     class = c("match_rule", "regex_rule")
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## maturity2date
#> function(x, expr = "first day", refdate = NULL) {
#>   res <- character(length(x))
#>   ix <- which(str_length(x) == 3)
#>   if (length(ix)) {
#>     res[ix] <- maturity2date_newcode(x[ix], expr)
#>   }
#>   ix <- which(str_length(x) == 4)
#>   if (length(ix)) {
#>     res[ix] <- maturity2date_oldcode(x[ix], expr, refdate)
#>   }
#>   as.Date(res)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## maturity2date_newcode
#> function(x, expr = "first day") {
#>   year <- as.integer(str_sub(x, 2)) + 2000
#>   month <- code2month_newcode(str_sub(x, 1, 1))
#>   month <- str_pad(month, 2, pad = "0")
#>   getdate(expr, paste0(year, "-", month), "Brazil/BMF") |> as.character()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## maturity2date_oldcode
#> function(x, expr = "first day", refdate = NULL) {
#>   base_year <- 2000
#>   if (!is.null(refdate) && refdate >= as.Date("2001-01-01")) {
#>     base_year <- 2010
#>   }
#>   year <- as.integer(str_sub(x, 4)) + base_year
#>   month <- code2month_oldcode(str_sub(x, 1, 3))
#>   month <- str_pad(month, 2, pad = "0")
#>   getdate(expr, paste0(year, "-", month), "Brazil/BMF") |> as.character()
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## mcsv_read_file
#> function(., filename, parse_fields = TRUE) {
#>   lines <- readLines(filename)
#>   l <- list()
#>   for (part_name in names(.$parts)) {
#>     part <- .$parts[[part_name]]
#>     idx <- .$.detect_lines(part, lines)
#>     df <- read.table(
#>       text = lines[idx], col.names = part$colnames, sep = .$.separator(part),
#>       as.is = TRUE, stringsAsFactors = FALSE, check.names = FALSE,
#>       colClasses = "character"
#>     )
#>     l[[part_name]] <- if (parse_fields) {
#>       parse_columns(df, part$colnames, part$handlers, .$.parser())
#>     } else {
#>       df
#>     }
#>   }
#>   class(l) <- "parts"
#>   l
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## mfwf_read_file
#> function(., filename, parse_fields = TRUE) {
#>   lines <- readLines(filename)
#>   l <- list()
#>   for (part_name in names(.$parts)) {
#>     part <- .$parts[[part_name]]
#>     idx <- .$.detect_lines(part, lines)
#>     df <- read_fwf(
#>       text = lines[idx], widths = part$widths,
#>       colnames = part$colnames
#>     )
#>     l[[part_name]] <- if (parse_fields) {
#>       parse_columns(df, part$colnames, part$handlers, .$.parser())
#>     } else {
#>       df
#>     }
#>   }
#>   class(l) <- "parts"
#>   l
#> }
#> <bytecode: 0x55b97ad97e88>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## mutate
#> function (.data, ...) 
#> {
#>     UseMethod("mutate")
#> }
#> <bytecode: 0x55b96ad417c0>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## new
#> function (Class, ...) 
#> {
#>     ClassDef <- getClass(Class, where = topenv(parent.frame()))
#>     value <- .Call(C_new_object, ClassDef)
#>     initialize(value, ...)
#> }
#> <bytecode: 0x55b96a40c448>
#> <environment: namespace:methods>
#> --- 
#>  
#> ## new_field
#> function(x) {
#>   width_ <- if (!is.null(x$width)) width(x$width)
#>   if (is.null(x$handler$type)) {
#>     handler_ <- pass_thru_handler()
#>   } else if (x$handler$type == "numeric") {
#>     handler_ <- to_numeric_handler(x$handler$dec, x$handler$sign)
#>   } else if (x$handler$type == "factor") {
#>     handler_ <- to_factor_handler(x$handler$levels, x$handler$labels)
#>   } else if (x$handler$type == "Date") {
#>     handler_ <- to_date_handler(x$handler$format)
#>   } else if (x$handler$type == "POSIXct") {
#>     handler_ <- to_time_handler(x$handler$format)
#>   } else if (x$handler$type == "strtime") {
#>     handler_ <- to_strtime_handler(x$handler$format)
#>   } else {
#>     handler_ <- pass_thru_handler()
#>   }
#>   field(x$name, x$description, width_, handler_)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## new_part
#> function(x) {
#>   part <- list()
#>   for (np in names(x)) {
#>     if (np == "fields") {
#>       part[["fields"]] <- do.call(fields, lapply(x[["fields"]], new_field))
#>     } else {
#>       part[[np]] <- x[[np]]
#>     }
#>   }
#>   part
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## new_template
#> function(tpl) {
#>   obj <- MarketData$proto()
#>   obj[["has_reader"]] <- FALSE
#>   obj[["has_downloader"]] <- FALSE
#>   for (n in names(tpl)) {
#>     if (n == "fields") {
#>       obj[["fields"]] <- do.call(fields, lapply(tpl$fields, new_field))
#>     } else if (n == "parts") {
#>       obj[["parts"]] <- lapply(tpl$parts, new_part)
#>     } else if (n == "reader") {
#>       obj[["has_reader"]] <- TRUE
#>       obj[["reader"]] <- tpl$reader
#>       func_name <- tpl$reader[["function"]]
#>       obj[["read_file"]] <- getFromNamespace(func_name, "rb3")
#>     } else if (n == "downloader") {
#>       obj[["has_downloader"]] <- TRUE
#>       obj[["downloader"]] <- tpl$downloader
#>       func_name <- tpl$downloader[["function"]]
#>       obj[["download_marketdata"]] <- getFromNamespace(func_name, "rb3")
#>     } else {
#>       obj[[n]] <- tpl[[n]]
#>     }
#>   }
#> 
#>   if (is(try(obj$reader, TRUE), "try-error")) {
#>     reader_name <- paste0(str_to_lower(obj$filetype), "_read_file")
#>     obj[["read_file"]] <- getFromNamespace(reader_name, "rb3")
#>     obj[["has_reader"]] <- TRUE
#>   }
#> 
#>   if (obj$filetype %in% c("MCSV", "MFWF", "MCUSTOM")) {
#>     obj[["init"]] <- .multipart_init
#>   }
#> 
#>   MarketData$register(obj)
#>   obj
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## options_open_interest_read
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   if (is.null(jason$Empresa)) {
#>     return(NULL)
#>   }
#>   df <- do.call(rbind, jason$Empresa)
#>   names(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## parse_columns
#> function(df, colnames, handlers, parser) {
#>   df <- trim_fields(df)
#>   e <- evalq(environment(), df, NULL)
#>   df <- lapply(colnames, function(x) {
#>     fun <- handlers[[x]]
#>     x <- df[[x]]
#>     do.call(fun, list(x), envir = e)
#>   })
#>   names(df) <- colnames
#>   df <- do.call(
#>     "data.frame",
#>     c(df, stringsAsFactors = FALSE, check.names = FALSE)
#>   )
#>   parse_text(parser, df) |> as_tibble()
#> }
#> <bytecode: 0x55b979bc30b8>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## parse_text
#> function(x, data, ...) standardGeneric("parse_text")
#> <environment: 0x55b9761a98e8>
#> attr(,"generic")
#> [1] "parse_text"
#> attr(,"generic")attr(,"package")
#> [1] "rb3"
#> attr(,"package")
#> [1] "rb3"
#> attr(,"group")
#> list()
#> attr(,"valueClass")
#> character(0)
#> attr(,"signature")
#> [1] "x"    "data"
#> attr(,"default")
#> `\001NULL\001`
#> attr(,"skeleton")
#> (function (x, data, ...) 
#> stop(gettextf("invalid call in method dispatch to '%s' (no default method)", 
#>     "parse_text"), domain = NA))(x, data, ...)
#> attr(,"class")
#> [1] "standardGeneric"
#> attr(,"class")attr(,"package")
#> [1] "methods"
#> --- 
#>  
#> ## parse_url
#> function (url) 
#> {
#>     if (is.url(url)) 
#>         return(url)
#>     url <- as.character(url)
#>     stopifnot(length(url) == 1)
#>     pull_off <- function(pattern) {
#>         if (!str_detect(url, pattern)) 
#>             return(NULL)
#>         piece <- str_match(url, pattern)[, 2]
#>         url <<- str_replace(url, pattern, "")
#>         piece
#>     }
#>     fragment <- pull_off("#(.*)$")
#>     scheme <- pull_off("^([[:alpha:]][[:alpha:][:digit:]+.-]*):")
#>     netloc <- pull_off("^//([^/?]*)/?")
#>     if (identical(netloc, "")) {
#>         url <- paste0("/", url)
#>         port <- username <- password <- hostname <- NULL
#>     }
#>     else if (!is.null(netloc)) {
#>         pieces <- strsplit(netloc, "@")[[1]]
#>         if (length(pieces) == 1) {
#>             username <- NULL
#>             password <- NULL
#>             host <- pieces
#>         }
#>         else {
#>             user_pass <- strsplit(pieces[[1]], ":")[[1]]
#>             username <- user_pass[1]
#>             if (length(user_pass) == 1) {
#>                 password <- NULL
#>             }
#>             else {
#>                 password <- user_pass[2]
#>             }
#>             host <- pieces[2]
#>         }
#>         host_pieces <- str_split(host, ":")[[1]]
#>         hostname <- host_pieces[1]
#>         port <- if (length(host_pieces) > 1) 
#>             host_pieces[2]
#>     }
#>     else {
#>         port <- username <- password <- hostname <- NULL
#>     }
#>     query <- pull_off("\\?(.*)$")
#>     if (!is.null(query)) {
#>         query <- parse_query(query)
#>     }
#>     params <- pull_off(";(.*)$")
#>     structure(list(scheme = scheme, hostname = hostname, port = port, 
#>         path = url, query = query, params = params, fragment = fragment, 
#>         username = username, password = password), class = "url")
#> }
#> <bytecode: 0x55b9731f6810>
#> <environment: namespace:httr>
#> --- 
#>  
#> ## parser_generic
#> An object of class "Transmuter"
#> Slot "envir":
#> <environment: 0x55b97479d1b0>
#> 
#> Slot "rules":
#> [[1]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] 1
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[2]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("any")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[3]]
#> $regex
#> [1] "^\\+|-$"
#> 
#> $handler
#> function(text, match) {
#>     idx <- text == "-"
#>     x <- rep(1, length(text))
#>     x[idx] <- -1
#>     x
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[4]]
#> $regex
#> [1] "^(S|N)$"
#> 
#> $handler
#> function(text, match) {
#>     text == "S"
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> 
#> --- 
#>  
#> ## parsers
#> $generic
#> An object of class "Transmuter"
#> Slot "envir":
#> <environment: 0x55b97479d1b0>
#> 
#> Slot "rules":
#> [[1]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] 1
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[2]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("any")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[3]]
#> $regex
#> [1] "^\\+|-$"
#> 
#> $handler
#> function(text, match) {
#>     idx <- text == "-"
#>     x <- rep(1, length(text))
#>     x[idx] <- -1
#>     x
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[4]]
#> $regex
#> [1] "^(S|N)$"
#> 
#> $handler
#> function(text, match) {
#>     text == "S"
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> 
#> 
#> $en
#> An object of class "Transmuter"
#> Slot "envir":
#> <environment: 0x55b973148930>
#> 
#> Slot "rules":
#> [[1]]
#> $regex
#> [1] "^(-|\\+)?(\\d+,)*\\d+(\\.\\d+)?$"
#> 
#> $handler
#> function(x, ...) as.numeric(.func(x)) * .mult
#> <environment: 0x55b973ab9b68>
#> 
#> $priority
#> [1] 2
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[2]]
#> $regex
#> [1] "^(-|\\+)?(\\d+,)*\\d+(\\.\\d+)?$"
#> 
#> $handler
#> function(x, ...) as.numeric(.func(x)) * .mult
#> <bytecode: 0x55b973160d30>
#> <environment: 0x55b973ab8a48>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("any")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[3]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] 1
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[4]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("any")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[5]]
#> $regex
#> [1] "^\\+|-$"
#> 
#> $handler
#> function(text, match) {
#>     idx <- text == "-"
#>     x <- rep(1, length(text))
#>     x[idx] <- -1
#>     x
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[6]]
#> $regex
#> [1] "^(S|N)$"
#> 
#> $handler
#> function(text, match) {
#>     text == "S"
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> 
#> 
#> $pt
#> An object of class "Transmuter"
#> Slot "envir":
#> <environment: 0x55b97311fc00>
#> 
#> Slot "rules":
#> [[1]]
#> $regex
#> [1] "^(-|\\+)?(\\d+\\.)*\\d+(,\\d+)?$"
#> 
#> $handler
#> function(x, ...) as.numeric(.func(x)) * .mult
#> <bytecode: 0x55b973160d30>
#> <environment: 0x55b973139ee8>
#> 
#> $priority
#> [1] 2
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[2]]
#> $regex
#> [1] "^(-|\\+)?(\\d+\\.)*\\d+(,\\d+)?$"
#> 
#> $handler
#> function(x, ...) as.numeric(.func(x)) * .mult
#> <bytecode: 0x55b973160d30>
#> <environment: 0x55b973139768>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("any")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[3]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] 1
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[4]]
#> $regex
#> [1] "^(-|\\+)?\\d{1,8}$"
#> 
#> $handler
#> function (x, ...)  .Primitive("as.integer")
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("any")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[5]]
#> $regex
#> [1] "^\\+|-$"
#> 
#> $handler
#> function(text, match) {
#>     idx <- text == "-"
#>     x <- rep(1, length(text))
#>     x[idx] <- -1
#>     x
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> [[6]]
#> $regex
#> [1] "^(S|N)$"
#> 
#> $handler
#> function(text, match) {
#>     text == "S"
#>   }
#> <environment: namespace:rb3>
#> 
#> $priority
#> [1] NA
#> 
#> $apply_to
#> function (..., na.rm = FALSE)  .Primitive("all")
#> 
#> $na.rm
#> [1] TRUE
#> 
#> attr(,"class")
#> [1] "match_rule" "regex_rule"
#> 
#> 
#> 
#> --- 
#>  
#> ## pass_thru_handler
#> function() {
#>   handler <- identity
#>   attr(handler, "type") <- "character"
#>   class(handler) <- c("function", "handler")
#>   handler
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## pb_bar
#> [1] ""
#> --- 
#>  
#> ## pb_current
#> [1] ""
#> --- 
#>  
#> ## pb_eta_str
#> [1] ""
#> --- 
#>  
#> ## pb_percent
#> [1] ""
#> --- 
#>  
#> ## pb_spin
#> [1] ""
#> --- 
#>  
#> ## pb_total
#> [1] ""
#> --- 
#>  
#> ## pivot_longer
#> function (data, cols, names_to = "name", names_prefix = NULL, 
#>     names_sep = NULL, names_pattern = NULL, names_ptypes = NULL, 
#>     names_transform = NULL, names_repair = "check_unique", values_to = "value", 
#>     values_drop_na = FALSE, values_ptypes = NULL, values_transform = NULL, 
#>     ...) 
#> {
#>     ellipsis::check_dots_used()
#>     UseMethod("pivot_longer")
#> }
#> <bytecode: 0x55b974eb3888>
#> <environment: namespace:tidyr>
#> --- 
#>  
#> ## POST
#> function (url = NULL, config = list(), ..., body = NULL, encode = c("multipart", 
#>     "form", "json", "raw"), handle = NULL) 
#> {
#>     encode <- match.arg(encode)
#>     hu <- handle_url(handle, url, ...)
#>     req <- request_build("POST", hu$url, body_config(body, match.arg(encode)), 
#>         as.request(config), ...)
#>     request_perform(req, hu$handle$handle)
#> }
#> <bytecode: 0x55b9730ecdb8>
#> <environment: namespace:httr>
#> --- 
#>  
#> ## preceding
#> function (dates, cal) 
#> UseMethod("preceding")
#> <bytecode: 0x55b96bd11750>
#> <environment: namespace:bizdays>
#> --- 
#>  
#> ## pricereport_reader
#> function(., filename, parse_fields = TRUE) {
#>   doc <- xmlInternalTreeParse(filename)
#>   negs <- getNodeSet(doc, "//d:PricRpt", c(d = "urn:bvmf.217.01.xsd"))
#> 
#>   df <- map_dfr(negs, function(node) {
#>     refdate <- xmlValue(node[["TradDt"]][["Dt"]])
#>     ticker <- xmlValue(node[["SctyId"]][["TckrSymb"]])
#>     attrib <- node[["FinInstrmAttrbts"]]
#> 
#>     tibble(
#>       refdate = refdate,
#>       ticker_symbol = ticker,
#>       security_id = xmlValue(node[["FinInstrmId"]][["OthrId"]][["Id"]]),
#>       security_proprietary = xmlValue(
#>         node[["FinInstrmId"]][["OthrId"]][["Tp"]][["Prtry"]]
#>       ),
#>       security_market = xmlValue(
#>         node[["FinInstrmId"]][["PlcOfListg"]][["MktIdrCd"]]
#>       ),
#>       volume = xmlValue(attrib[["NtlFinVol"]]),
#>       open_interest = xmlValue(attrib[["OpnIntrst"]]),
#>       traded_contracts = xmlValue(attrib[["FinInstrmQty"]]),
#>       best_ask_price = xmlValue(attrib[["BestAskPric"]]),
#>       best_bid_price = xmlValue(attrib[["BestBidPric"]]),
#>       first_price = xmlValue(attrib[["FrstPric"]]),
#>       min_price = xmlValue(attrib[["MinPric"]]),
#>       max_price = xmlValue(attrib[["MaxPric"]]),
#>       last_price = xmlValue(attrib[["LastPric"]]),
#>       average_price = xmlValue(attrib[["TradAvrgPric"]]),
#>       regular_transactions_quantity = xmlValue(attrib[["RglrTxsQty"]]),
#>       regular_traded_contracts = xmlValue(attrib[["RglrTraddCtrcts"]]),
#>       regular_volume = xmlValue(attrib[["NtlRglrVol"]]),
#>       nonregular_transactions_quantity = xmlValue(attrib[["NonRglrTxsQty"]]),
#>       nonregular_traded_contracts = xmlValue(attrib[["NonRglrTraddCtrcts"]]),
#>       nonregular_volume = xmlValue(attrib[["NtlNonRglrVol"]]),
#>       oscillation_percentage = xmlValue(attrib[["OscnPctg"]]),
#>       adjusted_quote = xmlValue(attrib[["AdjstdQt"]]),
#>       adjusted_tax = xmlValue(attrib[["AdjstdQtTax"]]),
#>       previous_adjusted_quote = xmlValue(attrib[["PrvsAdjstdQt"]]),
#>       previous_adjusted_tax = xmlValue(attrib[["PrvsAdjstdQtTax"]]),
#>       variation_points = xmlValue(attrib[["VartnPts"]]),
#>       adjusted_value_contract = xmlValue(attrib[["AdjstdValCtrct"]]),
#>     )
#>   })
#> 
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## print
#> function (x, ...) 
#> UseMethod("print")
#> <bytecode: 0x55b969dccf98>
#> <environment: namespace:base>
#> --- 
#>  
#> ## print.fields
#> function(x, ...) {
#>   df <- as.data.frame(x)
#>   suppressWarnings(
#>     print(ascii(df, include.rownames = TRUE), type = "org")
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## print.parts
#> function(x, ...) {
#>   nx <- names(x)
#>   for (ix in seq_along(nx)) {
#>     dx <- dim(x[[ix]])
#>     cat(sprintf(
#>       "Part %2d: %s [%d obs. of %d variables]", ix, nx[ix], dx[1],
#>       dx[2]
#>     ), "\n")
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## proto
#> function (. = parent.env(envir), expr = {
#> }, envir = new.env(parent = parent.frame()), ..., funEnvir = envir) 
#> {
#>     parent.env(envir) <- .
#>     envir <- as.proto.environment(envir)
#>     dots <- list(...)
#>     names <- names(dots)
#>     for (i in seq_along(dots)) {
#>         assign(names[i], dots[[i]], envir = envir)
#>         if (!identical(funEnvir, FALSE) && is.function(dots[[i]])) 
#>             environment(envir[[names[i]]]) <- funEnvir
#>     }
#>     eval(substitute(eval(quote({
#>         expr
#>     }))), envir)
#>     if (length(dots)) 
#>         as.proto.environment(envir)
#>     else envir
#> }
#> <bytecode: 0x55b9771837f8>
#> <environment: namespace:proto>
#> --- 
#>  
#> ## query_cdi
#> function() {
#>   fname <- download_marketdata("CDIIDI", do_cache = FALSE)
#> 
#>   if (!is.null(fname)) {
#>     read_marketdata(fname, "CDIIDI", do_cache = FALSE)
#>   } else {
#>     alert("danger", "Failed CDIIDI download")
#>     NULL
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## read_csv
#> function (file, col_names = TRUE, col_types = NULL, col_select = NULL, 
#>     id = NULL, locale = default_locale(), na = c("", "NA"), quoted_na = TRUE, 
#>     quote = "\"", comment = "", trim_ws = TRUE, skip = 0, n_max = Inf, 
#>     guess_max = min(1000, n_max), name_repair = "unique", num_threads = readr_threads(), 
#>     progress = show_progress(), show_col_types = should_show_types(), 
#>     skip_empty_rows = TRUE, lazy = should_read_lazy()) 
#> {
#>     if (edition_first()) {
#>         tokenizer <- tokenizer_csv(na = na, quoted_na = quoted_na, 
#>             quote = quote, comment = comment, trim_ws = trim_ws, 
#>             skip_empty_rows = skip_empty_rows)
#>         return(read_delimited(file, tokenizer, col_names = col_names, 
#>             col_types = col_types, locale = locale, skip = skip, 
#>             skip_empty_rows = skip_empty_rows, comment = comment, 
#>             n_max = n_max, guess_max = guess_max, progress = progress, 
#>             show_col_types = show_col_types))
#>     }
#>     if (!missing(quoted_na)) {
#>         lifecycle::deprecate_soft("2.0.0", "readr::read_csv(quoted_na = )")
#>     }
#>     vroom::vroom(file, delim = ",", col_names = col_names, col_types = col_types, 
#>         col_select = {
#>             {
#>                 col_select
#>             }
#>         }, id = id, .name_repair = name_repair, skip = skip, 
#>         n_max = n_max, na = na, quote = quote, comment = comment, 
#>         skip_empty_rows = skip_empty_rows, trim_ws = trim_ws, 
#>         escape_double = TRUE, escape_backslash = FALSE, locale = locale, 
#>         guess_max = guess_max, show_col_types = show_col_types, 
#>         progress = progress, altrep = lazy, num_threads = num_threads)
#> }
#> <bytecode: 0x55b974329948>
#> <environment: namespace:readr>
#> --- 
#>  
#> ## read_excel
#> function (path, sheet = NULL, range = NULL, col_names = TRUE, 
#>     col_types = NULL, na = "", trim_ws = TRUE, skip = 0, n_max = Inf, 
#>     guess_max = min(1000, n_max), progress = readxl_progress(), 
#>     .name_repair = "unique") 
#> {
#>     path <- check_file(path)
#>     format <- check_format(path)
#>     read_excel_(path = path, sheet = sheet, range = range, col_names = col_names, 
#>         col_types = col_types, na = na, trim_ws = trim_ws, skip = skip, 
#>         n_max = n_max, guess_max = guess_max, progress = progress, 
#>         .name_repair = .name_repair, format = format)
#> }
#> <bytecode: 0x55b974306240>
#> <environment: namespace:readxl>
#> --- 
#>  
#> ## read_file
#> function (file, locale = default_locale()) 
#> {
#>     if (empty_file(file)) {
#>         return("")
#>     }
#>     ds <- datasource(file, skip_empty_rows = FALSE)
#>     read_file_(ds, locale)
#> }
#> <bytecode: 0x55b9763b92a0>
#> <environment: namespace:readr>
#> --- 
#>  
#> ## read_fwf
#> function(fname, widths, colnames = NULL, skip = 0, text) {
#>   colpositions <- list()
#>   x <- 1
#>   i <- 1
#>   for (y in widths) {
#>     colpositions[[i]] <- c(x, x + y - 1)
#>     x <- x + y
#>     i <- i + 1
#>   }
#> 
#>   if (is.null(colnames)) {
#>     colnames <- paste0("V", seq_along(widths))
#>   }
#> 
#>   lines <- if (missing(text)) readLines(fname) else text
#> 
#>   if (skip) {
#>     lines <- lines[-seq(skip), ]
#>   }
#> 
#>   t <- list()
#>   for (i in seq_along(colnames)) {
#>     dx <- colpositions[[i]]
#>     t[[colnames[i]]] <- str_sub(lines, dx[1], dx[2])
#>   }
#> 
#>   as.data.frame(t,
#>     stringsAsFactors = FALSE, optional = TRUE,
#>     check.names = FALSE
#>   )
#> }
#> <bytecode: 0x55b97d18e320>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## read_html
#> function (x, encoding = "", ..., options = c("RECOVER", "NOERROR", 
#>     "NOBLANKS")) 
#> {
#>     UseMethod("read_html")
#> }
#> <bytecode: 0x55b97054e020>
#> <environment: namespace:xml2>
#> --- 
#>  
#> ## read_marketdata
#> function(filename, template = NULL,
#>                             parse_fields = TRUE,
#>                             do_cache = TRUE) {
#>   template <- .retrieve_template(filename, template)
#>   basename_ <- str_replace(basename(filename), "\\.[^\\.]+$", "") |>
#>     str_replace("\\.", "_")
#>   parsed_ <- if (parse_fields) "parsed" else "strict"
#>   cache_folder <- dirname(filename)
#>   f_cache <- file.path(
#>     cache_folder, str_glue("{b}-{p}.rds", b = basename_, p = parsed_)
#>   )
#> 
#>   if (file.exists(f_cache) && do_cache) {
#>     df_ <- read_rds(f_cache)
#>     if (is.null(df_)) {
#>       alert("warning", "Removed cached file {f_cache} that returns NULL.",
#>         f_cache = f_cache
#>       )
#>       unlink(f_cache)
#>     }
#>     return(df_)
#>   }
#>   df <- template$read_file(filename, parse_fields)
#>   if (is.null(df)) {
#>     rb3_clear_cache <- getOption("rb3.clear.cache")
#>     if (!is.null(rb3_clear_cache) && isTRUE(rb3_clear_cache)) {
#>       alert(
#>         "warning",
#>         "Removed {filename} - It hasn't valid content.",
#>         filename = filename
#>       )
#>       unlink(filename)
#>     } else {
#>       alert(
#>         "warning",
#>         "{filename} hasn't valid content, consider removing if it is cached.",
#>         filename = filename
#>       )
#>     }
#>   }
#>   if (do_cache && !is.null(df)) {
#>     write_rds(df, f_cache)
#>   }
#>   df
#> }
#> <bytecode: 0x55b97b94eb48>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## read_rds
#> function (file, refhook = NULL) 
#> {
#>     con <- file(file)
#>     on.exit(close(con))
#>     readRDS(con, refhook = refhook)
#> }
#> <bytecode: 0x55b97a974d80>
#> <environment: namespace:readr>
#> --- 
#>  
#> ## read.table
#> function (file, header = FALSE, sep = "", quote = "\"'", dec = ".", 
#>     numerals = c("allow.loss", "warn.loss", "no.loss"), row.names, 
#>     col.names, as.is = !stringsAsFactors, na.strings = "NA", 
#>     colClasses = NA, nrows = -1, skip = 0, check.names = TRUE, 
#>     fill = !blank.lines.skip, strip.white = FALSE, blank.lines.skip = TRUE, 
#>     comment.char = "#", allowEscapes = FALSE, flush = FALSE, 
#>     stringsAsFactors = FALSE, fileEncoding = "", encoding = "unknown", 
#>     text, skipNul = FALSE) 
#> {
#>     if (missing(file) && !missing(text)) {
#>         file <- textConnection(text, encoding = "UTF-8")
#>         encoding <- "UTF-8"
#>         on.exit(close(file))
#>     }
#>     if (is.character(file)) {
#>         file <- if (nzchar(fileEncoding)) 
#>             file(file, "rt", encoding = fileEncoding)
#>         else file(file, "rt")
#>         on.exit(close(file))
#>     }
#>     if (!inherits(file, "connection")) 
#>         stop("'file' must be a character string or connection")
#>     if (!isOpen(file, "rt")) {
#>         open(file, "rt")
#>         on.exit(close(file))
#>     }
#>     pbEncoding <- if (encoding %in% c("", "bytes", "UTF-8")) 
#>         encoding
#>     else "bytes"
#>     numerals <- match.arg(numerals)
#>     if (skip > 0L) 
#>         readLines(file, skip)
#>     nlines <- n0lines <- if (nrows < 0L) 
#>         5
#>     else min(5L, (header + nrows))
#>     lines <- .External(C_readtablehead, file, nlines, comment.char, 
#>         blank.lines.skip, quote, sep, skipNul)
#>     if (encoding %in% c("UTF-8", "latin1")) 
#>         Encoding(lines) <- encoding
#>     nlines <- length(lines)
#>     if (!nlines) {
#>         if (missing(col.names)) 
#>             stop("no lines available in input")
#>         rlabp <- FALSE
#>         cols <- length(col.names)
#>     }
#>     else {
#>         if (all(!nzchar(lines))) 
#>             stop("empty beginning of file")
#>         if (nlines < n0lines && file == 0L) {
#>             pushBack(c(lines, lines, ""), file, encoding = pbEncoding)
#>             on.exit((clearPushBack(stdin())))
#>         }
#>         else pushBack(c(lines, lines), file, encoding = pbEncoding)
#>         first <- scan(file, what = "", sep = sep, quote = quote, 
#>             nlines = 1, quiet = TRUE, skip = 0, strip.white = TRUE, 
#>             blank.lines.skip = blank.lines.skip, na.strings = character(0), 
#>             comment.char = comment.char, allowEscapes = allowEscapes, 
#>             encoding = encoding, skipNul = skipNul)
#>         col1 <- if (missing(col.names)) 
#>             length(first)
#>         else length(col.names)
#>         col <- numeric(nlines - 1L)
#>         if (nlines > 1L) 
#>             for (i in seq_along(col)) col[i] <- length(scan(file, 
#>                 what = "", sep = sep, quote = quote, nlines = 1, 
#>                 quiet = TRUE, skip = 0, strip.white = strip.white, 
#>                 blank.lines.skip = blank.lines.skip, comment.char = comment.char, 
#>                 allowEscapes = allowEscapes, encoding = encoding, 
#>                 skipNul = skipNul))
#>         cols <- max(col1, col)
#>         rlabp <- (cols - col1) == 1L
#>         if (rlabp && missing(header)) 
#>             header <- TRUE
#>         if (!header) 
#>             rlabp <- FALSE
#>         if (header) {
#>             .External(C_readtablehead, file, 1L, comment.char, 
#>                 blank.lines.skip, quote, sep, skipNul)
#>             if (missing(col.names)) 
#>                 col.names <- first
#>             else if (length(first) != length(col.names)) 
#>                 warning("header and 'col.names' are of different lengths")
#>         }
#>         else if (missing(col.names)) 
#>             col.names <- paste0("V", 1L:cols)
#>         if (length(col.names) + rlabp < cols) 
#>             stop("more columns than column names")
#>         if (fill && length(col.names) > cols) 
#>             cols <- length(col.names)
#>         if (!fill && cols > 0L && length(col.names) > cols) 
#>             stop("more column names than columns")
#>         if (cols == 0L) 
#>             stop("first five rows are empty: giving up")
#>     }
#>     if (check.names) 
#>         col.names <- make.names(col.names, unique = TRUE)
#>     if (rlabp) 
#>         col.names <- c("row.names", col.names)
#>     nmColClasses <- names(colClasses)
#>     if (is.null(nmColClasses)) {
#>         if (length(colClasses) < cols) 
#>             colClasses <- rep_len(colClasses, cols)
#>     }
#>     else {
#>         tmp <- rep_len(NA_character_, cols)
#>         names(tmp) <- col.names
#>         i <- match(nmColClasses, col.names, 0L)
#>         if (any(i <= 0L)) 
#>             warning("not all columns named in 'colClasses' exist")
#>         tmp[i[i > 0L]] <- colClasses[i > 0L]
#>         colClasses <- tmp
#>     }
#>     what <- rep.int(list(""), cols)
#>     names(what) <- col.names
#>     colClasses[colClasses %in% c("real", "double")] <- "numeric"
#>     known <- colClasses %in% c("logical", "integer", "numeric", 
#>         "complex", "character", "raw")
#>     what[known] <- lapply(colClasses[known], do.call, list(0))
#>     what[colClasses %in% "NULL"] <- list(NULL)
#>     keep <- !sapply(what, is.null)
#>     data <- scan(file = file, what = what, sep = sep, quote = quote, 
#>         dec = dec, nmax = nrows, skip = 0, na.strings = na.strings, 
#>         quiet = TRUE, fill = fill, strip.white = strip.white, 
#>         blank.lines.skip = blank.lines.skip, multi.line = FALSE, 
#>         comment.char = comment.char, allowEscapes = allowEscapes, 
#>         flush = flush, encoding = encoding, skipNul = skipNul)
#>     nlines <- length(data[[which.max(keep)]])
#>     if (cols != length(data)) {
#>         warning("cols = ", cols, " != length(data) = ", length(data), 
#>             domain = NA)
#>         cols <- length(data)
#>     }
#>     if (is.logical(as.is)) {
#>         as.is <- rep_len(as.is, cols)
#>     }
#>     else if (is.numeric(as.is)) {
#>         if (any(as.is < 1 | as.is > cols)) 
#>             stop("invalid numeric 'as.is' expression")
#>         i <- rep.int(FALSE, cols)
#>         i[as.is] <- TRUE
#>         as.is <- i
#>     }
#>     else if (is.character(as.is)) {
#>         i <- match(as.is, col.names, 0L)
#>         if (any(i <= 0L)) 
#>             warning("not all columns named in 'as.is' exist")
#>         i <- i[i > 0L]
#>         as.is <- rep.int(FALSE, cols)
#>         as.is[i] <- TRUE
#>     }
#>     else if (length(as.is) != cols) 
#>         stop(gettextf("'as.is' has the wrong length %d  != cols = %d", 
#>             length(as.is), cols), domain = NA)
#>     do <- keep & !known
#>     if (rlabp) 
#>         do[1L] <- FALSE
#>     for (i in (1L:cols)[do]) {
#>         data[[i]] <- if (is.na(colClasses[i])) 
#>             type.convert(data[[i]], as.is = as.is[i], dec = dec, 
#>                 numerals = numerals, na.strings = character(0L))
#>         else if (colClasses[i] == "factor") 
#>             as.factor(data[[i]])
#>         else if (colClasses[i] == "Date") 
#>             as.Date(data[[i]])
#>         else if (colClasses[i] == "POSIXct") 
#>             as.POSIXct(data[[i]])
#>         else methods::as(data[[i]], colClasses[i])
#>     }
#>     compactRN <- TRUE
#>     if (missing(row.names)) {
#>         if (rlabp) {
#>             row.names <- data[[1L]]
#>             data <- data[-1L]
#>             keep <- keep[-1L]
#>             compactRN <- FALSE
#>         }
#>         else row.names <- .set_row_names(as.integer(nlines))
#>     }
#>     else if (is.null(row.names)) {
#>         row.names <- .set_row_names(as.integer(nlines))
#>     }
#>     else if (is.character(row.names)) {
#>         compactRN <- FALSE
#>         if (length(row.names) == 1L) {
#>             rowvar <- (1L:cols)[match(col.names, row.names, 0L) == 
#>                 1L]
#>             row.names <- data[[rowvar]]
#>             data <- data[-rowvar]
#>             keep <- keep[-rowvar]
#>         }
#>     }
#>     else if (is.numeric(row.names) && length(row.names) == 1L) {
#>         compactRN <- FALSE
#>         rlabp <- row.names
#>         row.names <- data[[rlabp]]
#>         data <- data[-rlabp]
#>         keep <- keep[-rlabp]
#>     }
#>     else stop("invalid 'row.names' specification")
#>     data <- data[keep]
#>     if (is.object(row.names) || !(is.integer(row.names))) 
#>         row.names <- as.character(row.names)
#>     if (!compactRN) {
#>         if (length(row.names) != nlines) 
#>             stop("invalid 'row.names' length")
#>         if (anyDuplicated(row.names)) 
#>             stop("duplicate 'row.names' are not allowed")
#>         if (anyNA(row.names)) 
#>             stop("missing values in 'row.names' are not allowed")
#>     }
#>     class(data) <- "data.frame"
#>     attr(data, "row.names") <- row.names
#>     data
#> }
#> <bytecode: 0x55b977dfca68>
#> <environment: namespace:utils>
#> --- 
#>  
#> ## registry
#> <environment: 0x55b9747e8268>
#> attr(,"class")
#> [1] "proto"       "environment"
#> --- 
#>  
#> ## rule_result
#> function(applied = FALSE, value = NULL) {
#>   structure(list(applied = applied, value = value), class = "rule_result")
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## save_resource
#> function(res, encoding, dest) {
#>   if (headers(res)[["content-type"]] == "application/octet-stream" ||
#>     headers(res)[["content-type"]] == "application/x-zip-compressed") {
#>     bin <- content(res, as = "raw")
#>     writeBin(bin, dest)
#>   } else {
#>     text <- content(res, as = "text", encoding = encoding)
#>     writeLines(text, dest, useBytes = TRUE)
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## select
#> function (.data, ...) 
#> {
#>     UseMethod("select")
#> }
#> <bytecode: 0x55b96aa73e00>
#> <environment: namespace:dplyr>
#> --- 
#>  
#> ## settlement_prices_download
#> function(., dest, ...) {
#>   params <- list(...)
#>   if (is.null(params$refdate)) {
#>     msg <- "refdate argument not provided - download can't be done"
#>     alert("danger", msg)
#>     return(FALSE)
#>   }
#>   strdate <- format(as.Date(params$refdate), "%d/%m/%Y")
#>   res <- POST(.$downloader$url,
#>     body = list(dData1 = strdate),
#>     encode = "form"
#>   )
#>   if (status_code(res) != 200) {
#>     return(FALSE)
#>   }
#>   enc <- if (is.null(.$downloader$encoding)) "utf8" else .$downloader$encoding
#>   save_resource(res, enc, dest)
#>   TRUE
#> }
#> <bytecode: 0x55b971be8a60>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## settlement_prices_read
#> function(., filename, parse_fields = TRUE) {
#>   doc <- read_html(filename)
#>   xpath <- "//table[contains(@id, 'tblDadosAjustes')]"
#>   table <- html_element(doc, xpath = xpath)
#>   if (is(table, "xml_node")) {
#>     df <- html_table(table)
#>   } else {
#>     return(NULL)
#>   }
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## show_templates
#> function() {
#>   ui <- miniUI::miniPage(
#>     miniUI::miniTitleBar("rb3 Templates"),
#>     miniUI::miniContentPanel(
#>       DT::dataTableOutput("tableOutput")
#>     )
#>   )
#> 
#>   server <- function(input, output, session) {
#>     output$tableOutput <- DT::renderDataTable({
#>       df <- MarketData$show_templates()
#>       DT::datatable(df,
#>         selection = "none",
#>         options = list(paging = FALSE)
#>       )
#>     })
#>   }
#> 
#>   app <- shiny::shinyApp(ui = ui, server = server)
#>   viewer <- shiny::dialogViewer("rb3 Templates", width = 1200, height = 900)
#> 
#>   shiny::runGadget(app, viewer = viewer, stopOnCancel = TRUE)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## simple_download
#> function(., dest, ...) {
#>   enc <- if (is.null(.$downloader$encoding)) "utf8" else .$downloader$encoding
#>   just_download_data(.$downloader$url, enc, dest)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## single_futures_get
#> function(idx_date,
#>                                date_vec,
#>                                cache_folder = cachedir(),
#>                                do_cache = TRUE) {
#>   tpl <- "AjustesDiarios"
#>   refdate <- date_vec[idx_date]
#>   fname <- download_marketdata(tpl, cache_folder, do_cache, refdate = refdate)
#>   if (!is.null(fname)) {
#>     df <- read_marketdata(fname, tpl, TRUE, do_cache)
#>     if (!is.null(df)) {
#>       tibble(
#>         refdate = as.Date(refdate),
#>         commodity = flatten_names(df$mercadoria),
#>         maturity_code = df$vencimento,
#>         symbol = paste0(.data$commodity, .data$maturity_code),
#>         price_previous = df$pu_anterior,
#>         price = df$pu_atual,
#>         change = df$variacao,
#>         settlement_value = df$ajuste
#>       )
#>     } else {
#>       NULL
#>     }
#>   } else {
#>     alert("danger", "Failed download")
#>     return(NULL)
#>   }
#> }
#> <bytecode: 0x55b97c44ee30>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## single_index_get
#> function(index_name, year, cache_folder, do_cache) {
#>   template <- "GetPortfolioDay_IndexStatistics"
#>   f <- download_marketdata(template,
#>     index_name = index_name, year = year,
#>     cache_folder = cache_folder, do_cache = do_cache
#>   )
#>   index_data <- read_marketdata(f, template, do_cache = do_cache)
#> 
#>   if (is.null(index_data)) {
#>     return(NULL)
#>   }
#> 
#>   index_data <- pivot_longer(index_data$Results, .data$month01:.data$month12,
#>     names_to = "month"
#>   ) |>
#>     mutate(
#>       month = str_match(.data$month, "\\d\\d$") |> as.integer(),
#>       year = year,
#>       refdate = ISOdate(.data$year, .data$month, .data$day) |> as.Date(),
#>       index_name = index_name
#>     ) |>
#>     filter(!is.na(.data$value)) |>
#>     arrange(.data$refdate)
#> 
#>   index_data |> select(.data$refdate, .data$index_name, .data$value)
#> }
#> <bytecode: 0x55b979fb9368>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## slot
#> function (object, name) 
#> .Call(C_R_get_slot, object, name)
#> <bytecode: 0x55b9701b1b28>
#> <environment: namespace:methods>
#> --- 
#>  
#> ## status_code
#> function (x) 
#> UseMethod("status_code")
#> <bytecode: 0x55b96c737c00>
#> <environment: namespace:httr>
#> --- 
#>  
#> ## stock_indexes_composition_download
#> function(., dest, ...) {
#>   url_encoded_download(., dest,
#>     pageNumber = 1,
#>     pageSize = 9999
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## stock_indexes_composition_reader
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   if (is.null(jason$results)) {
#>     return(NULL)
#>   }
#>   df <- jason$results
#>   df[["update"]] <- jason$header$update
#>   df[["start_month"]] <- jason$header$startMonth
#>   df[["end_month"]] <- jason$header$endMonth
#>   df[["year"]] <- jason$header$year
#>   colnames(df) <- .$colnames
#>   if (parse_fields) {
#>     parse_columns(df, .$colnames, .$handlers, .$.parser())
#>   } else {
#>     df
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## stock_indexes_current_portfolio_download
#> function(., dest, ...) {
#>   if (!check_parameters(..., arg_name = "index_name")) {
#>     return(FALSE)
#>   }
#>   args <- list(...)
#>   segment <- 2
#>   if (hasName(args, "segment")) {
#>     segment <- args$segment
#>   }
#>   url_encoded_download(., dest,
#>     pageNumber = 1,
#>     pageSize = 9999,
#>     language = "pt-br",
#>     index = args$index_name,
#>     segment = segment
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## stock_indexes_json_reader
#> function(., filename, parse_fields = TRUE) {
#>   jason <- fromJSON(filename)
#>   l <- list()
#>   for (part_name in names(.$parts)) {
#>     part <- .$parts[[part_name]]
#>     if (is.null(jason[[part$name]])) {
#>       return(NULL)
#>     }
#>     df <- as.data.frame(jason[[part$name]])
#>     colnames(df) <- part$colnames
#>     l[[part_name]] <- if (parse_fields) {
#>       parse_columns(df, part$colnames, part$handlers, .$.parser())
#>     } else {
#>       df
#>     }
#>   }
#>   class(l) <- "parts"
#>   l
#> }
#> <bytecode: 0x55b971c3de48>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## stock_indexes_statistics_download
#> function(., dest, ...) {
#>   if (!check_parameters(..., arg_name = "index_name")) {
#>     return(FALSE)
#>   }
#>   if (!check_parameters(..., arg_name = "year")) {
#>     return(FALSE)
#>   }
#>   args <- list(...)
#>   url_encoded_download(., dest,
#>     language = "pt-br",
#>     index = args$index_name,
#>     year = args$year
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## stock_indexes_theo_portfolio_download
#> function(., dest, ...) {
#>   if (!check_parameters(..., arg_name = "index_name")) {
#>     return(FALSE)
#>   }
#>   args <- list(...)
#>   url_encoded_download(., dest,
#>     pageNumber = 1,
#>     pageSize = 9999,
#>     language = "pt-br",
#>     index = args$index_name
#>   )
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## str_c
#> function (..., sep = "", collapse = NULL) 
#> {
#>     stri_c(..., sep = sep, collapse = collapse, ignore_null = TRUE)
#> }
#> <bytecode: 0x55b974740680>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_detect
#> function (string, pattern, negate = FALSE) 
#> {
#>     switch(type(pattern), empty = , bound = str_count(string, 
#>         pattern) > 0 & !negate, fixed = stri_detect_fixed(string, 
#>         pattern, negate = negate, opts_fixed = opts(pattern)), 
#>         coll = stri_detect_coll(string, pattern, negate = negate, 
#>             opts_collator = opts(pattern)), regex = stri_detect_regex(string, 
#>             pattern, negate = negate, opts_regex = opts(pattern)))
#> }
#> <bytecode: 0x55b976234638>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_ends
#> function (string, pattern, negate = FALSE) 
#> {
#>     switch(type(pattern), empty = , bound = stop("boundary() patterns are not supported."), 
#>         fixed = stri_endswith_fixed(string, pattern, negate = negate, 
#>             opts_fixed = opts(pattern)), coll = stri_endswith_coll(string, 
#>             pattern, negate = negate, opts_collator = opts(pattern)), 
#>         regex = {
#>             pattern2 <- paste0(pattern, "$")
#>             attributes(pattern2) <- attributes(pattern)
#>             str_detect(string, pattern2, negate)
#>         })
#> }
#> <bytecode: 0x55b97bd11ad0>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_glue
#> function (..., .sep = "", .envir = parent.frame()) 
#> {
#>     glue::glue(..., .sep = .sep, .envir = .envir)
#> }
#> <bytecode: 0x55b97bb962c0>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_length
#> function (string) 
#> {
#>     stri_length(string)
#> }
#> <bytecode: 0x55b97bd13c58>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_match
#> function (string, pattern) 
#> {
#>     if (type(pattern) != "regex") {
#>         stop("Can only match regular expressions", call. = FALSE)
#>     }
#>     stri_match_first_regex(string, pattern, opts_regex = opts(pattern))
#> }
#> <bytecode: 0x55b974802310>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_pad
#> function (string, width, side = c("left", "right", "both"), pad = " ") 
#> {
#>     side <- match.arg(side)
#>     switch(side, left = stri_pad_left(string, width, pad = pad), 
#>         right = stri_pad_right(string, width, pad = pad), both = stri_pad_both(string, 
#>             width, pad = pad))
#> }
#> <bytecode: 0x55b9747cecf0>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_replace
#> function (string, pattern, replacement) 
#> {
#>     if (!missing(replacement) && is.function(replacement)) {
#>         return(str_transform(string, pattern, replacement))
#>     }
#>     switch(type(pattern), empty = stop("Empty `pattern` not supported", 
#>         call. = FALSE), bound = stop("Boundary `pattern` not supported", 
#>         call. = FALSE), fixed = stri_replace_first_fixed(string, 
#>         pattern, replacement, opts_fixed = opts(pattern)), coll = stri_replace_first_coll(string, 
#>         pattern, replacement, opts_collator = opts(pattern)), 
#>         regex = stri_replace_first_regex(string, pattern, fix_replacement(replacement), 
#>             opts_regex = opts(pattern)))
#> }
#> <bytecode: 0x55b97bc68f08>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_replace_all
#> function (string, pattern, replacement) 
#> {
#>     if (!missing(replacement) && is.function(replacement)) {
#>         return(str_transform_all(string, pattern, replacement))
#>     }
#>     if (!is.null(names(pattern))) {
#>         vec <- FALSE
#>         replacement <- unname(pattern)
#>         pattern[] <- names(pattern)
#>     }
#>     else {
#>         vec <- TRUE
#>     }
#>     switch(type(pattern), empty = stop("Empty `pattern`` not supported", 
#>         call. = FALSE), bound = stop("Boundary `pattern` not supported", 
#>         call. = FALSE), fixed = stri_replace_all_fixed(string, 
#>         pattern, replacement, vectorize_all = vec, opts_fixed = opts(pattern)), 
#>         coll = stri_replace_all_coll(string, pattern, replacement, 
#>             vectorize_all = vec, opts_collator = opts(pattern)), 
#>         regex = stri_replace_all_regex(string, pattern, fix_replacement(replacement), 
#>             vectorize_all = vec, opts_regex = opts(pattern)))
#> }
#> <bytecode: 0x55b978595c58>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_split
#> function (string, pattern, n = Inf, simplify = FALSE) 
#> {
#>     if (identical(n, Inf)) 
#>         n <- -1L
#>     switch(type(pattern), empty = stri_split_boundaries(string, 
#>         n = n, simplify = simplify, opts_brkiter = opts(pattern)), 
#>         bound = stri_split_boundaries(string, n = n, simplify = simplify, 
#>             opts_brkiter = opts(pattern)), fixed = stri_split_fixed(string, 
#>             pattern, n = n, simplify = simplify, opts_fixed = opts(pattern)), 
#>         regex = stri_split_regex(string, pattern, n = n, simplify = simplify, 
#>             opts_regex = opts(pattern)), coll = stri_split_coll(string, 
#>             pattern, n = n, simplify = simplify, opts_collator = opts(pattern)))
#> }
#> <bytecode: 0x55b9769a40c8>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_starts
#> function (string, pattern, negate = FALSE) 
#> {
#>     switch(type(pattern), empty = , bound = stop("boundary() patterns are not supported."), 
#>         fixed = stri_startswith_fixed(string, pattern, negate = negate, 
#>             opts_fixed = opts(pattern)), coll = stri_startswith_coll(string, 
#>             pattern, negate = negate, opts_collator = opts(pattern)), 
#>         regex = {
#>             pattern2 <- paste0("^", pattern)
#>             attributes(pattern2) <- attributes(pattern)
#>             str_detect(string, pattern2, negate)
#>         })
#> }
#> <bytecode: 0x55b97bc67d40>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_sub
#> function (string, start = 1L, end = -1L) 
#> {
#>     if (is.matrix(start)) {
#>         stri_sub(string, from = start)
#>     }
#>     else {
#>         stri_sub(string, from = start, to = end)
#>     }
#> }
#> <bytecode: 0x55b976d4b6b8>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_to_lower
#> function (string, locale = "en") 
#> {
#>     stri_trans_tolower(string, locale = locale)
#> }
#> <bytecode: 0x55b9764cf2e0>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## str_trim
#> function (string, side = c("both", "left", "right")) 
#> {
#>     side <- match.arg(side)
#>     switch(side, left = stri_trim_left(string), right = stri_trim_right(string), 
#>         both = stri_trim_both(string))
#> }
#> <bytecode: 0x55b96d043858>
#> <environment: namespace:stringr>
#> --- 
#>  
#> ## system.file
#> function (..., package = "base", lib.loc = NULL, mustWork = FALSE) 
#> {
#>     if (nargs() == 0L) 
#>         return(file.path(.Library, "base"))
#>     if (length(package) != 1L) 
#>         stop("'package' must be of length 1")
#>     packagePath <- find.package(package, lib.loc, quiet = TRUE)
#>     ans <- if (length(packagePath)) {
#>         FILES <- file.path(packagePath, ...)
#>         present <- file.exists(FILES)
#>         if (any(present)) 
#>             FILES[present]
#>         else ""
#>     }
#>     else ""
#>     if (mustWork && identical(ans, "")) 
#>         stop("no file found")
#>     ans
#> }
#> <bytecode: 0x55b9688146a0>
#> <environment: namespace:base>
#> --- 
#>  
#> ## take
#> function(x, ...) {
#>   UseMethod("take", x)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## take.list
#> function(x, k, ...) {
#>   map_chr(x, function(x) {
#>     v <- x[[k]]
#>     if (is.null(v)) {
#>       NA
#>     } else {
#>       v
#>     }
#>   })
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## tibble
#> function (..., .rows = NULL, .name_repair = c("check_unique", 
#>     "unique", "universal", "minimal")) 
#> {
#>     xs <- quos(...)
#>     tibble_quos(xs, .rows, .name_repair)
#> }
#> <bytecode: 0x55b96f8c6740>
#> <environment: namespace:tibble>
#> --- 
#>  
#> ## to_date
#> function(format = "%Y-%m-%d") {
#>   function(x, ...) as.Date(strptime(x, format))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_date_handler
#> function(format = NULL) {
#>   if (is.null(format)) {
#>     format <- "%Y-%m-%d"
#>   }
#>   handler <- function(x) {
#>     as.Date(x, format = format)
#>   }
#>   attr(handler, "format") <- format
#>   attr(handler, "type") <- "Date"
#>   class(handler) <- c("function", "handler")
#>   handler
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_datetime
#> function(format = "%Y-%m-%d %H:%M:%S") {
#>   function(x, ...) as.POSIXct(strptime(x, format))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_dbl
#> function(dec = NULL, thousands = NULL, percent = FALSE) {
#>   .func <- identity
#>   .mult <- 1
#>   if (percent) {
#>     .func <- composite(function(x) sub("\\s*%", "", x), .func)
#>     .mult <- 0.01
#>   }
#>   if (!is.null(dec)) {
#>     .func <- composite(function(x) sub(dec, ".", x, fixed = TRUE), .func)
#>   }
#>   if (!is.null(thousands)) {
#>     .func <- composite(function(x) gsub(thousands, "", x, fixed = TRUE), .func)
#>   }
#>   function(x, ...) as.numeric(.func(x)) * .mult
#> }
#> <bytecode: 0x55b97315d3c0>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_factor_handler
#> function(levels = NULL, labels = levels) {
#>   handler <- function(x) {
#>     if (is.null(levels)) {
#>       factor(x)
#>     } else {
#>       factor(x, levels = levels, labels = labels)
#>     }
#>   }
#>   attr(handler, "levels") <- levels
#>   attr(handler, "labels") <- labels
#>   attr(handler, "type") <- "factor"
#>   class(handler) <- c("function", "handler")
#>   handler
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_int
#> function() {
#>   as.integer
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_numeric_handler
#> function(dec = 0, sign = "") {
#>   handler <- function(x) {
#>     if (is(dec, "character")) {
#>       dec <- get(dec, envir = parent.frame())
#>     }
#>     if (!sign %in% c("+", "-", "")) {
#>       sign <- get(sign, envir = parent.frame())
#>     }
#>     x <- paste0(sign, x)
#>     as.numeric(x) / (10^as.numeric(dec))
#>   }
#>   attr(handler, "dec") <- dec
#>   attr(handler, "sign") <- sign
#>   attr(handler, "type") <- "numeric"
#>   class(handler) <- c("function", "handler")
#>   handler
#> }
#> <bytecode: 0x55b97c7f37d8>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_strtime_handler
#> function(format = NULL, tz = NULL) {
#>   if (is.null(format)) {
#>     format <- "%H%M%OS"
#>   }
#>   if (is.null(tz)) {
#>     tz <- "GMT"
#>   }
#>   handler <- function(x) {
#>     z <- str_pad(x, 9, pad = "0") |> str_match("(\\d{6})(\\d{3})")
#>     t <- str_c(z[, 2], ".", z[, 3])
#>     strptime(t, format = format, tz = tz)
#>   }
#>   attr(handler, "format") <- format
#>   attr(handler, "type") <- "strtime"
#>   class(handler) <- c("function", "handler")
#>   handler
#> }
#> <bytecode: 0x55b978f1e378>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## to_time_handler
#> function(format = NULL) {
#>   if (is.null(format)) {
#>     format <- "%H:%M:%S"
#>   }
#>   handler <- function(x) {
#>     strptime(x, format = format)
#>   }
#>   attr(handler, "format") <- format
#>   attr(handler, "type") <- "POSIXct"
#>   class(handler) <- c("function", "handler")
#>   handler
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## toJSON
#> function (x, dataframe = c("rows", "columns", "values"), matrix = c("rowmajor", 
#>     "columnmajor"), Date = c("ISO8601", "epoch"), POSIXt = c("string", 
#>     "ISO8601", "epoch", "mongo"), factor = c("string", "integer"), 
#>     complex = c("string", "list"), raw = c("base64", "hex", "mongo", 
#>         "int", "js"), null = c("list", "null"), na = c("null", 
#>         "string"), auto_unbox = FALSE, digits = 4, pretty = FALSE, 
#>     force = FALSE, ...) 
#> {
#>     dataframe <- match.arg(dataframe)
#>     matrix <- match.arg(matrix)
#>     Date <- match.arg(Date)
#>     POSIXt <- match.arg(POSIXt)
#>     factor <- match.arg(factor)
#>     complex <- match.arg(complex)
#>     raw <- match.arg(raw)
#>     null <- match.arg(null)
#>     x <- force(x)
#>     if (!missing(na)) {
#>         na <- match.arg(na)
#>     }
#>     else {
#>         na <- NULL
#>     }
#>     indent <- if (isTRUE(pretty)) 
#>         0L
#>     else NA_integer_
#>     ans <- asJSON(x, dataframe = dataframe, Date = Date, POSIXt = POSIXt, 
#>         factor = factor, complex = complex, raw = raw, matrix = matrix, 
#>         auto_unbox = auto_unbox, digits = digits, na = na, null = null, 
#>         force = force, indent = indent, ...)
#>     if (is.numeric(pretty)) {
#>         prettify(ans, pretty)
#>     }
#>     else {
#>         class(ans) <- "json"
#>         return(ans)
#>     }
#> }
#> <bytecode: 0x55b97c2c6410>
#> <environment: namespace:jsonlite>
#> --- 
#>  
#> ## transmute_regex
#> function(.x, .r, .f, apply_to = c("any", "all")) {
#>   trm <- transmuter(match_regex(.r, .f, apply_to = apply_to))
#>   parse_text(trm, .x)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## transmuter
#> function(...) {
#>   objs <- list(...)
#> 
#>   idx <- map_lgl(objs, function(x) is(x, "match_rule"))
#>   rules <- objs[idx]
#> 
#>   idx <- map_lgl(objs, function(x) is(x, "Transmuter"))
#>   parents <- objs[idx]
#>   for (parent in parents) {
#>     rules <- append(rules, slot(parent, "rules"))
#>   }
#> 
#>   new("Transmuter", envir = new.env(), rules = rules)
#> }
#> <bytecode: 0x55b973abb200>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## trim_fields
#> function(x) {
#>   fields <- lapply(x, function(z) {
#>     if (is(z, "character")) {
#>       str_trim(z)
#>     } else {
#>       z
#>     }
#>   })
#>   do.call("data.frame", c(fields,
#>     stringsAsFactors = FALSE,
#>     check.names = FALSE
#>   ))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## unfactor
#> function(x) {
#>   .unformat(x, function(x) {
#>     if (is.factor(x)) {
#>       as.character(x)
#>     } else {
#>       x
#>     }
#>   })
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## unformat
#> function(x) .unformat(x, as.character)
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## unzip
#> function (zipfile, files = NULL, list = FALSE, overwrite = TRUE, 
#>     junkpaths = FALSE, exdir = ".", unzip = "internal", setTimes = FALSE) 
#> {
#>     if (identical(unzip, "internal")) {
#>         if (!list && !missing(exdir)) 
#>             dir.create(exdir, showWarnings = FALSE, recursive = TRUE)
#>         res <- .External(C_unzip, zipfile, files, exdir, list, 
#>             overwrite, junkpaths, setTimes)
#>         if (list) {
#>             dates <- as.POSIXct(res[[3]], "%Y-%m-%d %H:%M", tz = "UTC")
#>             data.frame(Name = res[[1]], Length = res[[2]], Date = dates, 
#>                 stringsAsFactors = FALSE)
#>         }
#>         else invisible(attr(res, "extracted"))
#>     }
#>     else {
#>         WINDOWS <- .Platform$OS.type == "windows"
#>         if (!is.character(unzip) || length(unzip) != 1L || !nzchar(unzip)) 
#>             stop("'unzip' must be a single character string")
#>         zipfile <- path.expand(zipfile)
#>         if (list) {
#>             res <- if (WINDOWS) 
#>                 system2(unzip, c("-ql", shQuote(zipfile)), stdout = TRUE)
#>             else system2(unzip, c("-ql", shQuote(zipfile)), stdout = TRUE, 
#>                 env = c("TZ=UTC"))
#>             l <- length(res)
#>             res2 <- res[-c(2, l - 1, l)]
#>             res3 <- gsub(" *([^ ]+) +([^ ]+) +([^ ]+) +(.*)", 
#>                 "\\1 \\2 \\3 \"\\4\"", res2)
#>             con <- textConnection(res3)
#>             on.exit(close(con))
#>             z <- read.table(con, header = TRUE, as.is = TRUE)
#>             dt <- paste(z$Date, z$Time)
#>             formats <- if (max(nchar(z$Date) > 8)) 
#>                 c("%Y-%m-%d", "%d-%m-%Y", "%m-%d-%Y")
#>             else c("%m-%d-%y", "%d-%m-%y", "%y-%m-%d")
#>             slash <- any(grepl("/", z$Date))
#>             if (slash) 
#>                 formats <- gsub("-", "/", formats, fixed = TRUE)
#>             formats <- paste(formats, "%H:%M")
#>             for (f in formats) {
#>                 zz <- as.POSIXct(dt, tz = "UTC", format = f)
#>                 if (all(!is.na(zz))) 
#>                   break
#>             }
#>             z[, "Date"] <- zz
#>             z[c("Name", "Length", "Date")]
#>         }
#>         else {
#>             args <- character()
#>             if (junkpaths) 
#>                 args <- c(args, "-j")
#>             if (overwrite) 
#>                 args <- c(args, "-oq", shQuote(zipfile))
#>             else args <- c(args, "-nq", shQuote(zipfile))
#>             if (length(files)) 
#>                 args <- c(args, shQuote(files))
#>             if (exdir != ".") 
#>                 args <- c(args, "-d", shQuote(exdir))
#>             if (WINDOWS) 
#>                 system2(unzip, args, stdout = NULL, stderr = NULL, 
#>                   invisible = TRUE)
#>             else system2(unzip, args, stdout = NULL, stderr = NULL)
#>             invisible(NULL)
#>         }
#>     }
#> }
#> <bytecode: 0x55b9798e9bb0>
#> <environment: namespace:utils>
#> --- 
#>  
#> ## unzip_recursive
#> function(fname) {
#>   if (length(fname) == 1 &&
#>     str_ends(str_to_lower(fname), ".zip")) {
#>     exdir <- str_replace(fname, "\\.zip$", "")
#>     l <- unzip(fname, exdir = exdir)
#>     unzip_recursive(l)
#>   } else {
#>     fname
#>   }
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## url_encoded_download
#> function(., dest, ...) {
#>   args <- list(...)
#>   params <- toJSON(args, auto_unbox = TRUE)
#>   params_enc <- base64encode(charToRaw(params))
#>   url <- parse_url(.$downloader$url)
#>   url$path <- c(url$path, params_enc)
#>   res <- GET(url)
#>   if (status_code(res) != 200) {
#>     return(FALSE)
#>   }
#>   enc <- if (is.null(.$downloader$encoding)) "utf8" else .$downloader$encoding
#>   save_resource(res, enc, dest)
#>   TRUE
#> }
#> <bytecode: 0x55b97d8b0bf8>
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## width
#> function(x) {
#>   x <- as.numeric(x)
#>   class(x) <- c("numeric", "width")
#>   x
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## write_rds
#> function (x, file, compress = c("none", "gz", "bz2", "xz"), version = 2, 
#>     refhook = NULL, text = FALSE, path = deprecated(), ...) 
#> {
#>     if (is_present(path)) {
#>         deprecate_warn("1.4.0", "write_rds(path = )", "write_rds(file = )")
#>         file <- path
#>     }
#>     compress <- match.arg(compress)
#>     con <- switch(compress, none = file(file, ...), gz = gzfile(file, 
#>         ...), bz2 = bzfile(file, ...), xz = xzfile(file, ...))
#>     on.exit(close(con), add = TRUE)
#>     saveRDS(x, con, version = version, refhook = refhook, ascii = text)
#>     invisible(x)
#> }
#> <bytecode: 0x55b97199d020>
#> <environment: namespace:readr>
#> --- 
#>  
#> ## write.table
#> function (x, file = "", append = FALSE, quote = TRUE, sep = " ", 
#>     eol = "\n", na = "NA", dec = ".", row.names = TRUE, col.names = TRUE, 
#>     qmethod = c("escape", "double"), fileEncoding = "") 
#> {
#>     qmethod <- match.arg(qmethod)
#>     if (is.logical(quote) && (length(quote) != 1L || is.na(quote))) 
#>         stop("'quote' must be 'TRUE', 'FALSE' or numeric")
#>     quoteC <- if (is.logical(quote)) 
#>         quote
#>     else TRUE
#>     qset <- is.logical(quote) && quote
#>     if (!is.data.frame(x) && !is.matrix(x)) 
#>         x <- data.frame(x)
#>     makeRownames <- isTRUE(row.names)
#>     makeColnames <- is.logical(col.names) && !identical(FALSE, 
#>         col.names)
#>     if (is.matrix(x)) {
#>         p <- ncol(x)
#>         d <- dimnames(x)
#>         if (is.null(d)) 
#>             d <- list(NULL, NULL)
#>         if (is.null(d[[1L]]) && makeRownames) 
#>             d[[1L]] <- seq_len(nrow(x))
#>         if (is.null(d[[2L]]) && makeColnames && p > 0L) 
#>             d[[2L]] <- paste0("V", 1L:p)
#>         if (qset) 
#>             quote <- if (is.character(x)) 
#>                 seq_len(p)
#>             else numeric()
#>     }
#>     else {
#>         if (qset) 
#>             quote <- if (length(x)) 
#>                 which(unlist(lapply(x, function(x) is.character(x) || 
#>                   is.factor(x))))
#>             else numeric()
#>         if (any(vapply(x, function(z) length(dim(z)) == 2 && 
#>             dim(z)[2L] > 1, NA))) {
#>             c1 <- names(x)
#>             x <- as.matrix(x, rownames.force = makeRownames)
#>             d <- dimnames(x)
#>             if (qset) {
#>                 ord <- match(c1, d[[2L]], 0L)
#>                 quote <- ord[quote]
#>                 quote <- quote[quote > 0L]
#>             }
#>         }
#>         else d <- list(if (makeRownames) row.names(x), if (makeColnames) names(x))
#>         p <- ncol(x)
#>     }
#>     nocols <- p == 0L
#>     if (is.logical(quote)) 
#>         quote <- NULL
#>     else if (is.numeric(quote)) {
#>         if (any(quote < 1L | quote > p)) 
#>             stop("invalid numbers in 'quote'")
#>     }
#>     else stop("invalid 'quote' specification")
#>     rn <- FALSE
#>     rnames <- NULL
#>     if (is.logical(row.names)) {
#>         if (row.names) {
#>             rnames <- as.character(d[[1L]])
#>             rn <- TRUE
#>         }
#>     }
#>     else {
#>         rnames <- as.character(row.names)
#>         rn <- TRUE
#>         if (length(rnames) != nrow(x)) 
#>             stop("invalid 'row.names' specification")
#>     }
#>     if (!is.null(quote) && rn) 
#>         quote <- c(0, quote)
#>     if (is.logical(col.names)) {
#>         if (!rn && is.na(col.names)) 
#>             stop("'col.names = NA' makes no sense when 'row.names = FALSE'")
#>         col.names <- if (is.na(col.names) && rn) 
#>             c("", d[[2L]])
#>         else if (col.names) 
#>             d[[2L]]
#>         else NULL
#>     }
#>     else {
#>         col.names <- as.character(col.names)
#>         if (length(col.names) != p) 
#>             stop("invalid 'col.names' specification")
#>     }
#>     if (file == "") 
#>         file <- stdout()
#>     else if (is.character(file)) {
#>         file <- if (nzchar(fileEncoding)) 
#>             file(file, ifelse(append, "a", "w"), encoding = fileEncoding)
#>         else file(file, ifelse(append, "a", "w"))
#>         on.exit(close(file))
#>     }
#>     else if (!isOpen(file, "w")) {
#>         open(file, "w")
#>         on.exit(close(file))
#>     }
#>     if (!inherits(file, "connection")) 
#>         stop("'file' must be a character string or connection")
#>     qstring <- switch(qmethod, escape = "\\\"", double = "\"\"")
#>     if (!is.null(col.names)) {
#>         if (append) 
#>             warning("appending column names to file")
#>         if (quoteC) 
#>             col.names <- paste0("\"", gsub("\"", qstring, col.names, 
#>                 fixed = TRUE), "\"")
#>         writeLines(paste(col.names, collapse = sep), file, sep = eol)
#>     }
#>     if (nrow(x) == 0L) 
#>         return(invisible())
#>     if (nocols && !rn) 
#>         return(cat(rep.int(eol, NROW(x)), file = file, sep = ""))
#>     if (is.matrix(x) && !is.atomic(x)) 
#>         mode(x) <- "character"
#>     if (is.data.frame(x)) {
#>         x[] <- lapply(x, function(z) {
#>             if (is.object(z) && !is.factor(z)) 
#>                 as.character(z)
#>             else z
#>         })
#>     }
#>     invisible(.External2(C_writetable, x, file, nrow(x), p, rnames, 
#>         sep, eol, na, dec, as.integer(quote), qmethod != "double"))
#> }
#> <bytecode: 0x55b97d05d770>
#> <environment: namespace:utils>
#> --- 
#>  
#> ## xmlInternalTreeParse
#> function (file, ignoreBlanks = TRUE, handlers = NULL, replaceEntities = FALSE, 
#>     asText = FALSE, trim = TRUE, validate = FALSE, getDTD = TRUE, 
#>     isURL = FALSE, asTree = FALSE, addAttributeNamespaces = FALSE, 
#>     useInternalNodes = TRUE, isSchema = FALSE, fullNamespaceInfo = FALSE, 
#>     encoding = character(), useDotNames = length(grep("^\\.", 
#>         names(handlers))) > 0, xinclude = TRUE, addFinalizer = TRUE, 
#>     error = xmlErrorCumulator(), isHTML = FALSE, options = integer(), 
#>     parentFirst = FALSE) 
#> {
#>     isMissingAsText = missing(asText)
#>     if (length(file) > 1) {
#>         file = paste(file, collapse = "\n")
#>         if (!missing(asText) && !asText) 
#>             stop(structure(list(message = "multiple URLs passed to xmlTreeParse. If this is the content of the file, specify asText = TRUE"), 
#>                 class = c("MultipleURLError", "XMLParserError", 
#>                   "simpleError", "error", "condition")))
#>         asText = TRUE
#>     }
#>     if (missing(isURL) && !asText) 
#>         isURL <- length(grep("^(http|ftp|file)://", file, useBytes = TRUE, 
#>             perl = TRUE))
#>     if (file == "" || length(file) == 0) 
#>         stop("empty or no content specified")
#>     if (isHTML) {
#>         validate = FALSE
#>         getDTD = FALSE
#>         isSchema = FALSE
#>         docClass = "HTMLInternalDocument"
#>     }
#>     else docClass = character()
#>     checkHandlerNames(handlers, "DOM")
#>     if (missing(fullNamespaceInfo) && inherits(handlers, "RequiresNamespaceInfo")) 
#>         fullNamespaceInfo = TRUE
#>     oldValidate = xmlValidity()
#>     xmlValidity(validate)
#>     on.exit(xmlValidity(oldValidate))
#>     if (!asText && isURL == FALSE) {
#>         if (file.exists(file) == FALSE) 
#>             if (!missing(asText) && asText == FALSE) {
#>                 e = simpleError(paste("File", file, "does not exist"))
#>                 class(e) = c("FileNotFound", class(e))
#>                 stop(e)
#>             }
#>             else asText <- TRUE
#>     }
#>     if (asText && length(file) > 1) 
#>         file = paste(file, collapse = "\n")
#>     old = setEntitySubstitution(replaceEntities)
#>     on.exit(setEntitySubstitution(old), add = TRUE)
#>     if (asText && length(grep(sprintf("^%s?\\s*<", BOMRegExp), 
#>         file, perl = TRUE, useBytes = TRUE)) == 0) {
#>         if (!isHTML || (isMissingAsText && !inherits(file, "AsIs"))) {
#>             e = simpleError(paste("XML content does not seem to be XML:", 
#>                 if (file.exists(file)) 
#>                   file
#>                 else sQuote(substring(file, 100))))
#>             class(e) = c("XMLInputError", class(e))
#>             (if (isHTML) 
#>                 warning
#>             else stop)(e)
#>         }
#>     }
#>     if (!is.logical(xinclude)) {
#>         xinclude = as.logical(xinclude)
#>     }
#>     if (!asText && !isURL) 
#>         file = path.expand(as.character(file))
#>     if (useInternalNodes && trim) {
#>         prevBlanks = .Call("RS_XML_setKeepBlanksDefault", 0L, 
#>             PACKAGE = "XML")
#>         on.exit(.Call("RS_XML_setKeepBlanksDefault", prevBlanks, 
#>             PACKAGE = "XML"), add = TRUE)
#>     }
#>     .oldErrorHandler = setXMLErrorHandler(error)
#>     on.exit(.Call("RS_XML_setStructuredErrorHandler", .oldErrorHandler, 
#>         PACKAGE = "XML"), add = TRUE)
#>     if (length(options)) 
#>         options = sum(options)
#>     ans <- .Call("RS_XML_ParseTree", as.character(file), handlers, 
#>         as.logical(ignoreBlanks), as.logical(replaceEntities), 
#>         as.logical(asText), as.logical(trim), as.logical(validate), 
#>         as.logical(getDTD), as.logical(isURL), as.logical(addAttributeNamespaces), 
#>         as.logical(useInternalNodes), as.logical(isHTML), as.logical(isSchema), 
#>         as.logical(fullNamespaceInfo), as.character(encoding), 
#>         as.logical(useDotNames), xinclude, error, addFinalizer, 
#>         as.integer(options), as.logical(parentFirst), PACKAGE = "XML")
#>     if (!missing(handlers) && length(handlers) && !as.logical(asTree)) 
#>         return(handlers)
#>     if (!isSchema && length(class(ans))) 
#>         class(ans) = c(docClass, oldClass(class(ans)))
#>     if (inherits(ans, "XMLInternalDocument")) 
#>         addDocFinalizer(ans, addFinalizer)
#>     else if (!getDTD && !isSchema) {
#>         class(ans) = oldClass("XMLDocumentContent")
#>     }
#>     ans
#> }
#> <bytecode: 0x55b9780ff098>
#> <environment: namespace:XML>
#> --- 
#>  
#> ## xmlValue
#> function (x, ignoreComments = FALSE, recursive = TRUE, encoding = getEncoding(x), 
#>     trim = FALSE) 
#> {
#>     UseMethod("xmlValue")
#> }
#> <bytecode: 0x55b97483ce20>
#> <environment: namespace:XML>
#> --- 
#>  
#> ## yaml.load_file
#> function (input, error.label, readLines.warn = TRUE, ...) 
#> {
#>     if (missing(error.label)) {
#>         if (inherits(input, "connection")) {
#>             s <- try(summary(input), silent = TRUE)
#>             if (!inherits(s, "try-error") && is.list(s) && "description" %in% 
#>                 names(s)) {
#>                 error.label <- s$description
#>             }
#>         }
#>         else if (is.character(input) && nzchar(input[1])) {
#>             error.label <- input[1]
#>         }
#>         else {
#>             error.label <- NULL
#>         }
#>     }
#>     if (is.character(input)) {
#>         con <- file(input, encoding = "UTF-8")
#>         on.exit(close(con), add = TRUE)
#>     }
#>     else {
#>         con <- input
#>     }
#>     yaml.load(readLines(con, warn = readLines.warn), error.label = error.label, 
#>         ...)
#> }
#> <bytecode: 0x55b970646750>
#> <environment: namespace:yaml>
#> --- 
#>  
#> ## yc_get
#> function(refdate = Sys.Date(),
#>                    cache_folder = cachedir(),
#>                    do_cache = TRUE) {
#>   get_single_yc(1, as.Date(refdate), cache_folder, do_cache)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_ipca_get
#> function(refdate = Sys.Date(),
#>                         cache_folder = cachedir(),
#>                         do_cache = TRUE) {
#>   get_single_yc_ipca(1, as.Date(refdate), cache_folder, do_cache)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_ipca_mget
#> function(first_date = Sys.Date() - 5,
#>                          last_date = Sys.Date(),
#>                          by = 1,
#>                          cache_folder = cachedir(),
#>                          do_cache = TRUE) {
#>   first_date <- as.Date(first_date)
#>   last_date <- as.Date(last_date)
#> 
#>   # find biz days in between
#>   tpl <- .retrieve_template(NULL, "TaxasReferenciais")
#> 
#>   date_vec <- bizseq(first_date, last_date, tpl$calendar)
#> 
#>   # use by to separate dates
#>   date_vec <- date_vec[seq(1, length(date_vec), by = by)]
#> 
#>   # get data!
#>   df_yc <- bind_rows(
#>     log_map_process_along(date_vec, get_single_yc_ipca,
#>       "Fetching data points",
#>       date_vec = date_vec,
#>       cache_folder = cache_folder,
#>       do_cache = do_cache
#>     )
#>   )
#> 
#>   return(df_yc)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_ipca_superset
#> function(yc, fut) {
#>   fut_di1 <- fut |>
#>     filter(.data$commodity == "DAP") |>
#>     mutate(forward_date = maturity2date(.data$maturity_code, "15th day") |>
#>       following("Brazil/ANBIMA")) |>
#>     select(.data$refdate, .data$forward_date, .data$symbol)
#> 
#>   yc |>
#>     left_join(fut_di1, by = c("refdate", "forward_date"))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_mget
#> function(first_date = Sys.Date() - 5,
#>                     last_date = Sys.Date(),
#>                     by = 1,
#>                     cache_folder = cachedir(),
#>                     do_cache = TRUE) {
#>   first_date <- as.Date(first_date)
#>   last_date <- as.Date(last_date)
#> 
#>   # find biz days in between
#>   tpl <- .retrieve_template(NULL, "TaxasReferenciais")
#> 
#>   date_vec <- bizseq(first_date, last_date, tpl$calendar)
#> 
#>   # use by to separate dates
#>   date_vec <- date_vec[seq(1, length(date_vec), by = by)]
#> 
#>   # get data!
#>   df_yc <- bind_rows(
#>     log_map_process_along(date_vec, get_single_yc,
#>       "Fetching data points",
#>       date_vec = date_vec,
#>       cache_folder = cache_folder,
#>       do_cache = do_cache
#>     )
#>   )
#> 
#>   return(df_yc)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_superset
#> function(yc, fut) {
#>   fut_di1 <- fut |>
#>     filter(.data$commodity == "DI1") |>
#>     mutate(forward_date = maturity2date(.data$maturity_code) |>
#>       following("Brazil/ANBIMA")) |>
#>     select(.data$refdate, .data$forward_date, .data$symbol)
#> 
#>   yc |>
#>     left_join(fut_di1, by = c("refdate", "forward_date"))
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_usd_get
#> function(refdate = Sys.Date(),
#>                        cache_folder = cachedir(),
#>                        do_cache = TRUE) {
#>   get_single_yc_usd(1, as.Date(refdate), cache_folder, do_cache)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_usd_mget
#> function(first_date = Sys.Date() - 5,
#>                         last_date = Sys.Date(),
#>                         by = 1,
#>                         cache_folder = cachedir(),
#>                         do_cache = TRUE) {
#>   first_date <- as.Date(first_date)
#>   last_date <- as.Date(last_date)
#> 
#>   # find biz days in between
#>   tpl <- .retrieve_template(NULL, "TaxasReferenciais")
#> 
#>   date_vec <- bizseq(first_date, last_date, tpl$calendar)
#> 
#>   # use by to separate dates
#>   date_vec <- date_vec[seq(1, length(date_vec), by = by)]
#> 
#>   # get data!
#>   df_yc <- bind_rows(
#>     log_map_process_along(date_vec, get_single_yc_usd,
#>       "Fetching data points",
#>       date_vec = date_vec,
#>       cache_folder = cache_folder,
#>       do_cache = do_cache
#>     )
#>   )
#> 
#>   return(df_yc)
#> }
#> <environment: namespace:rb3>
#> --- 
#>  
#> ## yc_usd_superset
#> function(yc, fut) {
#>   fut_di1 <- fut |>
#>     filter(.data$commodity == "DDI") |>
#>     mutate(forward_date = maturity2date(.data$maturity_code) |>
#>       following("Brazil/ANBIMA")) |>
#>     select(.data$refdate, .data$forward_date, .data$symbol)
#> 
#>   yc |>
#>     left_join(fut_di1, by = c("refdate", "forward_date"))
#> }
#> <environment: namespace:rb3>
#> --- 
#> 
#> $`%or%`
#> NULL
#> 
#> $add.bizdays
#> NULL
#> 
#> $alert
#> NULL
#> 
#> $alert_fun
#> NULL
#> 
#> $apply_rule
#> NULL
#> 
#> $apply_rule.class_rule
#> NULL
#> 
#> $apply_rule.predicate_rule
#> NULL
#> 
#> $apply_rule.regex_rule
#> NULL
#> 
#> $apply_rules
#> NULL
#> 
#> $arrange
#> NULL
#> 
#> $as_dbl
#> NULL
#> 
#> $as_tibble
#> NULL
#> 
#> $as.data.frame.fields
#> NULL
#> 
#> $ascii
#> NULL
#> 
#> $base64_datetime_download
#> NULL
#> 
#> $base64encode
#> NULL
#> 
#> $bind_rows
#> NULL
#> 
#> $bizdayse
#> NULL
#> 
#> $bizseq
#> NULL
#> 
#> $cachedir
#> NULL
#> 
#> $cdi_get
#> NULL
#> 
#> $check_parameters
#> NULL
#> 
#> $ck_if_null
#> NULL
#> 
#> $clearcache
#> NULL
#> 
#> $cli_alert_danger
#> NULL
#> 
#> $cli_alert_info
#> NULL
#> 
#> $cli_alert_success
#> NULL
#> 
#> $cli_alert_warning
#> NULL
#> 
#> $cli_progress_along
#> NULL
#> 
#> $code2month
#> NULL
#> 
#> $code2month_newcode
#> NULL
#> 
#> $code2month_oldcode
#> NULL
#> 
#> $cols_number
#> NULL
#> 
#> $company_cash_dividends_download
#> NULL
#> 
#> $company_cash_dividends_reader
#> NULL
#> 
#> $company_details_download
#> NULL
#> 
#> $company_details_reader
#> NULL
#> 
#> $company_listed_supplement_download
#> NULL
#> 
#> $company_listed_supplement_reader
#> NULL
#> 
#> $composite
#> NULL
#> 
#> $content
#> NULL
#> 
#> $convert_to
#> NULL
#> 
#> $copy_file_to_temp
#> NULL
#> 
#> $cotahist_bdrs_get
#> NULL
#> 
#> $cotahist_equity_get
#> NULL
#> 
#> $cotahist_equity_options_get
#> NULL
#> 
#> $cotahist_equity_options_superset
#> NULL
#> 
#> $cotahist_etfs_get
#> NULL
#> 
#> $cotahist_fiagros_get
#> NULL
#> 
#> $cotahist_fidcs_get
#> NULL
#> 
#> $cotahist_fiis_get
#> NULL
#> 
#> $cotahist_funds_options_get
#> NULL
#> 
#> $cotahist_get
#> NULL
#> 
#> $cotahist_get_symbols
#> NULL
#> 
#> $cotahist_index_options_get
#> NULL
#> 
#> $cotahist_indexes_get
#> NULL
#> 
#> $cotahist_options_by_symbol_superset
#> NULL
#> 
#> $cotahist_units_get
#> NULL
#> 
#> $csv_read_file
#> NULL
#> 
#> $curve_download
#> NULL
#> 
#> $curve_read
#> NULL
#> 
#> $datetime_download
#> NULL
#> 
#> $digest
#> NULL
#> 
#> $display_template
#> NULL
#> 
#> $download_marketdata
#> NULL
#> 
#> $field
#> NULL
#> 
#> $fields
#> NULL
#> 
#> $fields_description
#> NULL
#> 
#> $fields_handlers
#> NULL
#> 
#> $fields_names
#> NULL
#> 
#> $fields_widths
#> NULL
#> 
#> $Filename
#> NULL
#> 
#> $filter
#> NULL
#> 
#> $filter_equity_data
#> NULL
#> 
#> $flatten_names
#> NULL
#> 
#> $following
#> NULL
#> 
#> $format_equity
#> NULL
#> 
#> $format_options
#> NULL
#> 
#> $fromJSON
#> NULL
#> 
#> $futures_get
#> NULL
#> 
#> $futures_mget
#> NULL
#> 
#> $fwf_read_file
#> NULL
#> 
#> $GET
#> NULL
#> 
#> $get_single_indexreport
#> NULL
#> 
#> $get_single_marketdata
#> NULL
#> 
#> $get_single_yc
#> NULL
#> 
#> $get_single_yc_ipca
#> NULL
#> 
#> $get_single_yc_usd
#> NULL
#> 
#> $getdate
#> NULL
#> 
#> $getFromNamespace
#> NULL
#> 
#> $getNodeSet
#> NULL
#> 
#> $hasName
#> NULL
#> 
#> $headers
#> NULL
#> 
#> $html_element
#> NULL
#> 
#> $html_nodes
#> NULL
#> 
#> $html_table
#> NULL
#> 
#> $html_text
#> NULL
#> 
#> $ibovespa_index_get
#> NULL
#> 
#> $idi_get
#> NULL
#> 
#> $index_by_segment_get
#> NULL
#> 
#> $index_comp_get
#> NULL
#> 
#> $index_get
#> NULL
#> 
#> $index_get_from_file
#> NULL
#> 
#> $index_weights_get
#> NULL
#> 
#> $indexes_get
#> NULL
#> 
#> $indexes_last_update
#> NULL
#> 
#> $indexreport_get
#> NULL
#> 
#> $indexreport_mget
#> NULL
#> 
#> $indexreport_reader
#> NULL
#> 
#> $inner_join
#> NULL
#> 
#> $is
#> NULL
#> 
#> $iter_rules
#> NULL
#> 
#> $json_read_file
#> NULL
#> 
#> $just_download_data
#> NULL
#> 
#> $left_join
#> NULL
#> 
#> $library.dynam
#> NULL
#> 
#> $library.dynam.unload
#> NULL
#> 
#> $load_builtin_calendars
#> NULL
#> 
#> $load_templates
#> NULL
#> 
#> $log_map_process_along
#> NULL
#> 
#> $map
#> NULL
#> 
#> $map_chr
#> NULL
#> 
#> $map_dfr
#> NULL
#> 
#> $map_int
#> NULL
#> 
#> $map_lgl
#> NULL
#> 
#> $MarketData
#> NULL
#> 
#> $match_class
#> NULL
#> 
#> $match_predicate
#> NULL
#> 
#> $match_regex
#> NULL
#> 
#> $maturity2date
#> NULL
#> 
#> $maturity2date_newcode
#> NULL
#> 
#> $maturity2date_oldcode
#> NULL
#> 
#> $mcsv_read_file
#> NULL
#> 
#> $mfwf_read_file
#> NULL
#> 
#> $mutate
#> NULL
#> 
#> $new
#> NULL
#> 
#> $new_field
#> NULL
#> 
#> $new_part
#> NULL
#> 
#> $new_template
#> NULL
#> 
#> $options_open_interest_read
#> NULL
#> 
#> $parse_columns
#> NULL
#> 
#> $parse_text
#> NULL
#> 
#> $parse_url
#> NULL
#> 
#> $parser_generic
#> NULL
#> 
#> $parsers
#> NULL
#> 
#> $pass_thru_handler
#> NULL
#> 
#> $pb_bar
#> NULL
#> 
#> $pb_current
#> NULL
#> 
#> $pb_eta_str
#> NULL
#> 
#> $pb_percent
#> NULL
#> 
#> $pb_spin
#> NULL
#> 
#> $pb_total
#> NULL
#> 
#> $pivot_longer
#> NULL
#> 
#> $POST
#> NULL
#> 
#> $preceding
#> NULL
#> 
#> $pricereport_reader
#> NULL
#> 
#> $print
#> NULL
#> 
#> $print.fields
#> NULL
#> 
#> $print.parts
#> NULL
#> 
#> $proto
#> NULL
#> 
#> $query_cdi
#> NULL
#> 
#> $read_csv
#> NULL
#> 
#> $read_excel
#> NULL
#> 
#> $read_file
#> NULL
#> 
#> $read_fwf
#> NULL
#> 
#> $read_html
#> NULL
#> 
#> $read_marketdata
#> NULL
#> 
#> $read_rds
#> NULL
#> 
#> $read.table
#> NULL
#> 
#> $registry
#> NULL
#> 
#> $rule_result
#> NULL
#> 
#> $save_resource
#> NULL
#> 
#> $select
#> NULL
#> 
#> $settlement_prices_download
#> NULL
#> 
#> $settlement_prices_read
#> NULL
#> 
#> $show_templates
#> NULL
#> 
#> $simple_download
#> NULL
#> 
#> $single_futures_get
#> NULL
#> 
#> $single_index_get
#> NULL
#> 
#> $slot
#> NULL
#> 
#> $status_code
#> NULL
#> 
#> $stock_indexes_composition_download
#> NULL
#> 
#> $stock_indexes_composition_reader
#> NULL
#> 
#> $stock_indexes_current_portfolio_download
#> NULL
#> 
#> $stock_indexes_json_reader
#> NULL
#> 
#> $stock_indexes_statistics_download
#> NULL
#> 
#> $stock_indexes_theo_portfolio_download
#> NULL
#> 
#> $str_c
#> NULL
#> 
#> $str_detect
#> NULL
#> 
#> $str_ends
#> NULL
#> 
#> $str_glue
#> NULL
#> 
#> $str_length
#> NULL
#> 
#> $str_match
#> NULL
#> 
#> $str_pad
#> NULL
#> 
#> $str_replace
#> NULL
#> 
#> $str_replace_all
#> NULL
#> 
#> $str_split
#> NULL
#> 
#> $str_starts
#> NULL
#> 
#> $str_sub
#> NULL
#> 
#> $str_to_lower
#> NULL
#> 
#> $str_trim
#> NULL
#> 
#> $system.file
#> NULL
#> 
#> $take
#> NULL
#> 
#> $take.list
#> NULL
#> 
#> $tibble
#> NULL
#> 
#> $to_date
#> NULL
#> 
#> $to_date_handler
#> NULL
#> 
#> $to_datetime
#> NULL
#> 
#> $to_dbl
#> NULL
#> 
#> $to_factor_handler
#> NULL
#> 
#> $to_int
#> NULL
#> 
#> $to_numeric_handler
#> NULL
#> 
#> $to_strtime_handler
#> NULL
#> 
#> $to_time_handler
#> NULL
#> 
#> $toJSON
#> NULL
#> 
#> $transmute_regex
#> NULL
#> 
#> $transmuter
#> NULL
#> 
#> $trim_fields
#> NULL
#> 
#> $unfactor
#> NULL
#> 
#> $unformat
#> NULL
#> 
#> $unzip
#> NULL
#> 
#> $unzip_recursive
#> NULL
#> 
#> $url_encoded_download
#> NULL
#> 
#> $width
#> NULL
#> 
#> $write_rds
#> NULL
#> 
#> $write.table
#> NULL
#> 
#> $xmlInternalTreeParse
#> NULL
#> 
#> $xmlValue
#> NULL
#> 
#> $yaml.load_file
#> NULL
#> 
#> $yc_get
#> NULL
#> 
#> $yc_ipca_get
#> NULL
#> 
#> $yc_ipca_mget
#> NULL
#> 
#> $yc_ipca_superset
#> NULL
#> 
#> $yc_mget
#> NULL
#> 
#> $yc_superset
#> NULL
#> 
#> $yc_usd_get
#> NULL
#> 
#> $yc_usd_mget
#> NULL
#> 
#> $yc_usd_superset
#> NULL
```

**\* might not be suitable for large packages with many exported
functions**

<br> <br>

#### **comments:**

<!-- record comments on package source code here -->

## Review test suite:

See guidance on
[testing](https://ropensci.github.io/dev_guide/building.html#testing)
for further details.

### test coverage

``` r
covr::package_coverage(pkg_dir)
#> rb3 Coverage: 81.01%
#> R/addin-display-template.R: 0.00%
#> R/addin-show-templates.R: 0.00%
#> R/util.R: 61.54%
#> R/marketdata.R: 73.81%
#> R/readers.R: 77.98%
#> R/scraper-indexes.R: 80.30%
#> R/transmute.R: 80.62%
#> R/fields.R: 80.70%
#> R/scraper-cdi.R: 86.67%
#> R/zzz.R: 87.80%
#> R/downloaders.R: 89.60%
#> R/scraper-yc.R: 91.55%
#> R/scraper-futures.R: 95.89%
#> R/handlers.R: 96.15%
#> R/convert_to.R: 100.00%
#> R/download-data.R: 100.00%
#> R/file.R: 100.00%
#> R/scraper-cotahist.R: 100.00%
```

### inspect [tests](https://github.com/wilsonfreitas/rb3/blob/master/tests/testthat)

#### **comments:**

-   Recommend to implement GitHub action.
    <!-- record comments on testing suite here -->

------------------------------------------------------------------------
