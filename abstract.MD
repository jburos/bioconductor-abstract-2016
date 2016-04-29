

## Working title: Strategies for large-scale analysis (GWAS) using Stan

## Premise

How to think about GWAS where the model is complex / estimation time is non-trivial

Also, typical GWAS treats all SNPs as independent; obviously not the case. 

Does it still make sense to run all X million SNPs independently on a massive HPC?

Possible approaches to consider: 
  1. simple first-pass using VB or MLE?
  then deeper analysis within selected regions, modeling LD / relationship between SNPs? 
  2. model all independent (pruned) SNPs together, in a massive model?
  3. variation of a random-forest, model-averaging over subsets of randomly-selected SNPs 


