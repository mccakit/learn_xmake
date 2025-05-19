##########
 Packages
##########

In a build system, a package collects ``pre-built`` or
``pre-configured`` resources that seamlessly integrate into your
project's build process.

XMake lets you package a ``target`` with the ``xmake package`` command.
Add parameters to specify the package format and other options.

To use packages in your project:

#. Add the repository containing the package with ``add_repositories``.
#. Declare the required packages using ``add_requires``.
#. Make the packages available to your targets with ``add_packages``.

.. code:: bash

   xmake package --format=local static_lib

.. code:: lua

   add_repositories("alias" "repository")
   add_requires("foo")
   target("hi", function()
        add_packages("foo")
   end)

****************
 Local Packages
****************

Local packages are **precompiled binaries** that can be used directly,
without the need for remote downloads or additional build steps.

To create a local package:

#. Build a target using ``xmake build``.
#. Package it with ``xmake package --format=local``.
#. Copy the generated build/packages directory to the repository of your
   choice.

****************
 Remote Package
****************

Remote packages are **build instructions** used to compile a specific
target. They are especially important in *cross-compilation* scenarios,
where the build environment differs from the target system

To create a remote package:

#. Create a repository that contains the target you will package

#. Package a target with ``xmake package --format=remote --url=<url>
   --version=<version>``.

#. Copy the generated build/packages directory to your chosen repository

      .. note::

         Package repositories should only contain the packages folder,
         not build/packages

**********************
 Third Party Packages
**********************

XMake lets you import and use packages defined in other build systems,
such as CMake

To use a third party package:

#. Clone the source repository of the package you want to use
#. Define a remote package with the ``package`` function and import the
   third-party build system using ``import``
#. Create a configuration table to specify your desired installation
   settings
#. Use ``extension.install`` to specify how the package should be built
   and installed

.. code:: lua

   package("foo", function()
       add_deps("cmake")
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
