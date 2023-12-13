Why accelerate genomics workflows?
==================================

-  **In the last couple of years, the field of AI has shown the
   importance of GPUs in accelerating machine learning workflows**
-  Current NGS analysis workflows can take days (especially for large
   datasets)

.. danger::

   GPUs for NGS
   -  Can we use GPUs to accelerate NGS workflows and reduce the
      processing time to hours/minutes?

.. Note::

   CPUs vs GPUs

   +-----------------------------------+-----------------------------------+
   | CPU                               | GPU                               |
   +===================================+===================================+
   | |image1|                          | |image2|                          |
   +-----------------------------------+-----------------------------------+
   | Core (processing units) can       | Core (processing unit)            |
   | complete a variety of tasks one   | specialized to do small, specific |
   | after another very quickly        | task                              |
   +-----------------------------------+-----------------------------------+
   | Several cores (e.g AMD EPYC 7642  | Many cores (e.g., NviDIA H100     |
   | 48-Core)                          | 15,432)                           |
   +-----------------------------------+-----------------------------------+
   | Best for Serial processing tasks  | Best for highly parallel tasks    |
   +-----------------------------------+-----------------------------------+
   | Traditional programs are written  | Additional Software are required  |
   | for CPU processing                | to convert CPU functions to GPU   |
   |                                   | functions for parallel execution  |
   +-----------------------------------+-----------------------------------+

.. |image1| image:: https://md.sigma2.no/uploads/979ec8af-4449-4e48-ad1b-5991b58d67b8.png
   :width: 20%
.. |image2| image:: https://md.sigma2.no/uploads/6f56709d-c1e3-4f9b-a547-c47e4a9dd271.png
   :width: 20%
