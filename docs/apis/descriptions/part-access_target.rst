----------------
**part: access**
----------------
A list of access properties that belong to a target. This contains the following information:

=================== ======= ========
**access**
------------------------------------
displayTarget       Boolean Required
accessZone          Number  Required
accessZoneText      String  Optional
displayChangeReason String  Optional
displayNote         String  Optional
=================== ======= ========

| **accessZone**
| The access zone of a target is an integer with the following values:

======== ===============
**Zone** **Description**
-------- ---------------
  0      Public
  1      Onsite
  2      Restricted
======== ===============

| **accessZoneText**
| Contains one of the following: Public, Onsite, Restricted, based upon the integer in accessZone.

When updating only the accessZone is taken into account. 

.. include:: descriptions/desc-systemGenerated.rst
