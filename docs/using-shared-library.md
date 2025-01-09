# Use shared library

To use generated shared library we need to put it inside php configuration folder.


## 1. Get php extension directory:

<div class="termy">

```console
$ php -i | grep extension_dir
```
</div>


## 2. Copy generated liveness sdk shared library(.so) file :

Replace "/php/extension_dir/path" text with actual path obtained from step 1.

<div class="termy">

```console
$ cp /path/to/libliveness.so /php/extension_dir/path
```
</div>


## 3. Get php configuration folder(conf.d) :

Get path of php.ini on your system. the parent folder of 'php.ini' contains 'conf.d' folder

<div class="termy">

```console
$ php -i | grep 'Configuration File'
```
</div>


## 4. Copy liveness.ini file :

The file liveness.ini located inside 'liveness_lib_phpcpp' folder.

Replace "/php/configuration/folder/path" text with actual path obtained from step 3.

<div class="termy">

```console
$ cp /path/to/liveness.ini/file /php/config/folder/path
```
</div>

Example:

<div class="termy">

```console
$ sudo cp /home/nivratti/liveness_lib_phpcpp/liveness.ini  /etc/php/7.2/cli/conf.d/
```
</div>