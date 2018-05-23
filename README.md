# NXDNReflector

This section is a reminder of how to set up NXDNReflectors.

ALWAYS update your system before you start a new software install
It will be easiest to sudo su or su depending on your debian type operating system

apt-get update ; apt-get upgrade -y

You will usually require tools to compile and build packages 

apt-get install build-essential

Make sure git is installed

apt-get install git

Grab the source code

cd ~/Downloads
git clone https://github.com/g4klx/NXDNClients.git
cd NXDNClients

In this case we are installing NXDNReflector 

cd NXDNReflector
make

Edit the NXDNReflector.ini to suit your needs

If you want to run NXDNReflector as a daemon you need to set up a user, group

groupadd mmdvm
useradd mmdvm -g mmdvm -s /sbin/nologin
usermod mmdvm -G dialout

*Totally optional* Restart the server

shutdown -r now or reboot

Now go to the directory you installed to

cd Downloads
cd NXDNReflector

Start up the NXDNReflector

./NXDNReflector NXDNReflector.ini

Check and see if the daemon is running by looking at running processesses or by using netstat

netstat -and

You are looking for a similar line to see the port is being used by NXDNReflector such as this

udp        0      0 0.0.0.0:41400           0.0.0.0:*

You can also check for the running process

ps aux


Look for a similar line to the one as follows

mmdvm     4237  0.4  0.0  31908  1904 ?        Ssl  11:32   0:48 ./NXDNReflector NXDNReflector.ini


Thats it! NXDNReflector is up and running!
73
K2COP


