.. _installation:

============
Installation
============

TensorLayer has some prerequisites that need to be installed first, including
`TensorFlow`_ , numpy and matplotlib. For GPU
support CUDA and cuDNN are required.

If you run into any trouble, please check the `TensorFlow installation
instructions <https://www.tensorflow.org/versions/master/get_started/os_setup.html>`_
which cover installing the TensorFlow for a range of operating systems including
Mac OX and Linux, or ask for help on `tensorlayer@gmail.com <tensorlayer@gmail.com>`_
or `FQA <http://tensorlayer.readthedocs.io/en/latest/user/more.html>`_.



Step 1 : Install dependencies
=================================

TensorLayer is build on the top of Python-version TensorFlow, so please install
Python first.

.. note::
  We highly recommend python3 instead of python2 for the sake of future.

Python includes ``pip`` command for installing additional modules is recommended.
Besides, a `virtual environment
<http://www.dabapps.com/blog/introduction-to-pip-and-virtualenv-python/>`_
via ``virtualenv`` can help you to manage python packages.

Take Python3 on Ubuntu for example, to install Python includes ``pip``, run the following commands:

.. code-block:: bash

  sudo apt-get install python3
  sudo apt-get install python3-pip
  sudo pip3 install virtualenv

To build a virtual environment and install dependencies into it, run the following commands:
(You can also skip to Step 3, automatically install the prerequisites by TensorLayer)

.. code-block:: bash

  virtualenv env
  env/bin/pip install matplotlib
  env/bin/pip install numpy
  env/bin/pip install scipy
  env/bin/pip install scikit-image

To check the installed packages, run the following command:

.. code-block:: bash

  env/bin/pip list

After that, you can run python script by using the virtual python as follow.

.. code-block:: bash

  env/bin/python *.py




Step 2 : TensorFlow
=========================

The installation instructions of TensorFlow are written to be very detailed on `TensorFlow`_  website.
However, there are something need to be considered.
For example, `TensorFlow`_ only officially
supports GPU acceleration for Linux and Mac OX at present.

.. warning::
  For ARM processor architecture, you need to install TensorFlow from source.



Step 3 : TensorLayer
=========================

The simplest way to install TensorLayer is as follow, it will also install the numpy and matplotlib automatically.

.. code-block:: bash

  [stable version] pip install tensorlayer
  [master version] pip install git+https://github.com/zsdonghao/tensorlayer.git

However, if you want to modify or extend TensorLayer, you can download the repository from
`Github`_ and install it as follow.

.. code-block:: bash

  cd to the root of the git tree
  pip install -e .

This command will run the ``setup.py`` to install TensorLayer. The ``-e`` reflects
editable, then you can edit the source code in ``tensorlayer`` folder, and ``import`` the edited
TensorLayer.


Step 4 : GPU support
==========================

Thanks to NVIDIA supports, training a fully connected network on a
GPU, which may be 10 to 20 times faster than training them on a CPU.
For convolutional network, may have 50 times faster.
This requires an NVIDIA GPU with CUDA and cuDNN support.


CUDA
----

The TensorFlow website also teach how to install the CUDA and cuDNN, please see
`TensorFlow GPU Support <https://www.tensorflow.org/versions/master/get_started/os_setup.html#optional-install-cuda-gpus-on-linux>`_.

Download and install the latest CUDA is available from NVIDIA website:

 - `CUDA download and install <https://developer.nvidia.com/cuda-downloads>`_


..
  After installation, make sure ``/usr/local/cuda/bin`` is in your ``PATH`` (use ``echo #PATH`` to check), and
  ``nvcc --version`` works. Also ensure ``/usr/local/cuda/lib64`` is in your
  ``LD_LIBRARY_PATH``, so the CUDA libraries can be found.

If CUDA is set up correctly, the following command should print some GPU information on
the terminal:

.. code-block:: bash

  python -c "import tensorflow"


cuDNN
--------

Apart from CUDA, NVIDIA also provides a library for common neural network operations that especially
speeds up Convolutional Neural Networks (CNNs). Again, it can be obtained from
NVIDIA after registering as a developer (it take a while):

Download and install the latest cuDNN is available from NVIDIA website:

 - `cuDNN download and install <https://developer.nvidia.com/cudnn>`_


To install it, copy the ``*.h`` files to ``/usr/local/cuda/include`` and the
``lib*`` files to ``/usr/local/cuda/lib64``.

.. _TensorFlow: https://www.tensorflow.org/versions/master/get_started/os_setup.html
.. _GitHub: https://github.com/zsdonghao/tensorlayer
.. _TensorLayer: https://github.com/zsdonghao/tensorlayer/


Issue
=======

If you get the following output when import tensorlayer, please read `FQA <http://tensorlayer.readthedocs.io/en/latest/user/more.html>`_.

.. code-block:: bash

  _tkinter.TclError: no display name and no $DISPLAY environment variable
