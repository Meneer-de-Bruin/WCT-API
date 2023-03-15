API Overview
============
In general the version number in the api call is the letter 'v' followed by the latest major version number. E.g. 'v1'. It is also possible 
to use the string 'latest' to call upon the latest version of the api. 

If an api is deprecated and no longer supported then the error 404 'Not Found – the requested resource does not exist' is returned. 

.. toctree::
   :maxdepth: 1
   :caption Authentication

   apis/api-authentication_POST
   apis/api-authentication_DELETE
   
.. toctree::
   :maxdepth: 1
   :caption: Target

   apis/api-targets_GET
   apis/api-target_GET
   apis/api-target_DELETE