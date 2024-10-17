# Module 3 - Common Statistical Tests and Plots

## Why notebooks for stats and plots?

For the majority of experiments, some form of statistical testing is required to identify features of interest and uncover differences between samples. Statistics is also one of the most common steps where errors are introduced, either through mistakes or inappropriate selection of tests and cutoffs. For this reasons, notebooks are great for recording exactly what was done and redistributing the analysis in a reusable manner for reviewers and other scientists. Similarly plotting can be done using notebooks so that figures can be trivially reproduced or altered. 

## Statistics - parametric or non-parametric

The choice of statistical test depends on the type of data you are working with, the question you are trying to answer, and the assumptions you want to make about the data. Parametric tests make assumptions about the underlying distribution of the data and use these assumptions to maximize the statistical power of the tests. Non-parametric tests make fewer assumptions about the underlying distribution of data but as a result are less powerful. 

The choice between non-parametric and a parametric test is often made subjectively. Real world data are rarely perfectly normally distributed and assumptions about equal variance and normality can be hard to test  robustly. How un-normal can a distribution be before the parametric test is less meaningful? How much do you care about a false positive and how many true positives are you willing to miss to minimize the false positive rate? There are also inbetween solutions such as the Welch's T-test, a parametric test that assumes normality but not equal variance. In this module we will cover examples of both tests, including an edge case where there is no choice but to use a parametric test due to low sample size, in notebook 3.1.

## Multiple testing correciton

Statistical tests often report back p-values as eitehr significant or not significant on a pre-determined cutoff value referred to as alpha. A common value of alpha is 0.05 but other values can be used provided that they are decided upon *before* doing the test. One issue that arises in large -omics datasets is the need to account for multiple tests. If we assume that an alpha of 0.05, this implies that an individual test will be a false positive 5% of the time. Thus as increasingly more tests are performed (N), the likelihood of at least one false positive (P) increases dramatically (P = 1-((1-alpha)**N)). For instance, after 10 tests, there is a 40% probability that at least one is erroneous and after 90 tests there is a 99% percent likelihood. 

This can be mitigated by accounting for multiple testing in the statistics. Various techniques exist for combating this problem. Similar to the decision to use a parametric or non-parametric test, it is a balancing act of minimizing false positives while preserving statistical power. The most simple correction is to multiply each p-value by the number of tests performed, this is a bonferroni correction and while it controls multiple testing well, it also crushes power. The benjamini-hochberg correction is a more conservative approach that corrects for multiple testing, albeit less strictly than the bonferroni correction, but with the added upside of better preserving power. We will explore both options in notebook 3.1.

## Plotting

Plots are critical to communicating results effectively, but high dimensional data can be very difficult to visualize. In notebook 3.2, we will make some of the more common plots needed for metaoblomics analyses including box plots of feature intensities per sample, clustermaps showing the relative similarity of different samples, and finally we will perform PCA and visualize the results. 