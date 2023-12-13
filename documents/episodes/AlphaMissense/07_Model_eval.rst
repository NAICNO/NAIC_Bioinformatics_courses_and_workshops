Model evaluation
================

Model evaluation ensures that the model’s performance is not biased by
the training data and that it can generalize to new and unseen variants
\* Predict the pathogenicity of each variant in the independent dataset
(variants not included in the training dataset)

-  AlphaMissense model is evaluated using multiple clinical benchmark
   datasets

   -  ``ClinVar`` test set,
   -  ``De novo variants`` from rare disease patients,
   -  ``Multiplexed Assays of Variant Effect`` - experimentally
      validated data

|image1|

.. Note::

   .. rubric::  Performance evaluation matrices: Metrics used to evaluate the performance of a model

   -  Accuracy
   
      -  Percentage of correctly predicted disease-causing or benign
         missense variants out of all missense variants
   
   -  Precision
   
      -  Percentage of correctly predicted disease-causing missense
         variants out of all the predicted disease-causing variants
   
   -  Recall
   
      -  Percentage of correctly predicted disease-causing variants out of
         actual disease-causing variants
   
   -  Area Under the Receiver Operating Characteristic (auROC)
   
      -  ``auROC = 1`` represents a perfect classifier
   
         -  correctly identifies all pathogenic variants and no benign
            variants are classified as pathogenic
   
      -  ``auROC = 0.5`` represents a model that performs no better than
         random guessing
   

.. |image1| image:: https://md.sigma2.no/uploads/705ab25c-6a8a-4d71-a0a7-3af4fff80cde.png
