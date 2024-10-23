# MANA2024 - Working like a data scientist on Jupyter

This workshop covers how to use Jupyter notebook for data analysis and visualization, with a focus on mass spectrometry related metabolomics and isotope tracing data. 

The URL of this repo is https://github.com/shuzhao-li/MANA2024.

PowerPoint slides are included in this repo.

# Preparation for the Workshop

For MANA 2024 tutorials will be hosted in Google Colab, so no installation is needed on your local machine.

But the colab environment needs to be preapred. You will need a google account with which to access Colab. 

Once you are in Colab, if you know how to use notebooks already, go to Module 0, notebook 0.2 and run all blocks this will prepare the environment by installing necessary packages and downloading datasets. Else, checkout notebook 0.1 first. This will teach you the basics of how to run the code in the notebooks, its not important at this time to know all the details. Once you can run code blocks, do notebook 0.2.

Now the environment is configured and datasets have been downloaded and you can proceed with module 1.

# Downloding Data and Software

In the colab environment, datasets are non-persistent, so each notebook must download the data and required packages each time. The notebooks will do this automatically. 

## Workshop Outline

The workshop is 75 minutes, with 15 minutes for questions and reserved for troubleshooting. 

We organize it in four modules. Module 0 is only for configuring the environment, colab or local. 

### Module 0. Introduction and Installation

Objective: 
  - configure the environment, colab or local, to run the remaining modules. 

For MANA 2024, all notebooks are available on google colab bypassing the need for installation for the workshop. To reach the notebook in colab, you can open the notebook here on github and click the button at the top of each notebook. 

This module will not be presented during the workshop but may be useful to workshop attendees who want to use Jupyter on their own after the Workshop.

Notebooks:
  - Introduction to Jupyter and Notebooks (0.1)
  - Installation of packages used during the workshop and downloading datasets (0.2)

On Completion: 
  - your environement is now ready to run the remaining modules.

### Module 1. Visualization of mass spectrometry data

Objective:
  - learn and visualize fundamental concepts in mass spectrometry 
  - introduce concepts in data pre-processing with an example using Asari
  - be able to run a simple computational pipeline for LC-MS data with an example using pcpfm.

Notebooks:
  - The processing of MS data using Asari (1.1) 
  - Visualization of MS data from Asari (1.2)
  - Basic processing of MS data using the PCPFM pipeline (1.3)

### Module 2. Metabolite annotation and isotope tracing data

Objective:
  - learn about pre-annotation and what it accomplishes
  - introduce usage of Khipu, our preannotation tool.
  - perform annotation within the pipeline

Notebooks:
  - Standalone pre-annotation with Khipu (2.0)
  - Generation of Khipugrams for Isotope Tracing Data (2.1)
  - Annotation within the PCPFM pipeline (2.2)

### Module 3. Common statistical analyses and plots

Objective:
  - Learn about different statistical tests and libraries in Python
  - Apply statistical tests to data from asari.
  - Generate common plots needed for visualizing mass spectrometry data. 

Module 3 is an overview of common statistical tests you may need for metabolomics data processing and related plots.
  - Terminology and overview of statistical concepts presented (3.0)
  - Statistical tests on metabolomics data (3.1)
  - Generation of common plots for metabolomics data (3.2)

## After The Workshop

Many of the notebooks provided are reusable with minimal modification on your own datasets. If you have any questions, please open an issue or email me directly at joshua.mitchell@jax.org. 
