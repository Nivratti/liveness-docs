# Generating shared library

This tutorial will guide you to generate shared library from liveness lib phphcpp sdk(c++).

The 'liveness_lib_phpcpp' code is a wrapper code around crow server. 

## Steps:

### 1. Extract liveness lib sdk:

Unzip zipped sdk file.

<div class="termy">

```console
$ unzip liveness_lib_phpcpp.zip
```
</div>


### 2. Move inside root sdk folder:

Change your working directory to `liveness_lib_phpcpp` folder.

<div class="termy">

```console
$ cd liveness_lib_phpcpp
```
</div>


### 3. Generate .so file:

<div class="termy">

```console
$ mkdir -p build
$ cd build
$ cmake ..
$ make -j$(nproc)
```
</div>

This will generate .so file named **'libliveness.so'** file inside current build folder.
