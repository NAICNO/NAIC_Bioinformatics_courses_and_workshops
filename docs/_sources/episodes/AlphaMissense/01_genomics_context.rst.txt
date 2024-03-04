Genomics context of missense variants
=====================================

-  Missense variants alter the amino acid sequence that could affect the
   protein structure potentially leading to diseases
-  Missense variants leading to diseases are known as pathogenic
   missense variants
-  Missense variants with limited effects not leading to diseases are
   known as bening missense variants

.. Important:: 

   .. rubric:: Challenges in the current clinical setting

   -  Understanding the pathogenicity (or bening status) of missense
      variants is a major challenge in the current clinical setting
   -  Over the years, scientists have identified a long list of disease
      associated genes.

      -  Differentiating pathogenic and bening missense variants in
         these set of genes is also a challenging task

.. Note::

   .. rubric:: Current methods to predict the pathogenicity of missense
      variants
      :name: current-methods-to-predict-the-pathogenicity-of-missense-variants-mega

   +------------------------------------------+---------------------------+
   | Method                                   | Tool                      |
   +==========================================+===========================+
   | Evolutionary conservation                | ConSurf, FATHMM,          |
   |                                          | MutationAssessor,         |
   |                                          | PANTHER, PhD-SNP, SIFT,   |
   |                                          | SNPs&GO                   |
   +------------------------------------------+---------------------------+
   | Protein structure/function and           | Align GVGD, MAPP,         |
   | evolutionary conservation                | MutationTaster, MutPred,  |
   |                                          | PolyPhen-2                |
   +------------------------------------------+---------------------------+

   .. rubric:: Ensembl Variation pathogenicity predictions
      :name: ensembl-variation-pathogenicity-predictions

   Ref:
   https://www.ensembl.org/info/genome/variation/prediction/protein_function.html

   |image1|

   -  **REVEL**: Ensemble method that integrates scores from multiple
      pathogenicity predicting tools to one score

   .. rubric:: Limitations in current methods
      :name: limitations-in-current-methods

   -  Current tools rely on applying hard-thresholds (cut-off scores)
   -  Practically, these hard-thresholds are used only as guides

      -  For example, VEP user manual strongly recommends using an
         appropriate cut-off depending on the experiment and dataset.

   -  These tools are used to predict the pathogenicity of other variant
      types (not only missense)

      -  Tools have shown stronger pathogenicity scores for more harmful
         variant types (stop-gain, stop-loss, splice-site) compared to
         missense variants

.. danger::

   .. rubric:: Pathogenicity of missense variants
      :name: pathogenicity-of-missense-variants-fire

   -  Predicting the pathogenicity of missense variants remains a
      challenging task.
   -  A large majority of currently identified missense variants fall to
      the category - *variants with uncertain significance*

      -  `doi: 10.1038/s41586-020-2308-7 (Nature. 2020; 581(7809):
         434–443.) <https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7334197>`__

.. Important::

   .. rubric:: Deep learning based solution
      :name: deep-learning-based-solution-tada

   |image2|

.. |image1| image:: https://md.sigma2.no/uploads/71e7a315-75f5-44d0-9669-be2af0a2da83.png
.. |image2| image:: https://md.sigma2.no/uploads/131d3219-a641-4fcb-9d2d-171006bb9614.png
