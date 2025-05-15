################
 Local Packages
################

Local packages are **precompiled binaries** that can be used directly,
without the need for remote downloads or additional build steps.

To create a local package:

#. Build a target using ``xmake build``.

#. Package it with ``xmake package --format=local``.

#. Copy the generated build/packages directory to the repository of your
   choice.

   .. note::

      Your package repository should only contain the packages directory
