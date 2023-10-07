# TP-Link Archer AC1300 Linux #

```shell
sudo su
```
```shell
git clone "https://github.com/RinCat/RTL88x2BU-Linux-Driver.git" /usr/src/rtl88x2bu-git
```
```shell
sed -i 's/PACKAGE_VERSION="@PKGVER@"/PACKAGE_VERSION="git"/g' /usr/src/rtl88x2bu-git/dkms.conf
```
```shell
dkms add -m rtl88x2bu -v git
```
```shell
dkms autoinstall
```

# D-Link-WiFi-Drivers #

D-Link WiFi Drivers For Windows, macOS and Linux

LINUX

A) Debian based OS - 

1.Install DKMS and other required tools
```shell
sudo apt-get install git linux-headers-generic build-essential dkms
```

2.Download rtl8192eu-linux-driver repository or clone it and change directory to path - 
```shell
git clone https://github.com/Mange/rtl8192eu-linux-driver
cd rtl8192eu-linux-driver
```

3.Add Driver to DKMS - 
```shell
sudo dkms add .
```

4.Build and Install the driver -
```shell
sudo dkms install rtl8192eu/1.0
```

5.Blacklist RTL8XXXU - 
```shell
echo "blacklist rtl8xxxu" | sudo tee /etc/modprobe.d/rtl8xxxu.conf
```

6.Force driver to be active from boot -
```shell
echo -e "8192eu\n\nloop" | sudo tee /etc/modules
```

7.Replug Issue Solution - 
```shell
echo "options 8192eu rtw_power_mgnt=0 rtw_enusbss=0" | sudo tee /etc/modprobe.d/8192eu.conf
```

8.Update changes to grub and initramfs -
```shell
sudo update-grub && sudo update-initramfs -u
```

9.Reboot from newly generated initramfs - 
```shell
systemctl reboot -i
```

10.Check Network module -
```shell
sudo lshw -c network
```
