# This repository contains several projects related to self-driving cars.
All of the projects in this repository were designed and tested in
- 64-bit Anaconda 4.4.0 (Python 3.6.1)
- with OpenCV 3.3.0
- on Windows 10

If you need help setting this up on your computer, please follow the guide in the
following section

#### Installing Anaconda (or Python) with *OpenCV* and Matplotlib (and Numpy)
1. 
    - If you want to use Anaconda (which comes packaged with many additional, useful features), get it here https://www.anaconda.com/download/#download. The code in this repo was tested on the 64-bit version of Anaconda 4.4.0 for Windows.
    - If you only want the bare-bones python distribution, you can get it here
https://www.python.org/downloads/windows/. To
ensure that you have similar dependencies to the Anaconda version I used to write this code,
find a version with the prefix 3.6, and make sure you choose one of the **Windows x86-64** installers.
The default python download link is sometimes for the 32-bit version, so just make sure you pay attention to the **x86-64** suffix.

1. It is not absolutely necessary, but you should add your python distribution to your path. Doing
so will let you open a command prompt anywhere and start python by simply entering `python`. Note: To exit, enter `exit()` which return you back to the command prompt.

1. Anaconda doesn't come packaged with *OpenCV*.
To install it, I downloaded the wheel from http://www.lfd.uci.edu/~gohlke/pythonlibs/#opencv.
You need to choose whichever version matches your python distribution. For instance, I downloaded the wheel `opencv_python‑3.3.0+contrib‑cp36‑cp36m‑win_amd64.whl`, where
    - **3.3.0** denotes the *OpenCV* version (you probably don't need exactly this version)
    - **cp36** denotes my Python version (3.6). (Note: choose the version that matches your python version, particularly if you aren't using python 3.6)
    - **win** denotes the fact that I want the Windows distribution
    - **amd64** denotes the fact that I want the 64-bit distribution. Again, this must match your python version. If you have a 32-bit python distro, then you want the **win32** wheel. If you are unsure what version of python you are running, the easiest way is to typically open the command prompt and enter `python`. On my system, with the aforementioned Anaconda distribution, this returns
    
          C:\Users\bob>python
          Python 3.6.1 |Anaconda 4.4.0 (64-bit)| (default, May 11 2017, 13:25:24) [MSC v.1900 64 bit (AMD64)] on win32
          Type "help", "copyright", "credits" or "license" for more information.

      Type `exit()` to end the python session.

1. Once you have downloaded the wheel, you can install it by opening a command prompt in the directory where you downloaded the wheel and typing

        pip install opencv_python‑3.3.0+contrib‑cp36‑cp36m‑win_amd64.whl
        
Obviously, if you downloaded a different wheel, just insert the name of the wheel you downloaded.

1. Once OpenCV is installed, make sure that you have the right numpy version for it.
Since Anaconda might have been compiled with a different numpy than the OpenCV lib,
we need to check that everything is all right. To do that, open a command prompt and
enter `python`. Then once in the python environment, type `import cv2`. If
you get an error saying that you have the wrong numpy version, then you should `exit()` the python environment, and download
numpy from http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy using the same logic as the previous step. Once you download the wheel, you can first uninstall the old numpy:

        pip uninstall numpy

and then install the new version:

        pip install numpy‑1.13.1+mkl‑cp36‑cp36m‑win_amd64.whl

**Note for bare-bones users: You should also download numpy and install it using the steps described above since that distro will be much faster than the default version.**

1.  Finally, make sure that your distribution has *matplotlib*, which is used extensively in this repo for plotting and saving figures. To install it, you can simply use `pip`, that is, open a command prompt and enter
~~~
pip install matplotlib
~~~
Even if your distribution already had such an installation, the above command shouldn't harm anybody.
