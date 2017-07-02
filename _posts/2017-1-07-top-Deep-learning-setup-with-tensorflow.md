---
layout: post
title:  "Tensorflow setup for Deep Learning"
date:   2017-07-15 18:34:10 +0700
categories: [html, ruby]
---

Since they came up with the deep learning idea that all time TERMINATOR seems possible, not exactly the apocalypse part but the cool autonomous and intelligent humanoids part. We will be configuring Tensorflow library on UBUNTU 14.4 on top of Anaconda3-4.2.0. At present there is a latest version available but if you are a newbie and want to explore and learn about deep learning you will be needing to playaround with lots of opensource repos and examples that are produced by the Tensorflow comunity and those projects will work well with the old most stable and tested version of tensorflow. So lets install it...   



## 1. [Install Anaconda]( Run the following commands in your terminal)

GO TO : https://repo.continuum.io/archive/
DOWNLOAD Anaconda3-4.2.0 FOR YOU PLATFORM OR ANY VERSION
```sh
//RUN THE FOLLOWING IN YOUR TERMINAL
cd Downloads
bash Anaconda3-4.4.0-Linux-x86_64_2.sh 

```

## 2. [Create a new environment]( Run the following commands in your terminal)

```sh
conda create -n mycondaenv
source activate mycondaenv
```

## 3. [Install Tensorflow-0.11.0]( Run the following commands in your terminal)


```sh
export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0-cp35-cp35m-linux_x86_64.whl
pip install --ignore-installed --upgrade $TF_BINARY_URL
```


There you go you have a deep learning setup on you machine, HAPPY! CODING...




