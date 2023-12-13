CPU-only and GPU-only workflows
===============================

-  NAIC - Norwegian AI Cloud implemented CPU-only and GPU-only workflows

   -  CPU-only: Industry standard best-practices workflow
   -  GPU-only: NVIDIA Clara Parabricks

NVIDIA Clara Parabricks
-----------------------

-  ``Clara Parabricks:`` GPU-enabled bioinformatics tools by NVIDIA

..

   Parabricks documentation:
   https://docs.nvidia.com/clara/parabricks/latest/index.html >
   Parabricks was built from the ground up by GPU computing and Deep
   Learning experts who wanted to develop the fastest and most efficient
   possible implementation of common genomics algorithms used in
   secondary analysis.

|image1|

NAIC - NVIDIA Clara Parabricks
------------------------------

**https://github.com/NAICNO/clara_parabricks** \* At NAIC, we used these
``Parabricks tools`` to create best-practices workflow and the current
standard CPU-only workflow

|image2|

NAIC workflows: CPU-only and GPU-only
-------------------------------------

+----------------+--------------------------+--------------------------+
| Stage          | CPU-only                 | GPU-only                 |
+================+==========================+==========================+
| Read mapping   | ``bwa mem`` ->           | ``pbrun fq2bam``         |
| and sorting by | ``samtools sort``        | (``GPU-BWA mem ->        |
| coordinates    |                          |  Sorting Phase-I & II``) |
+----------------+--------------------------+--------------------------+
| Masking        | GATK ``MarkDuplicates``  | ``pbrun fq2bam``         |
| duplicated     | -> ``BaseRecalibrator``  | (``GPU-GATK Marki        |
| reads &        |                          | ng Duplicates -> BQSR``) |
| generate base  |                          |                          |
| quality score  |                          |                          |
| recalibration  |                          |                          |
| table          |                          |                          |
+----------------+--------------------------+--------------------------+
| Recalibrate    | GATK ``ApplyBQSR`` ->    | `                        |
| base quality   | ``HaplotypeCaller``      | `pbrun haplotypecaller`` |
| scores and     |                          | (``GPU-GATK ApplyB       |
| call variants  |                          | QSR & HaplotypeCaller``) |
+----------------+--------------------------+--------------------------+

.. |image1| image:: https://md.sigma2.no/uploads/0e551b74-1ef3-46fa-8bd7-6471dadee6e0.png
.. |image2| image:: https://md.sigma2.no/uploads/318c01d1-5456-42a2-90a0-07ecf709c217.png
