-----------------
**part: profile**
-----------------
A list of profile properties that belong to a target. This contains the following information:

=============== ======= ========
**profile**
--------------------------------
harvesterType   Number  Required
id              Number  Required
imported        Boolean Required
name            String  Required
overrides       List    Optional
profile			String	Optional
=============== ======= ========

.. include:: descriptions/desc-harvesterType.rst

.. include:: descriptions/desc-overrides.rst

| ** profile **
| Required when imported is 'true'. This then contains the imported profile.