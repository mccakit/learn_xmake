############
 Toolchains
############

In this document, following toolchains will be used:

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

      #. Install cmake, python, make and git with ``scoop install``

#. Build and Install LLVM

      #. Clone the LLVM repository. I recommend using `this PR branch
         <https://github.com/tcottin/llvm-project>`_ as it enables
         Doxygen-style formatting on hover.

         .. note::

            Don't forget to switch to ``clangd-doxygen-parser`` branch

      #. Open the x64 Native Tools Command Prompt and navigate to to
         your llvm repository

      #. Create build configuation file with ``cmake``

         .. note::

            I recommend building clang, lld, clang-tools-extra, lldb,
            libcxx, libc and compiler-rt with exception handling,
            run-time type information and assertions enabled. For
            targets, I suggest building X86, ARM and RISC-V

      #. Build and install LLVM with ``ninja --build`` and ```cmake
         --install``

#. Patch LLVM installation so C++ Modules work

      #. Clone this `repo
         <https://github.com/mccakit/xmake_llvm_patch>`_ that contains
         patch files for ``llvm\share\libc++\v1\std`` just override the
         files

#. Add the bin folder of your installation to your PATH

******
 EMCC
******

#. Download emscripten using scoop

      .. code:: bash

         scoop install main/emscripten

#. Install and activate Emscripten

      .. code:: bash

         emsdk install latest
         emsdk activate latest --permanent

*******
 DPC++
*******

#. Download and run DPC++ installer from this `link
   <https://sycl.tech/getting-started#implementations>`__.

******
 CUDA
******

#. Download CUDA using scoop

      .. code:: bash

         scoop install main/cuda

*******
 Rustc
*******

#. Download rustup using scoop

      .. code:: bash

         scoop install main/rustup

*****
 Zig
*****

#. Download zig using scoop

      .. code:: bash

         scoop install versions/zig-dev
