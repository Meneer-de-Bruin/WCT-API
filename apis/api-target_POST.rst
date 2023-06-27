Create Target (POST)
====================
Create a target.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/targets <https://wct-api.readthedocs.io/en/latest/apis/api-target_POST.html>`_

target-id and creationdate can never be created. These are system generated. 

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
============ ======= ========
**Body**
-----------------------------
general      List    Required
seeds        List    Optional
profile      List    Optional
schedule     List    Optional
annotations  List    Optional
description  List    Optional
groups       List    Optional
access       List    Optional
============ ======= ========

-----------------
**part: general**
-----------------
A list of general properties that belong to a target. This contains the following information:

=================== ======= ========
**general**
------------------------------------
name                String  Required
description         String  Optional
referenceNumber     String  Optional
RunOnApproval       Boolean Optional
automatedQA         Boolean Optional
owner               String  Required
state               Number  Required
autoPrune           Boolean Optional
referencdCrawl      Boolean Optional
requestToArchivists String  Optional
=================== ======= ========

| **RunOnApproval**
| The default is 'false'.

| **automatedQA**
| The default is 'false'.

.. include:: descriptions/desc-state_target.rst

| **autoPrune**
| The default is 'false'.

| **refCrawl**
| The default is 'false'.

---------------
**part: seeds**
---------------
A list of seeds that belong to a target containing the following information:

============== ======= ========
**seeds**
-------------------------------
seed           URL     Required
primary        Boolean Required
authorisations List    Required
============== ======= ========

| **primary**
| This indicates if a seed is the primary seed, or not. There can only be one primary seed. Default is 'false'.

| **authorisations**
| A list of identifiers of harvest authorisations. The harvest authorisation information itself can be retrivied with the API :doc:`api-harvest_authorisation_GET`.

.. include:: descriptions/part-profile_target.rst

.. include:: descriptions/desc-harvesterType.rst

.. include:: descriptions/desc-overrides.rst

| **profile**
| Required when imported is 'true'. This then contains the imported profile as-is.

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


.. include:: descriptions/part-annotations_target.rst

.. include:: descriptions/part-description_target.rst

.. include:: descriptions/part-groups_target.rst

----------------
**Part: access**
----------------
A list of access properties that belong to a target. This contains the following information:

=================== ======= ========
**access**
------------------------------------
displayTarget       Boolean Required
accessZone          Number  Required
displayChangeReason String  Optional
displayNote         String  Optional
=================== ======= ========

Response
--------
200: OK

The inserted target is returned as if the API :doc:`api-target_GET` had been used.

Errors
------
If any error is raised no output is returned. Nor is the target created.

=== =======================================================================================
400	Bad request, required value <element> has not been given.
403 Not authorized, user is no longer logged in.
405 Method not allowed, only POST, GET, PUT, DELETE are allowed.
=== =======================================================================================
