############
 Toolchains
############

A toolchain is a set of programming tools that work together to build
software for a specific platform or environment

In XMake, you define a toolchain using the ``toolchain`` function.
Inside it, you specify the compiler, linker, and other tools with
``set_toolset``. You can also load any required environment variables
using your custom tooling.

.. code:: lua

   toolchain("myclang", function()
       set_toolset("cc", "clang")
       set_toolset("cxx", "clang++")
    end)

After defining a toolchain, you can use it either at project or target
level by calling ``set_toolchains``

.. code:: lua

   set_toolchains("llvm")
   target("llvm_target", function()
   end)
   target("msvc_target", function()
        set_toolchains("msvc")
   end)

You can also select a toolchain from the command line:

.. code:: bash

   xmake config --toolchain=gcc
