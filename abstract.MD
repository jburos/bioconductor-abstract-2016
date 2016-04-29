

## Working title: Strategies for large-scale analysis (GWAS) using Stan

## Premise

How to think about GWAS where the model is complex / estimation time is non-trivial

1. Typical GWAS treats all SNPs as independent; obviously not the case. 
  - Does it still make sense to run all X million SNPs independently on a massive HPC?
2. It can be difficult to systematically ascertain convergence / validity of results 
  - minimal set of criteria for initial screening of results

May or may not take an implicitly Bayesian approach at the outset, although many implementations are semi-bayesian.

## Content 

Possible approaches: 
  1. two-stage analysis, 
     - first-pass using RF, VB, or MLE to find potentially interesting SNPs
     - follow up within selected set of results, modeling LD / relationship between SNPs in greater detail
  2. model all independent (pruned) SNPs together
     - in a big model?
     - in a set of models, each with a subset of SNPs (ie variation of a random-forest)
  3. model all (indep + non-indep) SNPs together, accounting for LD structure

Choice may depend on set-up (ie type of outcome, etc). Classify "set ups" by their corresponding single-SNP model structure.

1. For "simple" case of logistic regression or survival model without time-varying covariates
   . no hierarchical structure in equivalent single-SNP model 
2. for "complex" case of family data, bivariate outcome and/or longitudinal model 
   . survival model with TVC
   . longitudinal model
   . family data

## Goals : 

1. Review methods for implementing various approaches to GWAS in Stan.  
2. Evaluate efficiency / validity among various methods of approaching GWAS, under variety of scenarios. 

## References : 

1. [A Bayesian Graphical Model for Genome-wide Association Studies (GWAS)](http://research.lunenfeld.ca/mprime_briollais/files/file/A%20Bayesian%20Graphical%20Model%20for%20Genome-wide%20Association%20Studies_%20Submitted%20to%20Annals%20of%20Applied%20Statistics.pdf)
2. [Prioritizing GWAS Results: A Review of Statistical Methods and Recommendations for Their Application](http://ac.els-cdn.com/S0002929709005321/1-s2.0-S0002929709005321-main.pdf)