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
startDate         Date   Required
endDate           Date   Optional
type              Number Required
owner             String Required
nextExecutionDate  Date   Required
lastExecutionDate Date   Optional
================= ====== ========

.. include:: descriptions/desc-cron.rst

| ** startDate ** 
.. include:: descriptions/desc-formatDate.rst

| ** endDate ** 
.. include:: descriptions/desc-formatDate.rst

.. include:: descriptions/desc-scheduleType.rst

.. include:: descriptions/desc-owner.rst

| ** nextExecutionDate ** 
.. include:: descriptions/desc-formatDate.rst

| ** lastExecutionDate ** 
.. include:: descriptions/desc-formatDate.rst

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

Example
-------
.. code-block:: linux

  curl \
  --location 'http://localhost/wct/api/v1/targets/<target-id>' \
  --header 'Authorization: Bearer <token>' \ 
  --header 'Content-Type: application/json' \
  --data-raw '{"general": { \
    "owner": "demo", \
    "state": 2, \
    "name" : "TEST - TARGET 2023-07-06T09:43:09.816Z" \
 } \
}'

.. code-block:: linux

  curl \
  --location 'http://localhost/wct/api/v1/targets/<target-id>' \
  --header 'Authorization: Bearer <token>' \ 
  --header 'Content-Type: application/json' \
  --data-raw '{ \
    "general": { \
        "owner": "demo", \
        "state": 5, \
        "name": "TEST - TARGET 2023-07-06T09:43:09.816Z - IJsselbi\u00EBnnale", \
        "description": "info@ijsselbiennale.nl" \
    }, \
 \
    "profile": { \
        "id": "1", \
        "imported": false, \
        "harvesterType": "HERITIRX3", \
        "name": "Default - KB", \
        "overrides": [ \
            { \
                "id": "ignoreRobots", \
                "value": true, \
                "enabled": true \
            } \
        ] \
    }, \
 \
    "groups": [],  \
 \
    "description": { \
        "description": "Test target", \
        "type": "01 - Algemeen" \
    }, \
 \
    "access": { \
        "displayTarget": true, \
        "accessZone": "0", \
        "accessZoneText": "Public" \
    }, \
 \
    "annotations": { \
        "selection": {"date": "2020-09-24T10:24:02.000+00:00"}, \
        "annotations": [] \
    }, \
 \
    "seeds": [ \
        { \
            "seed": "https://ijsselbiennale.nl/", \
            "primary": true, \
            "authorisations": [98304] \
        } \
    ], \
     \
    "schedule": { \
        "harvestOptimization": false, \
        "schedules": [ \
            { \
                "cron": "00 23 25 7,8,9 ? *", \
                "startDate": "2019-12-03T15:55:22.000+00:00", \
                "type": -3, \
                "nextExecutionDate": "2024-12-03T15:55:22.000+00:00", \
                "owner": "demo" \
            } \
        ] \
    } \
}'