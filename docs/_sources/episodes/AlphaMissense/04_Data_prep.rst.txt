Data Preparation
================

-  The process of collecting, cleaning, and organizing large datasets of
   variants along with their corresponding pathogenicity annotations
-  Critical for ensuring the quality and reliability of the model’s
   predictions

.. mermaid::

   graph TD;
   1(Data collection)
   1 -- Raw data - missense variants + respective protein sequences--> 2
   2(Data annotation)
   2 -- Data annotated with pathogenicity/benign status--> 3
   3(Cleaned data)
   3 -- Removing duplicated and erroneous data --> 4
   4(Split data) --> 5(Training data)
   4(Split data) --> 6(Validation data)
   4(Split data) --> 7(Test data)

   A(Ensure the variants are accurately identified <br> and annotated with their respective protein sequences) -->
   B(Gathering pathogenicity annotations <br> from reliable sources)
   B --> C(Ensures the data is clean,<br> consistent, and ready to be used for modeling)
   C --> D(Model training/validation and testing)
      classDef highlight fill:#99ccff;
      classDef white fill:#ffffff;
      class 1,2,3,4,5,6,7 highlight;
      

.. Note::

   .. rubric:: Dataset Splitting :mega:
      :name: dataset-splitting-mega

   -  Training data:

      -  Train the AlphaMissense model
      -  Bening: missense variants frequently observed in human and
         primate populations
      -  Pathogenic: missense variants absent from human and primate
         populations

   -  Validation data:

      -  Tune model parameters
      -  Held-out data - Pathogenic missense variants in ClinVar
         (ClinVar ) & Bening variants from population-databases

   -  Test data:

      -  Evaluate the model’s performance on unseen data
      -  Held-out data - Pathogenic missense variants in ClinVar and
         other selected studies & Bening variants from
         population-databases


.. Attention::

   .. rubric:: Validation data vs test data

   - Validation data:
      - Used during model training to guide many model-building decisions
   - Test data:
      - Completely unseen dataset used at the very end to get an unbiased evaluation of the fully trained model
