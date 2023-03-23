-----------------
**part: general**
-----------------
A list of general properties that belong to a target. This contains the following information:

============= ======= ========
**general**
------------------------------
description   String  Required
refNumber     String  Optional
RunOnApproval Boolean Required
automatedQA   Boolean Required
userId        Number  Required
state         Number  Required
autoPrune     Boolean Required
refCrawl      Boolean Required
request       String  Optional
============= ======= ========

| **description**
| The default is an empty string.

| **RunOnApproval**
| The default is 'false'.

| **automatedQA**
| The default is 'false'.

.. include:: descriptions/desc-state_target.rst

| **autoPrune**
| The default is 'false'.

| **refCrawl**
| The default is 'false'.