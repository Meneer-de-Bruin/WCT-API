-----------------
**part: profile**
-----------------
A list of profile properties that belong to a target instanace. This contains the following information:

=============== ======= ========
**profile**
--------------------------------
id              Number  Required
imported        Boolean Required
harvesterType   String  Required
name            String  Required
overrides       List    Optional
=============== ======= ========

| **id**
| A list of all profiles, with their id and name, can be retrieved with the API :doc: `api-profile_GET`_.

.. include:: descriptions/desc-harvesterType.rst

.. include:: descriptions/desc-overrides.rst

| **profile**
| Required when imported is 'true'. This then contains the imported profile as-is.