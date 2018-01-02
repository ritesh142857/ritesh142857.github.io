---
layout: default
title: NFS Shared Folder Setup
---

## NFS Shared Folder Setup
<hr>

First off, make sure the devices which will share folders are on the same network.

NFS file sharing is used here for sharing folders between <b>Server:PC1</b> and <b>Client:PC2</b>.
<br>
nfs must be setup on both the devices for sharing.

Make sure that the following packages are installed on the devices:

 - On Server:PC1 -> nfs-kernel-server
 - On Client:PC2 -> nfs-common

First set up the folder to be shared.

Let the folder to be shared be called <b>exampleFolder</b> (on Server:PC1)

<h2>On the server/host side:</h2>
Check whether nfs-kernel-server is installed or not by typing the following command:

{% highlight bash %}
dpkg -s nfs-kernel-server
{% endhighlight %}

If its not present, install it by typing:
{% highlight bash %}
sudo apt-get install nfs-kernel-server
{% endhighlight %}

Now the folder to share must be prepared. Assume the folder is present at the following location on Server:PC1
{% highlight bash %}
/home/userr/exampleFolder
{% endhighlight %}

Edit the following file: /etc/exports

Add the following line:

<b style="font-size: 14px;">(FolderToBeShared) (Client IP)(rw,sync,no_root_squash,no_subtree_check)</b>

for example, if the Client (Rpi) IP is 192.168.2.3,

<b style="font-size: 14px;">/home/userr/exampleFolder 192.168.2.3(rw,sync,no_root_squash,no_subtree_check)</b>

Save and exit.

Run the following command for adding our new export to the export table:

{% highlight bash %}
sudo exportfs -a
{% endhighlight %}

Then issue the following command for starting the nfs server:

{% highlight bash %}
sudo service nfs-kernel-server start
{% endhighlight %}

The shared folder is now visible to the Client:PC2.

<h2>On the Client Side:</h2>

Make sure that the package nfs-common is installed.

Now create a directory for mounting the shared folder. The directory that is used here is <b>/mnt/nfs/home/userr/exampleFolder</b>

To create the directory,

{% highlight bash %}
sudo mkdir /mnt/nfs/home/userr/exampleFolder
{% endhighlight %}

To mount,

{% highlight bash %}
sudo mount (HostIP):/home/userr/exampleFolder /mnt/nfs/home/userr/exampleFolder
{% endhighlight %}

The folder is now shared between Server:PC1 and the Client:PC2
