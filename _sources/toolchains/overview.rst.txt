##########
 Overview
##########

A toolchain is a set of programming tools that work together to build
software for a specific platform or environment

In XMake, toolchains are defined using the ``toolchain`` function, where
you specify the compiler, linker, and other tools using ``set_toolset``.
You can then load the necessary environment variables with custom
tooling.

.. code:: lua

   toolchain("myclang")
       set_toolset("cc", "clang")
       set_toolset("cxx", "clang++")
   toolchain_end()

Once defined, a toolchain can be applied at either the project or target
level by calling ``set_toolchains``

.. code:: lua

   set_toolchains("llvm")
   target("hi") do
        set_toolchains("msvc")

You can also specify which toolchain to use from the command line with:

.. code:: bash

    xmake config --toolchain=gcc
