nVIDIA K20x / Intel Xeon Phi cluster
====================================

Access
------

::

   qsub  -l partition=gpu,nodes=1:K20Xm <jobscript>

or

::

   qsub  -l partition=gpu,nodes=1:K40c <jobscript>

depending which GPU node you would like to use if you don't 'care' on
which type of GPU node your job ends up you can just submit it like
this:

::

   qsub  -l partition=gpu <jobscript>

Submit to a Phi node:
~~~~~~~~~~~~~~~~~~~~~

::

   qsub -l partition=phi <jobscript>

