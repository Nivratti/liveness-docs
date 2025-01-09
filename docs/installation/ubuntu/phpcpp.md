# phpcpp

The PHP-CPP library is a C++ library for developing PHP extensions. It offers a collection of well documented and easy-to-use classes that can be used and extended to build native extensions for PHP. The full documentation can be found on [http://www.php-cpp.com](http://www.php-cpp.com "http://www.php-cpp.com").


## Required versions:
- php >= 7.1
- gcc with c++11 support
- cmake >= 3.15
- make


##  Steps:

To install the latest phpcpp, follow these steps:

## 1) Install php -devel:

<div class="termy">

```console
$ sudo apt-get install php-dev
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