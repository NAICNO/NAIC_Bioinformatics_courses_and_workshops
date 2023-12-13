Model training and validation
=============================

This step use AlphaFold model, which is already trained to predict
protein structures *(pre-trained)*. Then this pre-trained model is
trained on a dataset prepared in the previous step.

.. mermaid::

   graph TD;
   i1(Benign & Pathogenic - training data) --> 1
   i3(Benign & Pathogenic - training data) --> 6
   i4(Balanced ClinVar & benign variants) --> 7
   1(Updated AlphaFold pre-trained model)
   1 --> 2(Makes predictions for each variant)
   2 --> 3(Compare prediction to actual variants and calculate the error) 
   3 --> 4(Update model parameters based on error)
   4 --> 5(Improved model)
   5 --> 6(Make predictions & evaluate the performance)
   6 --> 4
   6 --> 7(Model validation)
   7 --> 4
   7 --> 8(Prediction performance reaches a stable level)
      classDef highlight fill:#99ccff;
      classDef white fill:#ffffff;
      class 1,2,3,4,5,6,7,8 highlight;   

.. Note::

   Model training details
   -----------------------


   .. rubric:: Bening labelled variants:

   - Human variants: gnomAD
   - Primate variants: Great Ape project and a few other sources 
   - Remove training variants at protein positions if they appear on validation or test sets

   .. rubric:: Low-frequency variants are likely to be pathogenic than the frequent ones

   -  Used machine learning technique that adjusts model parameters
      according to the variant frequency so that the *frequent variants
      contribute more strongly to the training signal*

   .. rubric:: Pathogenic labelled variants

   -  Unobserved in human and primate populations (unobserved data)

   .. rubric::  Training data
   
   - Balanced dataset reflecting the true distribution of pathogenic and benign missense variants in the population

   -  The pathogenic set contains the same number of variants for each trinucleotide context as the benign set
   -  Probability of sampling a pathogenic variant depends on abundance of its protein in the benign set

   -  Variants in proteins that play a role in critical cellular function are likely to be pathogenic. Minimize the bias of functional context of protein in training set

   .. rubric:: Effects of using balanced training and test dataset

   - Unobserved data (pathogenic variants in training data) can have likely bening variants. Following technique can be used to filter-out likely bening variants in unobserved data

   1. Use ``AlphaMissense initial model`` - Already learned to
      differentiate pathogenic and benign variants
   2. Predict pathogenicity of unobserved variants using initial model
   3. Use new scores to remove likely bening variants in unobserved data

   Minimize the probability of including likely bening unobserved variants in downstream AlphaMissense model training rounds
