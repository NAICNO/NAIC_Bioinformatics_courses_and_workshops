Studying genetic variations and disease outcomes
================================================

-  Deep learning is well-suited for analyzing the intricate
   relationships between genetic variations and disease outcomes,

   -  ultimately leading to accurate predictions of variant
      pathogenicity
   -  E.g., AlphaMissense from Google DeepMind

AlphaMissense
-------------

-  AlphaMissense is developed to predict the pathogenicity of missense
   variants

   -  i.e., Whether variants that change the protein sequences are
      likely to cause diseases (pathogenic) or not (bening).

-  AlphaMissense is based on AlphaFold model

   -  AlphaFold - Accuratley predicts 3D structure of proteins from
      their amino acid sequences using advanced deep learning techniques
      and biological knowledge-bases

AlphaMissense deep learning workflow
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  AlphaMissense deep learning workflow can be described in 4 main steps

.. mermaid::

   graph TD;
      1(Data preparation) --> 2(Feature engineering)
      2 --> 3(Model training)
      3 --> 4(Model evaluation)
        
      classDef highlight fill:#99ccff;
      classDef white fill:#ffffff;
      class 1,2,3,4 highlight;

.. Note::

   .. rubric:: Genomics context of each step :mega:
      :name: genomics-context-of-each-step-mega

   +---------------------------+------------------------------------------+
   | ML Concept                | Genomics conext                          |
   +===========================+==========================================+
   | Data preparation          | Collecting and processing a large        |
   |                           | dataset of missense variants along with  |
   |                           | annotations indicating their             |
   |                           | pathogenicity (disease-causing or        |
   |                           | benign)                                  |
   +---------------------------+------------------------------------------+
   | Feature engineering       | Convert amino acid sequences into        |
   |                           | representations suitable for deep        |
   |                           | learning models                          |
   +---------------------------+------------------------------------------+
   | Model training            | Fine-tune AlphaFold model that predicts  |
   |                           | protein structure to predict variant     |
   |                           | pathogenicity                            |
   +---------------------------+------------------------------------------+
   | Model evaluation          | Assess the accuracy and generalizability |
   |                           | of variant pathogenicity prediction      |
   |                           | using independent datasets               |
   +---------------------------+------------------------------------------+
