################
 Remote Package
################

Remote packages are **build instructions** used to compile a specific
target. They are especially important in *cross-compilation* scenarios,
where the build environment differs from the target system

To create a remote package:

#. Put the source code containing the target definition into a
   repository

#. Package a target with ``xmake package --format=remote``.

#. Point to your source repository with ``add_urls`` by editing the
   generated package defintion file

#. Copy the generated build/packages directory to the repository of your
   choice.

   .. note::

      Your repository should contain only the packages directory
