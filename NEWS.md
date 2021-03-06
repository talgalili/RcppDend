dendextendRcpp 0.6.0 (2015-05-22)
----------------------------

UPDATED R FUNCTIONS:
   * renamed: labels.dendrogram -> dendextendRcpp_labels.dendrogram
   * assign_dendextendRcpp_to_dendextend - 
      * now loads into dendextend_options the dendextendRcpp_labels.dendrogram. This is intended to fix: 
               "checking use of S3 registration ... WARNING
            Registered S3 method from a standard package overwritten by 'dendextendRcpp':
            method from 
            labels.dendrogram stats"
      * Added "dendextend::" to fix: "no visible global function
definition for 'dendextend_options'"
   * Fix various "no visible global function definition for"

OTHER NOTES:
   * Now works through "create_dendextend_options" (Thanks to suggestions by Kurt Hornik and Uwe Ligges).


dendextendRcpp 0.5.1 (2014-03-16)
----------------------------

UPDATED R DOCS:
   * Hiding {microbenchmark} from the docs (Props to Prof Brian Ripley), from the functions: dendextendRcpp_get_branches_heights, dendextendRcpp_heights_per_k.dendrogram, dendextendRcpp::labels.dendrogram


dendextendRcpp 0.5.0 (2014-03-15)
----------------------------

UPDATED DESCRIPTION:
   * Added dependency for R (>= 3.0.0)

UPDATED R FUNCTIONS:
   * renamed: 
      * cut_lower_fun -> dendextendRcpp_cut_lower_fun
      * get_branches_heights -> dendextendRcpp_get_branches_heights
      * heights_per_k.dendrogram -> dendextendRcpp_heights_per_k.dendrogram

OTHER NOTES:
   * Now works through "create_dendextend_options" (Thanks to suggestions by Kurt Hornik and Uwe Ligges).
   * dendextendRcpp 0.5.0 is intended to be shipped to CRAN.



dendextendRcpp 0.4.0 (2014-03-01)
----------------------------

UPDATED R FUNCTIONS:
   * assign_dendextendRcpp_to_dendextend - Moved to passing the functions through "options" instead of through assignInNamespace.

OTHER NOTES:
   * Version 0.4.0 of dendextendRcpp will not be effective for versions of dendextend which are before 0.13.0 (however, it would also not conflict with them...)
   * dendextendRcpp 0.4.0 is intended to be shipped to CRAN.



dendextendRcpp 0.3.3 (2014-02-04)
----------------------------

UPDATED R FUNCTIONS:
   * assign_dendextendRcpp_to_dendextend - remove assign of old_ functions (we might as well just copy them manually)
   * old_* functions moved to the new imports_dendextend.r file

UPDATED Rcpp FUNCTIONS:
   * patches for Rcpp 0.11.0, using as<RObject> to wrap some functions so that the package will compile. Props to Kevin Ushey!
   * changed .hpp -> .h (for portability issues, props to Kurt Hornik)

UPDATED DESCRIPTION:
   * added Kevin Ushey to Authors@R list (thanks to his patch)

OTHER NOTES:
   * dendextend 0.3.3 is intended to be shipped to CRAN. (first release!)



dendextendRcpp 0.3.2 (2014-02-03)
----------------------------

UPDATED R FUNCTIONS:
   * assign_dendextendRcpp_to_dendextend - remove require(dendextend)
   * stats:::labels.dendrogram -> stats_labels.dendrogram (in the new imports_stats.r file)

TESTS:
   * dendextend::: ->  old_

DOCS:
   * Added aliases to: 'old_cut_lower_fun', 'old_get_branches_heights',  'old_heights_per_k.dendrogram'. Thus fixing "checking for missing documentation entries ... WARNING - Undocumented code objects:"
   * Fix: Codoc mismatches from documentation object 'labels.dendrogram'
   * cut_lower_fun - fix "cutree" links (to go to exact package)
   * Fix: Undocumented arguments in documentation object 'cut_lower_fun'
   * Rcpp_cut_lower -> dendextendRcpp::Rcpp_cut_lower
   * Undocumented code objects - added aliases

OTHER NOTES:
   * some minor updated to README.md
   * Fixed: cut_lower_labels -> cut_lower_fun
   * Added importFrom in order to fix "Packages in Depends field not imported from:"

   * dendextend 0.3.2 is intended to be shipped to CRAN. (first release! - failed after not working with Rcpp 0.11.0, though it did work for Rcpp 0.10.6)

dendextendRcpp 0.3.1 (2014-02-02)
----------------------------
UPDATED R FUNCTIONS:
   * assign_dendextendRcpp_to_dendextend 
      * added old_cut_lower_fun
      * Fixed the assignment of "old_" to "make sense"... (they are now added to dendextendRcpp enviornment)

OTHER NOTES:
   * Fixed Authors@R in DESCRIPTION
   * Fixes to indentation and some Rcpp modified code


dendextendRcpp 0.3.0 (2013-08-20)
----------------------------
NEW R FUNCTIONS ADDED: 
   * cut_lower_fun - overrides dendextend function - will give a 4-16 times faster cutree(h) function for R!

NEW RCPP FUNCTIONS ADDED: 
   * Rcpp_cut_lower (+find_dend_for_height).
      This function changes the output of the nodes to be of dendrogram class
      which enables the fast operation of functions on them!

dendextendRcpp 0.2.1 (2013-08-20)
----------------------------
OTHER NOTES:
   * added zzz.r file - with code to override dendextend functions in case dendextendRcpp is loaded AFTER dendextend.
   * fixed Rcpp_labels_dendrogram works test - adjusting for the new "warn" parameter.

dendextendRcpp 0.2.0 (2013-08-19)
----------------------------

NEW R FUNCTIONS ADDED: 
   * get_branches_heights - overrides dendextend function dendextend:::get_branches_heights function.
   * heights_per_k.dendrogram - gives a 10 to 130(!) faster loading times.

NEW RCPP FUNCTIONS ADDED: 
   * get_height
   * push_back_heights
   * Rcpp_get_dend_heights
   * Rcpp_k_per_height
   * Rcpp_k_per_heights (plural)

OTHER NOTES:
   * Moved "is" function to a new file called "is_functions.cpp".
Created a "is_functions.hpp" file for it, and made sure to call it from "labels_dendrogram.cpp"
   * moved labels.dendrogram to a new file labels_dendrogram.r
    
BUG FIXES
   * labels.dendrogram - now returns a label also if the tree is just a leaf.

THE PACKAGE IS NOW RENAMED:
   * from RcppDend to dendextendRcpp - in order to have it easier to remember (at least for me).

UPDATED FUNCTIONS:
   * labels.dendrogram - added warn=FALSE

dendextendRcpp 0.1.1 (2013-08-17)
----------------------------

BUG FIXES
   * Added missing rows from NAMESPACE (They were removed automatically due to a bug in roxygen2+Rstudio)

OTHER NOTES:
   * Added tests





dendextendRcpp 0.1.0 (2013-08-16)
----------------------------

NEW R FUNCTIONS ADDED: 
   * labels.dendrogram - overrides R's default stats:::labels.dendrogram function.

NEW RCPP FUNCTIONS ADDED: 
   * is_list
   * is_string
   * is_logical
   * is_leaf
   * get_label
   * push_back_labels
   * Rcpp_labels_dendrogram
   * Rcpp_count_leaves

OTHER NOTES:
   * First commit. Includes DESCRIPTION, a template for a basic test, a labels function, and this NEWS.



TODO
----------------------------
* Check if we have any old_ that should be changed into dendextend_

