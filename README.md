# temp

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
