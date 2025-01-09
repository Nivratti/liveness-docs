# opencv

The OpenCV package is available from the CentOS 7 standard repositories, but is it pretty outdated. We need to install the latest stable version of OpenCV with dnn module.


## Required versions:
- Openncv 4.4.0 or greater
- gcc with c++11 support
- cmake >= 3.15
- make

##  Steps:

To install the latest OpenCV version from the source, follow these steps:

### 1. Setup folder to process opencv installation:

We are going to  create installation directory.


<div class="termy">

```console
$ cvVersion="master"

$ rm -rf opencv
$ rm -rf opencv_contrib

$ mkdir installation
$ mkdir installation/OpenCV-"$cvVersion"
```

</div>


Finally, we will be storing the current working directory in cwd variable. We are also going to refer to this directory as **OpenCV_Home_Dir** .

<div class="termy">

```console
$ cwd=$(pwd)
```

</div>


### 2. Install packages

Next we are going to install libraries and packages that will be required for OpenCV installation.

<div class="termy">

```console
$ sudo yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
$ sudo yum -y install epel-release
$ sudo yum -y install git gcc gcc-c++ cmake3
$ sudo yum -y install qt5-qtbase-devel
$ sudo yum install -y python34 python34-devel python34-pip
$ sudo yum install -y python python-devel python-pip

$ sudo yum -y install python-devel numpy python34-numpy
$ sudo yum -y install gtk2-devel

$ sudo rpm --import http://li.nux.ro/download/nux/RPM-GPG-KEY-nux.ro
$ sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
$ sudo yum install -y ffmpeg
$ sudo yum install -y ffmpeg-devel

$ sudo yum install -y libpng-devel
$ sudo yum install -y openexr-devel
$ sudo yum install -y libwebp-devel
$ sudo yum -y install libjpeg-turbo-devel 
$ sudo yum install -y freeglut-devel mesa-libGL mesa-libGL-devel
$ sudo yum -y install libtiff-devel 
$ sudo yum -y install libdc1394-devel --skip-broken
$ sudo yum -y install tbb-devel eigen3-devel
$ sudo yum -y install boost boost-thread boost-devel
```

</div>


### 3. Clone GitHub Repositories

We will next clone opencv and opencv_contrib GitHub repositories.

<div class="termy">

```console
$ git clone https://github.com/opencv/opencv.git
$ cd opencv
$ git checkout $cvVersion
$ cd ..

$ git clone https://github.com/opencv/opencv_contrib.git
$ cd opencv_contrib
$ git checkout $cvVersion
$ cd ..
```

</div>


### 4. Build OpenCV

Now comes the part we have been so eagerly waiting for – building OpenCV. First, we will create **build** directory.

<div class="termy">

```console
$ cd opencv
$ mkdir build
$ cd build
```
</div>


Next, we will use CMake and make to build OpenCV.

<div class="termy">

```console
$ cmake3 -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D OPENCV_GENERATE_PKGCONFIG=ON \
-D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
-D ENABLE_CXX11=ON \
-D BUILD_EXAMPLES=ON ..

$ make -j$(nproc)
$ make install

$ cd $cwd

```
</div>

