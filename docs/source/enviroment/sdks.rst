#######
 SDK's
#######

This document uses the following toolchains:

.. csv-table:: SDK's
   :file: ../_static/enviroment/sdks.csv
   :widths: 3,3,6
   :align: left

*******
 MinGW
*******

Install it using scoop

.. code:: bash

   scoop install mingw

***********
 MacOS-SDK
***********

Clone the repo that illegally redistributes all versions

.. code:: bash

   git clone git@github.com:alexey-lysiuk/macos-sdk.git

********
 Debian
********

Set up a Debian sysroot using Docker

#. Install `WSL
   <https://learn.microsoft.com/en-us/windows/wsl/install>`_ and
   `Rancher Desktop <https://rancherdesktop.io/>`_

#. Pull the Debian Image, Build a container then install ``g++``

      .. code:: bash

         docker pull debian:bookworm
         docker run -it --name=deb debian:bookworm
         apt update; apt install g++; exit

#. Export the container as a .tar file and extract it as **admin**

.. code:: bash

   docker export deb -o deb.tar

*************
 Android SDK
*************

Install Android Studio CLI with scoop then use that to install the SDK

.. code:: bash

   scoop install android-clt
   sdkmanager "platforms;android-25"
   sdkmanager --update

************
 MILK-V Duo
************

Clone the official SDK for the Milk-V Duo

.. code:: bash

   git clone --recursive git@github.com:milkv-duo/duo-buildroot-sdk-v2.git

**********
 CH32V003
**********

Clone the official SDK from WCH

.. code:: bash

   git clone --recursive git@github.com:openwch/ch32v003.git
