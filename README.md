# allee_effects_stochasticity
Repository containing R code and output data for Gong et al., 2025

# Allee effects, colonization, and extinction: the surprising benefits of demographic stochasticity

Authors: Angela Gong, Emma Walker, and Benjamin Gilbert

Corresponding Author: Angela Gong, reachable at angelag0ng@outlook.com

This repository contains code and data files relevant to the following manuscript:

Allee effects, colonization, and extinction: the surprising benefits of demographic stochasticity.

In this manuscript, we outline novel insights into a means by which demographic stochasticity may promote persistence in long-lived populations. See below for an excerpt from the Methods section providing an overview of the analyses performed:

We formulated a discrete-time Markov chain describing the probability of population increase or decrease to any given population size within a single generation. Using this model we numerically solved for the probability that a population reaches its carrying capacity from a single individual (i.e., probability of colonization), and the extinction rates of populations initially at the upper equilibrium. We calculated these for populations varying in strength and attenuation of Allee effects, and across a range of carrying capacities, for different strengths of demographic stochasticity.

The main file of relevance for code documentation is entitled "Allee effects and stochasticity.Rmd". It contains annotated code for the functions and calculations that were performed to collect data for the study. The code for the manuscript was run using the following R and package versions:

- R version 4.4.2 (2024-10-31) -- "Pile of Leaves"
- cowplot 1.1.3
- egg 0.4.5
- ggpubr 0.6.0
- RColorBrewer 1.1-3
- scales 1.3.0
- tidyverse 2.0.0, including: dplyr 1.1.4, readr 2.1.5, forcats 1.0.0, stringr 1.5.1, ggplot2 3.5.1, tibble 3.2.1, lubridate 1.9.3, tidyr 1.3.1, and purrr 1.0.2
- vegan 2.6-8
- viridis 0.6.5

This Rmd file is entirely self-contained; given the required packages, no other data or code files are necessary to reproduce the data and figures visualized in the manuscript. Nevertheless, we also provide three data files in this repository. These data files are summarized as follows, alongside a description of each column:

1. "allee effects and stochasticity main results.csv" - this file contains results for parameter combinations that are visualized in the main text of the manuscript (i.e., figs. 1-4).

    1.  "Kapx": the maximum carrying capacity for the population in the absence of an Allee effect
    2.  "r": the intrinsic growth rate of the population
    3.  "b": the Allee effect attenuation point, or the point at which the Allee effect reaches half its maximum strength
    4.  "beta": a constant used to vary the strength of the Allee effect, which is equal to beta/b
    5.  "init.size": size parameter used in the negative binomial distribution to generate transition matrices. This parameter is inversely correlated with the strength of demographic stochasticity.
    6.  "Kexact": the upper equilibrium of the population.
    7.  "rcrit": the Allee threshold of the population.
    8.  "p.colonization.from.one": the probability of colonization to Kexact from a population size of 1.
    9.  "poiss.imm": the total probability of colonization for a population experiencing stochastic immigration.
    10. "p.colonization.from.rcrit": the probability of colonization to Kexact from the Allee threshold.
    11. "p.colonization.to.rcrit": the probability of colonization to the Allee threshold from a population size of 1.
    12. "t.extinction.from.Kexact": the waiting time to extinction from Kexact.
    13. "t.extinction.from.rcrit": the waiting time to extinction from the Allee threshold.

2.  "allee effects and stochasticity main results more parms.csv" - this file contains results for an extended set of parameter combinations that are visualized in the supplementary figures section of the manuscript. The columns are the same as the previous file.

3.  "allee effects and stochasticity supplementary results probability of colonization for one or more immigrants.csv" - this file contains results for the analysis performed and visualized in figure S3 in the supplementary figures section of the manuscript.

    1.  "number.immigrants": the number of immigrants arriving at a patch.
    2.  "p.establish": the probability of colonization to Kexact for the population from the number of immigrants specified in column 1.
    3.  "Kapx": the maximum carrying capacity for the population in the absence of an Allee effect
    4.  "r": the intrinsic growth rate of the population
    5.  "b": the Allee effect attenuation point, or the point at which the Allee effect reaches half its maximum strength
    6.  "beta": a constant used to vary the strength of the Allee effect, which is equal to beta/b
    7.  "init.size": size parameter used in the negative binomial distribution to generate transition matrices. This parameter is inversely correlated with the strength of demographic stochasticity.
    8.  "Kexact": the upper equilibrium of the population.
    9.  "rcrit": the Allee threshold of the population.

To save some time, one can use these data files and simply run the code file from lines 271-632 (for main text figures), and lines 637-790 and 842-1170 (for supplementary figures). However, once again, these data files can be reproduced by simply running the entirety of the code file.
