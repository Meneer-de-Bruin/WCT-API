------------------
**part: schedule**
------------------
Consists of the following information:

=================== ======= ========
**schedule**
------------------------------------
harvestOptimization Boolean Optional
harvestNow          Boolean Optional
schedules           List    Optional
=================== ======= ========

| **schedules**
| A list of schedules that belong to a target containing the following information:

================= ======= ========
**schedules**
----------------------------------
id                Number  Required
cron              String  Required
startDate         Date    Required
endDate           Date    Optional
type              Number  Required
owner             String  Required
nextExecutionDate Date    Required
lastExecutionDate Date    Optional
================= ======= ========

| **id**
.. include:: descriptions/desc-systemGenerated.rst

.. include:: descriptions/desc-cron.rst

| **startDate** 
.. include:: descriptions/desc-formatDate.rst

| **endDate** 
.. include:: descriptions/desc-formatDate.rst

.. include:: descriptions/desc-scheduleType.rst

.. include:: descriptions/desc-owner.rst

| **nextExecutionDate** 
.. include:: descriptions/desc-formatDate.rst

| **lastExecutionDate** 
.. include:: descriptions/desc-formatDate.rst
