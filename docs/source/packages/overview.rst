##########
 Overview
##########

A package in a build system context is indeed a collection of pre-built
or pre-configured resources (headers, libraries, tools, assets, etc.)
that can be downloaded and integrated into your project's build process
automatically.

In XMake, you can package a target using the command ``xmake package``.
By specifying the ``--format`` option, you can choose the package type,
such as ``remote`` or ``local``. To use packages in your project,
declare them with ``add_requires``, and make them available to targets using
``add_packages``

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

   package("foo")
       add_deps("cmake")
       set_sourcedir("foo")
       on_install(function (package)
           import("package.tools.cmake")
           cmake.install(package, {})
       end)
   package_end()
