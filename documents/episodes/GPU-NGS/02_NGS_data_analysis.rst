NGS data analysis and precision genomics applications
=====================================================

Sequence data analysis
----------------------

-  Raw sequencing data is processed using a broad range of
   bioinformatics tools
-  Bioinformatics tools used to process these data sets depend on the

   -  type of the sequencing machine used to generate the raw data and
   -  the objective of the analysis (e.g., Precision genomics)

Precision genomics
------------------

-  Tailoring disease prevention and treatment based on the person’s
   genetic makeup
-  Here, we analyse raw sequencing data and identify changes in DNA that
   could lead to a diseases
-  Raw data analysis involves a number of complex processes and the
   collections of such processes are commonly known as “Sequence
   analysis workflows”

Main steps in sequence analysis workflows
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. mermaid::

   graph TD;
      i1(Raw data) --> 1
      i2(Reference data) --> 1
      1(Mapping raw data onto the reference)
      1 -- Alignment file --> 2
      2(Optimization & fine-tuning of the alignment file)
      2 -- Optimised & fine-tuned alignment file --> 3
      3(Identify DNA changes)

      classDef highlight fill:#99ccff;
      classDef white fill:#ffffff;
      class 1,2,3, highlight;
       

Precision genomics in routine clinical practice
-----------------------------------------------

-  Sequence analysis workflows are routinely used in current clinical
   setting
-  However they all (a large majority) use CPUs for the computing power
-  For a large sequence data set (i.e., cancer DNA-seq), it takes about
   24-48 hrs to complete a single sample *(CPUs: 64; RAM: 512GB)*.
