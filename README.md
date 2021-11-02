# D-Link-WiFi-Drivers
D-Link WiFi Drivers For Windows, macOS and Linux

LINUX

A) Debian based OS - 

1.Install DKMS and other required tools - 
sudo apt-get install git linux-headers-generic build-essential dkms

2.Download rtl8192eu-linux-driver repository or clone it and change directory to path - 
git clone https://github.com/Mange/rtl8192eu-linux-driver
cd rtl8192eu-linux-driver

3.Add Driver to DKMS - 
sudo dkms add .

4.Build and Install the driver - 
sudo dkms install rtl8192eu/1.0

5.Blacklist RTL8XXXU - 
echo "blacklist rtl8xxxu" | sudo tee /etc/modprobe.d/rtl8xxxu.conf

6.Force driver to be active from boot - 
echo -e "8192eu\n\nloop" | sudo tee /etc/modules

7.Replug Issue Solution - 
echo "options 8192eu rtw_power_mgnt=0 rtw_enusbss=0" | sudo tee /etc/modprobe.d/8192eu.conf

8.Update changes to grub and initramfs - 
sudo update-grub && sudo update-initramfs -u

9.Reboot from newly generated initramfs - 
systemctl reboot -i

10.Check Network module - 
sudo lshw -c network
