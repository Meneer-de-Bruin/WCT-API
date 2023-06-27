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
scheduleId        Number Required
cron              String Required
scheduleStartDate Date   Required
scheduleEndDate   Date   Optional
scheduleType      Number Required
owner             String Required
nextScheduleDate  Date   Required
lastProcessedDate Date   Optional
================= ====== ========

.. include:: descriptions/desc-cron.rst

.. include:: descriptions/desc-scheduleStartDate.rst

.. include:: descriptions/desc-scheduleEndDate.rst

.. include:: descriptions/desc-scheduleType.rst

.. include:: descriptions/desc-owner.rst

.. include:: descriptions/desc-nextScheduleDate.rst

.. include:: descriptions/desc-lastProcessedDate.rst