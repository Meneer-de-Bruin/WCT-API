------------------
**Part: schedule**
------------------
Consists of the following information:

=================== ======= ========
**schedule**
------------------------------------
harvestOptimization Boolean Optional
schedules           List    Optional
=================== ======= ========

| **schedules**
| A list of schedules that belong to a target containing the following information:

================= ====== ========
**schedules**
---------------------------------
id                Number Required
cron              String Required
startDate         Date   Required
endDate           Date   Optional
type              Number Required
owner             String Required
nextExecutionDate Date   Required
lastExecutionDate Date   Optional
================= ====== ========

.. include:: desc-cron.rst

| ** startDate ** 
.. include:: desc-formatDate.rst

| ** endDate ** 
.. include:: desc-formatDate.rst

.. include:: desc-scheduleType.rst

.. include:: desc-owner.rst

| ** nextExecutionDate ** 
.. include:: desc-formatDate.rst

| ** lastExecutionDate ** 
.. include:: desc-formatDate.rst
