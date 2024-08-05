# jetpack6-joysitck manual install

## environment
- jetpack 6(L4T-36.3.0)
- Release: 5.15.136-tegra
- H/W model: jetson agx orin dev. kit

## install
```
sudo apt update
sudo apt upgrade

git clone https://github.com/paroj/xpad.git
cd xpad
make
sudo mkdir /lib/modules/$(uname -r)/kernel/drivers/input/joystick
sudo cp xpad.ko /lib/modules/$(uname -r)/kernel/drivers/input/joystick
sudo depmod -a
sudo modprobe xpad
sudo dmesg | grep xpad

ls -l /dev/input/js0 # check js0
jstest /dev/input/js0 # run it!
```
