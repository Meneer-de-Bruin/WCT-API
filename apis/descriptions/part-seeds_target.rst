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
| This indicates if a seed is the primary seed, or not. There can only be one primary seed.

| **authorisations**
| A list of identifiers of harvest authorisations. The harvest authorisation information itself can be retrivied with the API :doc:`api-harvest_authorisation_GET`.