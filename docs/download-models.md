# Download models

Download neural network models from google drive before starting using liveness prediction.

I have two ways to download models in easy way. You can choose any method.


## Option 1. Bash script:

Download trained neural network models by using bash script. Move inside directory where download_models.sh located and then run


<div class="termy">

```console
$ ./download_models.sh
```

</div>



## Option 2. Using python script:

Download trained neural network models by using python script. 

First you need to install gdown package.

<div class="termy">

```console
$ pip3 install gdown
```

</div>



Move inside directory where download_models.py located and then run.


<div class="termy">

```console
$ python3 download_models.py
```

</div>

After downloading models you can use liveness prediction sdk interface.

