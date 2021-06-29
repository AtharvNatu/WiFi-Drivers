# D-Link-WiFi-Drivers
D-Link WiFi Drivers For Windows, macOS and Linux

LINUX

Debian based OS - 

1. Install DKMS and other required tools -

sudo apt-get install git linux-headers-generic build-essential dkms

2. Download rtl8192eu-linux-driver repository or clone it and change directory to path -
 
git clone https://github.com/Mange/rtl8192eu-linux-driver

cd rtl8192eu-linux-driver

3. Add Driver to DKMS - 

sudo dkms add .
