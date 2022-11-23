API Overview
============
In general the version number in the api call is the letter 'v' followed by the latest major version number. E.g. 'v1'. It is also possible 
to use the string 'latest' to call upon the latest version of the api. 

If an api is deprecated and no longer supported then the error 404 'Not Found – the requested resource does not exist' is returned. 

APIs v1
=======

==============
Authentication
==============
.. toctree::
   :maxdepth: 1

   api-authentication_POST
   
======
Target
======
.. toctree::
   :maxdepth: 1

   api-target_GET
   api-target_POST
