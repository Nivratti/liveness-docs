# phpcpp

The PHP-CPP library is a C++ library for developing PHP extensions. It offers a collection of well documented and easy-to-use classes that can be used and extended to build native extensions for PHP. The full documentation can be found on [http://www.php-cpp.com](http://www.php-cpp.com "http://www.php-cpp.com").


## Required versions:
- php >= 7.1
- gcc with c++11 support
- cmake >= 3.15
- make


##  Steps:

To install the latest phpcpp, follow these steps:

## 1) install GCC 8:

First check installed gcc version using command `$ gcc --version`. If it's less than 8 follow below steps.

<div class="termy">

```console
$ sudo yum update
$ yum install devtoolset-8-gcc devtoolset-8-gcc-c++
$ source scl_source enable devtoolset-8
$ scl enable devtoolset-8 -- bash
```

</div>


## 2) Clean older php versions:

First check is their any installed php version using command `$ php --version`. If it's less than 7.1 remove it.

<div class="termy">

```console
$ yum list installed | grep php
$ yum -y remove php*

```

</div>


## 3) Install php7.2:

<div class="termy">

```console
$ sudo yum install epel-release
$ sudo yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
$ sudo yum install yum-utils
$ sudo yum-config-manager --enable remi-php72
$ sudo yum update
$ sudo yum install php
```
</div>


## 4) Install php -devel:

<div class="termy">

```console
$ yum install php-devel
```
</div>


## 5) Install PHP-CPP:

<div class="termy">

```console
$ git clone https://github.com/CopernicaMarketingSoftware/PHP-CPP.git
$ make
$ sudo make install
```
</div>