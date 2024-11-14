# temp

https://www.reddit.com/r/debian/comments/178bbg2/why_arent_all_packages_from/



deb http://deb.debian.org/debian/ bookworm main contrib non-free non-free-firmware

deb http://security.debian.org/debian-security/ bookworm-security main contrib non-free non-free-firmware

deb http://deb.debian.org/debian/ bookworm-updates main contrib non-free non-free-firmware

deb http://deb.debian.org/debian bookworm-backports main contrib non-free non-free-firmware


sudo nano /etc/apt/sources.list

sudo apt-get update

-------------------------------------------------------------------------------------------------------

https://wiki.debian.org/SourcesList#Example_sources.list

sudo nano /tec/apt/sources.list

deb http://deb.debian.org/debian/ bookworm main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm main non-free-firmware

sudo apt install virt-manager qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils ovmf
-------------------------------------------
kontrollera virtualisering: ger tillbaka två siffor om ok, troligen: 44
egrep -c '(vmx|svm)' /proc/cpuinfo
--------------------------------------
Kör: så slipper man ange lösenord när man öppnar virtual machine manager
sudo usermod -aG libvirt,kvm $USER
----------------------
sudo nano /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="quiet intel_iommu=on iommu=pt ipv6.disable=1"

sudo update-grub

sudo apt install git-all
----------------------

starta, skriv in i shell:
virt-manager
-------------------------------------------------------------

routerVM:

sudo apt install make build-essential
sudo apt update && sudo apt install -y build-essential dkms

unpack your source pakage to some folder

go to this folder
do this:

$ ./configure
$ make
$ sudo make install
After installation you can load just compiled module by enter command:

$ sudo insmod your_module.so
$ ifconfig eth0 up


