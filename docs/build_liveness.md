# Build liveness

This tutorial will guide you to how to build liveness sdk.

We have used [Crow](https://github.com/ipkn/crow) framework to serve liveness models..


## Steps:

### 1. Extract liveness sdk:

Unzip sdk file.

<div class="termy">

```console
$ unzip liveness.zip
```
</div>


### 2. Move inside root sdk folder:

Change your working directory to `liveness/engine/cpp` folder.

<div class="termy">

```console
$ cd liveness/engine/cpp
```
</div>


### 3. Compile code:

<div class="termy">

```console
$ mkdir -p build
$ cd build
$ cmake ..
$ make -j$(nproc)
```
</div>

This will generate binary file named 'liveness_api' file inside current build folder.
