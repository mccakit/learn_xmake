#########
 Targets
#########

In XMake, a target represents something you want to build. You declare
targets using the ``target`` function. The general syntax looks like
this:

.. code:: lua

   target("name", function()
       --stuff
   end)

At build time, XMake compiles the specified targets and links them
together as needed to produce the final output.

You configure a target by calling functions inside the target block.
Here are the essential configuration functions you'll typically use:

-  ``set_kind()`` set the target type
-  ``add_files()`` add source files
-  ``add_headerfiles()`` add headerfiles
-  ``add_includedirs()`` add includedirs
-  ``add_deps()`` link a target
-  ``add_packages()`` link a package
-  ``add_syslinks()`` link to system libraries
-  ``add_cxflags()`` add C/C++ flags
-  ``add_ldflags()`` add linker flags
-  ``add_defines()`` add definitions
