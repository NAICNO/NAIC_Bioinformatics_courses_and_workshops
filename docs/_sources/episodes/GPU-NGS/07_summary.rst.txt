Summary
=======

.. container:: success

   -  GPU-only pipelines complete sequence analysis workflows ~22 to ~60
      times faster than CPU-only pipelines
   -  Performance of the GPU-only pipeline vary depending on the
      available GPU platform

      -  Pipeline run ~2.6x faster in ``A100`` compared to
         ``GeForce-RTX 3090``

   -  GPU-only and CPU-only pipelines both agrees on the DNA-changes
      detected in a given sample

      -  Over 99.2% DNA changes detected on a give sample are identified
         in both GPU- and CPU-only pipelines.

   -  Source code is not public and software is available in for use in
      the non-commercial settings (*commercial applications need to go
      for a paid license agreement* ).


Concerns
--------

-  Source code is not public

   -  Distributed as container image. Which means we can not make any
      changes to the wrappers and must use it as a whole.
   -  When we got stuck in several occasions due to resource limitation
      we had to spend a lot of time figuring out solutions
   -  We don’t have the option to compile the software on a GPU platform
      (i.e, ``Tesla M60``) and fix cuda-compatibility issues from
      our-side (we have to depend on NVIDIA - Parabricks developers)

-  Software is available for use in the non-commercial settings.
