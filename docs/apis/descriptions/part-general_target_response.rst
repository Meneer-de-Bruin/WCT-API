-----------------
**part: general**
-----------------
A list of general properties that belong to a target. This contains the following information:

=================== ======= ========
**general**
------------------------------------
id                  Number  Required
creationDate        Date    Required
name                String  Required
description         String  Optional
referenceNumber     String  Optional
RunOnApproval       Boolean Required
automatedQA         Boolean Required
owner               String  Required
state               Number  Required
autoPrune           Boolean Required
referencdCrawl      Boolean Required
requestToArchivists String  Optional
=================== ======= ========

| **creationDate**
.. include:: descriptions/desc-formatDate.rst

.. include:: descriptions/desc-owner.rst

.. include:: descriptions/desc-state_target.rst

| **RunOnApproval**
| The default is 'false'.

| **automatedQA**
| The default is 'false'.

.. include:: descriptions/desc-state_target.rst

| **autoPrune**
| The default is 'false'.

| **refCrawl**
| The default is 'false'.