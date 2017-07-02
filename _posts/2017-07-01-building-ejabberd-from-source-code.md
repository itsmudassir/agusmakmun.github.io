---
layout: post
title:  "Building Ejabberd From Source Code"
date:   2017-07-01 03:43:45 +0700
categories: [xmpp, erlang]
---

Recently we went through the deployment of Ejabberd in my [previous blog post][previous blog post]. If you want to add your own modules to ejabberd server you will need to build the source code of Ejabberd. Here is how i did it.



## 1. [GET EJABBERD REPO]()

```sh
sudo apt-get install git
cd ~
git clone https://github.com/processone/ejabberd.git
```


## 2. [INSTALL AUTOMAKE AND GENERATE A CONFIGURE FILE]( Run the following commnds in your terminal)

```sh
sudo apt-get install automake
cd ejabberd/
./autogen.sh
```

## 3. [EJABBERD WILL NEED ERLANG INSTALL IT]( Run the following commnds in your terminal)

```sh
wget http://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb
sudo dpkg -i erlang-solutions_1.0_all.deb

wget http://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc
sudo apt-key add erlang_solutions.asc

sudo apt-get update
sudo apt-get install erlang
```

## 4. [ERLANG SOURCE ALSO NEEDS C++ AND RUN THR CONFIGURE SCRIPT IN EJABBERD DIR]( )
 
```sh
sudo apt-get install build-essential

./configure
```


## 5. [INSTALL THE FOLLOWING DEPENDENCIES]( )

```sh
sudo apt-get install libssl-dev
sudo apt-get install libyaml-dev
sudo apt-get install libexpat1-dev
```

## 6. [INSTALL]( )
Inside the Ejabberd directory enter the following commands

```sh
make
make install
```



Related Posts : 
[https://gist.github.com/dirkmoors/4acc602fedffe4768f39]

[http://www.blikoontech.com/networking/how-to-install-ejabberd-on-linux-ubuntu]

[https://alexpetroaica.wordpress.com/2015/09/17/how-to-compile-ejabberd-from-sources/]



 [previous blog post]:https://itsmudassir.github.io/xmpp/erlang/2017/07/02/Deploy-xmpp-server-on-aws.html

 [https://gist.github.com/dirkmoors/4acc602fedffe4768f39]:https://gist.github.com/dirkmoors/4acc602fedffe4768f39

 [http://www.blikoontech.com/networking/how-to-install-ejabberd-on-linux-ubuntu]:http://www.blikoontech.com/networking/how-to-install-ejabberd-on-linux-ubuntu

 [https://alexpetroaica.wordpress.com/2015/09/17/how-to-compile-ejabberd-from-sources/]:https://alexpetroaica.wordpress.com/2015/09/17/how-to-compile-ejabberd-from-sources/

 
