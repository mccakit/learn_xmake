#######
 SDK's
#######

In this document, a x64 Debian Bookworm Docker image will be used as a
sysroot for cross compilation.

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
