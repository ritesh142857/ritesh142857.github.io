---
layout: default
title: NodeMCU Setup
---

## NodeMCU Firmware Setup
<hr>

* Download the NodeMCU firmware from:
{% highlight bash %}
https://github.com/nodemcu/nodemcu-firmware/releases
{% endhighlight %}

* Download esptool for flashing:
<br>Enter the folowing command:
{% highlight bash %}
git clone https://github.com/themadinventor/esptool.git
{% endhighlight %}

* Connect the NodeMCU to the computer and put it in Flash Mode.
	Now upload the firmware by entering the following:
	<br><br>(Assuming that /dev/ttyUSB0 is the serial port to which the NodeMCU is connected. If different, replace this with that one.)
{% highlight bash %}
sudo python esptool.py –port /dev/ttyUSB0 write_flash 0x00000 path_to_firmware.bin
{% endhighlight %}

* After the firmware is flashed, disconnect and reconnect the 	NodeMCU to the computer, launch Screen or Minicom and press 	reset on the NodeMCU.
