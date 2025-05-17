##########
 Overview
##########

In the context of a build system, a package refers to a collection of
pre-built or pre-configured resources—such as headers, libraries,
tools, or assets—that can be automatically downloaded and seamlessly
integrated into your project's build process.

In XMake, you can package a target by using the ``xmake package`` command. By
providing the ``--format`` option, you can specify the package type,
such as ``remote`` or ``local``.

To use packages in your project:

#. Add the repository containing the package with ``add_repositories``.
#. Declare the required packages using ``add_requires``.
#. Make the packages available to your targets with ``add_packages``.

.. code:: bash

   xmake package --format=local static_lib

.. code:: lua

   add_repositories("some_repo" "some_url")
   add_requires("foo")

Additionally, XMake supports integration with other popular build
systems to leverage a wide range of existing packages. This is done by
importing the appropriate extension and calling its ``install``
function.

.. code:: lua

   package("foo", function()
       add_deps("cmake")
       set_sourcedir("foo")
       on_install(function (package)
           import("package.tools.cmake")
           cmake.install(package, {})
       end)
    end)
