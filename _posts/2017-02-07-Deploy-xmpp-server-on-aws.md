---
layout: post
title:  "Xmpp Chat Backend Deployment on AWS"
date:   2017-07-02 18:34:10 +0700
categories: [xmpp, erlang]
---

The year 2017 is all about chatbots. For having a live chat support on your website you either need to embed a service such as WebsiteAlive or any other competetor and pay for their service or you can be smart and deploy your own as open source universe is always there for you. Today we will deploy an open source chat backend called EJABBERD, it is one of the best scalable chat backends.



## 1. [Setup AWS VM]()

-> Launch an EC2 instance in the desired configuration. In order to stay within my Free Tier, I chose the smallest available configuration using EBS and running Amazon’s custom Linux image

-> Configure the security groups for the newly created instance. We need to allow SSH-access as well as open the ports used by XMPP/ejabberd. In default configuration, ejabberd is using TCP ports 5266, 5280 and 5269. For ease just allow all ports(can be insecure).
 
-> Connect to your instance using SSH 

## 2. [Download and Install The Setup]( Run the following commnds in your terminal)

```sh
mkdir Downloads
wget -O Downloads/ejabberd-13.12-linux-x86_64-installer.run http://www.process-one.net/downloads/downloads-action.php?file=/ejabberd/13.12/ejabberd-13.12-linux-x86_64-installer.run
chmod +x Downloads/ejabberd-13.12-linux-x86_64-installer.run
sudo Downloads/ejabberd-13.12-linux-x86_64-installer.run
```

## 3. [Installation Instructions]( Run the following commnds in your terminal)

-> In the setup for ejabberd server domain, enter the public DNS of your instance e.g. ec2-###-###-###-###.eu-west-1.compute.amazonaws.com.



## 4. [Configure ejabberd.cfg]( )
 
 ```sh
 %% Admin user
{acl, admin, {user, "adminname", "yoursite.com"}}.
%% Hostname
{hosts, ["yoursite.com"]}.
```


## 5. [Start The Service]( )

```sh
sudo /opt/ejabberd-13.12/bin/ejabberdctl start  
sudo /opt/ejabberd-13.12/bin/ejabberdctl status
```

## 6. [Testing]( )
 Your site will be live at  http://yoursite.com:5280/admin




Related Posts
[http://www.rookidsapp.com/blog/how-to-install-ejabberd-xmpp-server-on-ubuntu-aws/]

[https://androidtechieblog.wordpress.com/2015/12/27/ejabberd-using-amazon-ec2-aws-and-xml-rpc-for-android-xmpp-chat-part-1/]


[http://www.sebastianhaas.at/installung-running-ejabberd-aws-ec2-instance/]



 [http://www.rookidsapp.com/blog/how-to-install-ejabberd-xmpp-server-on-ubuntu-aws/]: http://www.rookidsapp.com/blog/how-to-install-ejabberd-xmpp-server-on-ubuntu-aws/

 [https://androidtechieblog.wordpress.com/2015/12/27/ejabberd-using-amazon-ec2-aws-and-xml-rpc-for-android-xmpp-chat-part-1/]:https:/androidtechieblog.wordpress.com/2015/12/27/ejabberd-using-amazon-ec2-aws-and-xml-rpc-for-android-xmpp-chat-part-1/

 [http://www.sebastianhaas.at/installung-running-ejabberd-aws-ec2-instance/]:http://www.sebastianhaas.at/installung-running-ejabberd-aws-ec2-instance/

 
