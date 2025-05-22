############
 Toolchains
############

This document uses the following toolchains:

.. csv-table:: Toolchains
   :file: ../_static/enviroment/toolchains.csv
   :widths: 2,2,8
   :align: left

******
 LLVM
******

To install LLVM with all available backends, you must compile it from
source. On Windows, this requires Visual Studio and additional
dependencies.

#. Install Visual Studio Build Tools

      #. Get the installer from `here
         <https://visualstudio.microsoft.com/downloads/?q=build+tools>`_
      #. Enable **Desktop Development with C++** and at the right panel
         enable *ATL*, *MFC*, *CLI* support and Modules

#. Install additional dependencies

      .. code:: bash

         scoop install python git

#. Build and Install LLVM in "x64 Native Tools Command Prompt"

      #. Clone the LLVM repository. I recommend using `this PR branch
         <https://github.com/tcottin/llvm-project>`_ as it enables
         Doxygen-style formatting on hover.

         .. code:: bash

            git clone --recursive git@github.com:tcottin/llvm-project.git
            cd llvm-project
            git switch clangd-doxygen-parser

      #. Build with CMake/Ninja

         .. code:: bash

            cmake -S llvm -B build -G Ninja ^
                -DLLVM_ENABLE_EH=ON ^
                -DLLVM_ENABLE_RTTI=ON ^
                -DLLVM_ENABLE_ASSERTIONS=ON ^
                -DLLVM_TARGETS_TO_BUILD="X86;ARM;AArch64;RISCV" ^
                -DCMAKE_BUILD_TYPE=Release ^
                -DLLVM_ENABLE_PROJECTS="clang;lld;clang-tools-extra;lldb" ^
                -DLLVM_ENABLE_RUNTIMES="libcxx;compiler-rt;libcxxabi"
            ninja -S build -j

#. Build and install LLVM, then add the ``bin`` directory of the
   installation to your ``PATH``

   .. code:: bash

      cmake --install build --prefix <path>

#. Patch LLVM installation to fix C++ Modules by cloning this `repo
   <https://github.com/mccakit/xmake_llvm_patch>`_ and overriding
   ``llvm\share\libc++\v1\std``

*******
 DPC++
*******

#. Download and run DPC++ installer from this `link
   <https://sycl.tech/getting-started#implementations>`__.

********
 Others
********

Install the remaining toolchains with scoop:

.. code:: bash

   scoop install emscripten rustup zig-dev openjdk17
   emsdk install latest
   emsdk activate latest --permanent
