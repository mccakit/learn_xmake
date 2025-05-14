##########
 Overview
##########

In XMake, a target is a core unit of the build system that represents
something you want to build, they are declared using the
target() function. The general syntax is:

.. code:: lua

   target("name") do
       --stuff
   end

At build time, XMake compiles the specified targets and links them
together as needed to produce the final output.

Configuration is done by calling functions inside the ``target``
function, here are the essential configuration functions you'll commonly
use:

-  ``set_kind()`` set the target type
-  ``add_files()`` add source files
-  ``add_headerfiles()`` add headerfiles
-  ``add_includedirs()`` add includedirs
-  ``add_deps()`` link a target
-  ``add_packages()`` link a package
