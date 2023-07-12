============
API Overview
============
In general the version number in the api call is the letter 'v' followed by the latest major version number. E.g. 'v1'. It is also possible 
to use the string 'latest' to call upon the latest version of the api. 

If an api is deprecated and no longer supported then the error 404 'Not Found – the requested resource does not exist' is returned. 

Authentication
==============
.. toctree::
   :maxdepth: 1

   api-authentication_POST
   api-authentication_DELETE
   
Targets
=======
.. toctree::
   :maxdepth: 1

   api-targets_GET
   api-target_POST
   api-target_GET
   api-target_PUT
   api-target_DELETE
   api-target_states_GET
   api-target_scheduleTypes_GET
   
Target Instances
================
.. toctree::
   :maxdepth: 1

   api-target_instances_GET
   api-target_instance_states_GET

Group
=====
.. toctree::
   :maxdepth: 1
   
   api-groups_GET.rst
   
User
====
.. toctree::
   :maxdepth: 1
   
   api-users_GET.rst
   
Harvest Authorisations
======================
.. toctree::
   :maxdepth: 1
   
   api-harvest_authorisation_GET.rst
   
Profile
=======
.. toctree::
   :maxdepth: 1
   
   api-profile_GET.rst
