# Module 2 - Metabolite Annotation and Stable Isotope Tracing

## Metabolite Annotation

In Module 1, the basic processing of MS data was achieved using Asari, resulting in feature tables summarizing all detected features across the experiment. In this module, we will expand upon the previous analysis by performing annotation. Later in Module 2, we will introduce the basics of processing Stable Isotope Tracing data. 

But first, what is Annotation? 

Annotation is the mapping of observed spectral features to one or more candidate compounds or metabolites. Annotations are classified according to the confidence levels detailed in _____ et al (___) as summarized below:

    - Level 1a: annotation generated based on MS2 and precursor m/z similarity to an authentic compound standard
    - Level 1b: annotation generated based on m/z and rtime similarity to an authentic compound standard
    - Level 2: annotation generated based on MS2 and precursor m/z similarity to a spectral database entry
    - Level 4: annotation generated using m/z-based matching to a chemical structure database

Note that while higher confidence annotations are higher quality than lower confidence annotation, annotation confidence is only a proxy for annotation correctness. Metabolites that are critical for the biological interpretation of a study may warrant further characterization to confirm their identities. Additionally, many features observed in untargeted studies may not receive an annotation despite representing real metabolites present in the samples.

Great diversity exists in the annotation schemes and algorithms used by various software. For example, some software will directly annotate features without any pre-processing while others may do various steps to clean up the data before annotation. The annotation process for Asari is described below. 

## Pre-Annotation and Empirical Compounds

Asari performs annotation on an intermediate data structure we call an Empricial Compound (empCpd). An empCpd is a collection of features likely representing the same chemical entity or isomers thereof. Separation of isomers, if desired, must be done at the experimental level (e.g., chiral column). EmpCpds are constructed using our Khipu package by identifying known mass patterns between co-eluting features corresponding to either isotopologues or adducts of the metabolite. Here an isotopologue refers to a version of the metabolite with a specific isotopic composition while adduction is the phenomena in which a metabolite "picks up" one or more other elements during ionization (e.g., Na, K, H, etc.) In Asari, all annotations are performed at the empCpd level and then mapped back to individual features. Using sets of features, Khipu can also infer the neutral mass of a metabolite despite not being able to observe the neutral mass directly using mass spectrometry. We call this process pre-annotation as it occurs before annotation to compounds but still provides isotope and adduct annotations.

Pre-annotation has multiple advantages, most importantly, it reduces the number of annotations that must be generated thereby minimizing the chance of false positives. For example, if a metabolite has five features due to adduction and isotopologue patterns, only one query is performed rather than five. Additionally, empCpd construction yields a data structure that captures both known and unknown metabolites for downstream analysis. 

In notebook 2.1, we will construct empCpds from the MT02 dataset and generate Level 2 and Level 4 annotations for them. 

## Stable Isotope Tracing

In stable isotope tracing experiments, an exogenous supply of an isotope is provided to the system using one or more "tracer" compounds that have been enriched for these stable isotopes. A commonly used tracer in U-13C-Glucose in which all six carbons have been replaced with 13C. Unlike radioactive tracers, such as 14C, the isotopes selected for these experiments do not decay, simplifying their use in living organisms, but complicating data analysis as many stable isotopes occur at appreciable rates in nature (e.g., 1% of all carbon is 13C). As the tracers are metabolized the enriched isotopes accumulate in downstream metabolites until a steady state is reached or the experiment is terminated.

Since the only plausable mechanism by which a metabolite can acquire multiple tracer isotopes is by being a downstream metabolite of one or more tracers, empirical compounds that are heavily enriched for a tracer isotope are likely metabolites even if they cannot be annotated. 

In notebook 2.2, we will construct empCpds for the _____ dataset, generate reprsentative khipugrams for labelled metabolites, and identiy a novel metabolite on the basis of isotope labelling patterns. 