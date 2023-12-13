Evaluation of CPU-only vs GPU-only workflows
============================================

Testing workflows using sample data sets:
-----------------------------------------

-  Tested CPU-only and GPU-only workflow using two “Small-samples” and
   “Large-sample”
-  Raw data size:

   -  Small-sample 1: ``5.2`` *GB*
   -  Small-sample 2: ``12.4`` *GB*
   -  Large-sample 1: ``318`` *GB*

-  Tested GPU-only workflow using additional “Large-sample” sample

   -  Large-sample 2: ``627`` *GB*

Processing time
---------------

CPU-only workflow (i.e, current industry standard)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

=============================== =============== =================
Sample (sample size)            Processing time Resources
=============================== =============== =================
Small-sample 1 (``5.2``\ *GB*)  2hrs: 52mins    CPU:12; RAM:117GB
Small-sample 2 (``12.4``\ *GB*) 5hrs: 15mins    CPU:12; RAM:117GB
Large-sample 1 (``318``\ *GB*)  89hrs: 30mins   CPU:64; RAM:564GB
Large-sample-restricted\*       19hrs: 36mins   CPU:64; RAM:564GB
=============================== =============== =================

-  *Large-sample-restricted:*

   -  Restrict the tools to analysis specific set of regions that are
      most likely to harbour disease relevant DNA changes.

      .. raw:: html

         </p>

CPU-only vs GPU-only
~~~~~~~~~~~~~~~~~~~~

=============================== ============= ===================
Sample (sample size)            CPU-only      GPU-only
=============================== ============= ===================
Small-sample 1 (``5.2``\ *GB*)  02hrs: 52mins 0hrs: 05mins: 4sec
Small-sample 2 (``12.4``\ *GB*) 05hrs: 15mins 0hrs: 11mins: 44sec
Large-sample 1 (``318``\ *GB*)  89hrs: 30mins 4hrs: 08mins
Large-sample 2 (``627``\ *GB*)  NA            7hrs: 10mins.
=============================== ============= ===================

Performance on different NVIDIA GPU products
--------------------------------------------

-  UiO ML-Nodes provides access to different GPU platforms/products
-  We implemented the GPU-pipeline on two different GPU platforms

============================== ================ ==============
Sample (sample size)           GeForce-RTX 3090 A100-PCIE-40GB
============================== ================ ==============
Large-sample 1 (``318``\ *GB*) 4hrs: 08mins     1hrs: 33mins
============================== ================ ==============
