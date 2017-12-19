---
layout: default
title: NFS Shared Folder Setup
---

## NFS Shared Folder Setup
<hr>

First off, make sure the devices which will share folders are on the same network.

NFS file sharing is used here for sharing folders between the Raspberry Pi and the PC. The nfs must be setup on both the devices for sharing.

Make sure that the following packages are installed on the devices:

   PC1 (host): nfs-kernel-server
   <br>PC2: nfs-common

Setting up the folders to be shared:

1. The folder being shared must be the NetBeans project folder
(Ex: CppApplications_1)

2. On the host side:
Check whether nfs-kernel-server is installed or not by typing the following command:

{% highlight bash %}
dpkg -s nfs-kernel-server
{% endhighlight %}

If its not present, install it by typing:
{% highlight bash %}
sudo apt-get install nfs-kernel-server
{% endhighlight %}

Now the folder to share must be prepared. Assume the folder is present at the following location:
{% highlight bash %}
/home/userr/NetBeansProjects/CppApplication_1
{% endhighlight %}

Edit the following file: /etc/exports

Add the following line:

(FolderToBeShared) (Client IP)(rw,sync,no_root_squash,no_subtree_check)

for example, if the Client (Rpi) IP is 192.168.2.3,

/home/userr/NetBeansProjects/CppApplication_1 192.168.2.3(rw,sync,no_root_squash,no_subtree_check)

Save and exit.

Run the following command for adding our new export to the export table:

{% highlight bash %}
sudo exportfs -a
{% endhighlight %}


Then issue the following command for starting the nfs server:

sudo service nfs-kernel-server start

The shared folder is now visible to the Raspberry Pi.

On the Client Side:

Make sure that the package nfs-common is installed.

Now create a directory for mounting the shared folder. The directory that is used here is /mnt/nfs/home/userr/NetBeansProjects/CppApplication_1

To create the directory,

sudo mkdir /mnt/nfs/home/userr/NetBeansProjects/CppApplication_1

To mount,

sudo mount (HostIP):/home/userr/NetBeansProjects/CppApplication_1 /mnt/nfs/home/userr/NetBeansProjects/CppApplication_1

The folder is now shared between the PC and the Rpi.
