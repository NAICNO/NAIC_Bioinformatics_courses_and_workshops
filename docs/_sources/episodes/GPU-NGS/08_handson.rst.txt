Hands-on experiment :mega:
==========================

NAIC Clara Parabricks
~~~~~~~~~~~~~~~~~~~~~

|image1|

Installation: Clone NAIC Clara Parabricks GitHub ripository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: bash

   # Clone NAIC Clara Parabricks GitHub ripository
   git clone git@github.com:NAICNO/clara_parabricks.git

   # NGS analysis workflows are available in `clara_parabricks/workflows`
   cd clara_parabricks/workflows

Run command for ``GPU-only pipeline``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: bash

   bash nextflow-23.04.4-all \
       run \
       germline_pipeline.nf \
       -profile singularity \
       --fastq_folder <path to *fastq.gz files> \
       --genome_folder <path to GRCh38 reference files> \
       --genome_json reference_data.json \
       --processor GPU \
       -with-report \
       -with-trace \
       -resume
       
   ## Pipeline can use docker or singularity to run `parabricks` tools. 
   ## Refere `README.md` for more details.

Reference datasets:
^^^^^^^^^^^^^^^^^^^

.. code:: bash

   cat reference_data.json
   {
       "known_sites_gold_standard": {
         "vcf": "Mills_and_1000G_gold_standard.indels.hg38.vcf.gz",
         "tbi": "Mills_and_1000G_gold_standard.indels.hg38.vcf.gz.tbi"
       },
       "known_sites_high_confidence": {
         "vcf": "1000G_phase1.snps.high_confidence.hg38.vcf.gz",
         "tbi": "1000G_phase1.snps.high_confidence.hg38.vcf.gz.tbi"
       },
       "reference_fasta": {
         "fai": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.fai",
         "amb": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.amb",
         "pac": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.pac",
         "ann": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.ann",
         "bwt": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.bwt",
         "sa": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.sa",
         "fna": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna",
         "dict": "GCA_000001405.15_GRCh38_no_alt_analysis_set.fna.dict"
   }

Implementation details - ``README.md``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  https://github.com/NAICNO/clara_parabricks

Output
^^^^^^

.. code:: bash

   Results/GPU/
   -- sample_name
       |-- alignments
       |   |-- sample_name_GPU_recal_gpu.txt -> <path to workfolder>/sample_name_GPU_recal_gpu.txt
       |   |-- sample_name_pbrun_fq2bam_GPU.bam -> <path to workfolder>/sample_name_pbrun_fq2bam_GPU.bam
       |-- variants
           |-- haplotypeCaller
               |-- sample_name_pbrun_fq2bam_GPU.bam.vcf -> <path to workfolder>/sample_name_pbrun_fq2bam_GPU.bam.vcf

.. |image1| image:: https://md.sigma2.no/uploads/fe60572a-f721-4406-a250-9f14ab5b1982.png
