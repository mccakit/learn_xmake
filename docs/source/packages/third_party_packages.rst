######################
 Third Party Packages
######################

XMake supports importing and using packages defined in other build
systems, such as CMake, allowing for seamless integration of external
dependencies

To consume a third party package:

#. Clone the source repository of the desired package
#. Define a remote package using the ``package`` function and import the
   third-party build system using ``import``
#. Create a configuration table to specify how you want the package to
   be installed
#. Use ``tool.install`` to specify how the package should be built and
   installed
#. In your project, declare the package with ``add_requires``
#. Link the package to your target using ``add_packages``

*******
 CMake
*******

.. code:: lua

   package("foo", function()
       add_deps("cmake", "meson")
       set_sourcedir("foo")
       on_install(function (package)
           local configs = {
               "-DGLFW_BUILD_DOCS=OFF",
               "-DGLFW_BUILD_TESTS=OFF",
               "-DGLFW_BUILD_EXAMPLES=OFF"
           }
           import("package.tools.cmake")
           cmake.install(package, configs)
       end)
    end)
