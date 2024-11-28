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

sudo apt-get install firmware-b43-installer

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

https://www.reddit.com/r/debian/comments/n3bkba/installing_wifi_nic_driver_during_netinst_install/


sudo apt install virt-manager qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils ovmf
-------------------------------------------
kontrollera virtualisering: ger tillbaka två siffor om ok, troligen: 44
egrep -c '(vmx|svm)' /proc/cpuinfo
--------------------------------------
Kör: så slipper man ange lösenord när man öppnar virtual machine manager
sudo usermod -aG libvirt,kvm $USER
----------------------
sudo nano /etc/default/grub



Ändra:
 
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
 
till:
 
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash intel_iommu=on iommu=pt ipv6.disable=1"



GRUB_CMDLINE_LINUX_DEFAULT="quiet intel_iommu=on iommu=pt ipv6.disable=1"

sudo update-grub

----------------------

starta, skriv in i shell:
virt-manager

-------------------------------------------------------------

sudo nano /etc/apt/sources.list

sudo apt-get update

deb http://deb.debian.org/debian/ bookworm main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm main non-free-firmware










___________________________________________________________________________________________________________________________
To solve:  Virtualized Intel VT-X/EPT is not supported on this platform
kör i sökfönstret: appwiz.cpl

core isolation - kärnisolering: av(det var redan av så jag ändrade inte)

kör i sökfönstret: Gpedit.msc

It didn't work for me in windows 11 and it should be done!!!
For Microsoft Windows 10 Pro & above:
Edit group policy (gpedit)
Go to Local Computer Policy > Computer Configuration > Administrative Templates > System
Double Click on Device Guard on the right hand side to open.
Double Click on "Turn On Virtualization Security" to open a new window
It would be "Not Configured", Select "Disable" and click "Ok"
Close the Group Policy Editor.
Restart the system

_________________________________________________________________________________________________________________________


Is your Windows 10 licence based on an OEM licence (came pre-installed on a PC) or Retail (purchased separately to a PC)

If it is a Retail licence, then it will have transfer rights to a new PC, if it is OEM it will not . .. 

Which Kind of License I Use
Sometimes, you may want to know which kind of license you are using. If so, please refer to the following steps:
Step 1: Open a Command Prompt or PowerShell. Then, type in “Slmgr /dli” or “slmgr /dlv” and press Enter.
Step 2: Wait a few seconds for the Windows Script Manager to appear and tell you which license type you have.


https://www.partitionwizard.com/clone-disk/win10-oem-vs-retail.html



get product key:
wmic path softwarelicensingservice get OA3xOriginalProductKey 


---------------------------------------------------------------------------------------
router VM:

ip -c a

sudo systemctl restart networking

sudo ip link set enp8s0 up  #enp8s0 är namnet från kommandot ip -c a  2:

sudo apt remove iptables

sudo apt install nftables #Skriva firefall regler

sudo nft list ruelset

sudo apt install
sudo apt install dnsmasq
sudo apt install wpasupplicant


sudo systemctl enable serial-getty@ttyS0.service
sudo systemctl start serial-getty@ttyS0.service



host:

virsh console router

sudo shutdown now
lspci -nn   #Listar alla pci express enheter på datorn
lspci -nn | grep -i wifi  #listar wifi

--------------------------------------------------------------------

This is confirmed as working on Ubuntu 14.04 32-bit. The laptop I fixed is 32-bit, and it won't run Ubuntu 14.10.

This should also work for Ubuntu 14.10 though, and for all Broadcom cards that are supported. Almost all Broadcom cards are supported though, so cross your fingers :)

For a fresh installation, run these commands one-by-one in the terminal:

sudo apt-get purge bcmwl-kernel-source
sudo apt-get install linux-firmware-nonfree
sudo apt-get install firmware-b43-installer
sudo modprobe -r b43 && sudo modprobe b43  
sudo reboot  
You will get no errors this time on startup, and your wireless will work. If it doesn't work, please edit your question to add the results of running some diagnostics:

dmesg | grep -e b43 -e wlan
rfkill list all
-----------------------------------------------------------------------
1

Please download this file and transfer it to the desktop: http://mirrors.kernel.org/ubuntu/pool/multiverse/l/linux-firmware-nonfree/linux-firmware-nonfree_1.14ubuntu1_all.deb Now, open a terminal and do:

sudo dpkg -i ~/Desktop/linux-firmware*.deb
sudo modprobe -r b43 && sudo modprobe b43
Your wireless should now be working. If it is not, please edit your question to add some diagnostics:

dmesg | grep -e b43 -e wlan
rfkill list all
-------------------------------------------------------------------------------------------

sudo dmesg | grep -e DMAR -e IOMMU

lägga till: options vfio_iommu_type1 allow_unsafe_interrupts=1
i filen: sudo nano /etc/modprobe.d/vfio.conf

ip link show
ip addr show
hostname -I

/etc/resolv.conf

sudo apt install iputils-ping #Installera ping

----------------------------------------------------------------------------------------------------------
Skapa ett skript:

touch script.sh
chmod +x script.sh
nano script.sh

-----------------------------------------
echo This is myscript.h running
date >> /var/log/sys-start.log
sudo virsh nodedev-dettach pci_0000_03_00_0 &>> /var/log/sys-start.log
sudo virsh start router &>> /var/log/sys-start.log
echo ---------------------------- >> /var/log/sys-start.log
----------------------------------------

Save the changes, and run the shell script by typing in

/home/deb/Documents/myscript.sh
./script.sh

skapa logfil:
sudo touch /var/log/sys-start.log
sudo chmod 777 /var/log/sys-start.log
------------------------------------------------------------------------------------------------------------

Starta Ubuntu i shell:

/etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT=”quiet splash”  remove ”quiet splash” 
GRUB_CMDLINE_LINUX=”text”
GRUB_TERMINAL=console

sudo update-grub

There is one further step for Ubuntu versions which use systemd by default. It's necessary to change the default target from "graphical" target to "multi-user" target.
sudo systemctl set-default multi-user.target

You can always revert to desktop boot later by restoring GRUB config file and running:
sudo systemctl set-default graphical.target

-----------------------------------------------------------------------------
/etc/systemd/network/ 

Virtuell brygga:

[Match] 
Name=work 

[Network] 
DHCP=yes 


[NetDev] 
Name=work 

Kind=bridge 

-------------------------------------
sudo systemctl enable systemd-resolved.service
sudo systemctl restart systemd-resolved.service
--------------------------------------------------------

/etc/dnsmasq.conf 
interface=enp0s8
dhcp-range=enp0s8,10.0.0.2,10.0.0.100
dhcp-option=enp0s8,3,10.0.0.1
dhcp-option=enp0s8,6,1.1.1.1 

-----------------------------------------------------------

#filen nftables :

nano chmod nftables

---------------------------------------------------------
#!/usr/sbin/nft -f 

flush ruleset 

table inet filter {
        chain input {
                type filter hook input priority filter; policy drop;

                #established/related connections:
                ct state established,related accept
    
                # loopback interface
                iifname lo accept
    iifname enp0s8 accept
                # icmp
                icmp type echo-request accept


                #Allow incoming http and https from approved IP range>
                log prefix "Dropped Input: "
              

               
        }
        chain forward {
                # Drop everything (assumes this device is not a route>
                type filter hook forward priority filter; policy accept;

                
        }
        chain output {
                type filter hook output priority filter; policy accept;

        }
}
table ip nat {
  chain prerouting {
    type nat hook prerouting priority filter; policy accept;
  }
  chain postrouting {
    type nat hook postrouting priority srcnat; policy accept;
    oifname wlp1s0 masquerade
  }
} 

sudo chmod + /etc/nfttables/main.nft
sudo nft -f /etc/nfttables/main.nft
sudo systemctl enable nftables
sudo systemctl start nftables

https://jonamiki.com/2020/01/29/dnsmasq-failed-to-create-listening-socket-for-port-53-address-already-in-use/
---------------------------------------------------------

Invoke-HardeningKitty -Mode HailMary -Log -Report -FileFindingList .\lists\finding_list_0x6d69636b_machine.csv

---------------------------------------------------------------------------------------------------------------

Kali:
sudo apt update
sudo apt upgrade
sudo apt install netexec python3-impacket python3-certipy bloodhound ldap-utils hashcat neo4j mimikatz
burpsuite fzf bat ripget fd-findhtop eza sqlmap
bloodhound(windows AD) 
ldap-utils(ldapsearch sökningar i AD ldap) 
mimikatz(AD,tex kerberos attacker)
burpsuite #För webben
sqlmap #scanna/breaka databaser
sudo apt install fzf  #Leta efter saker på maskinen, tex filer eller text
sudo apt install bat  #variant på cat
sudo apt install ripgrep #variant på grep, kommando: rg import 	--no-ignore #Tar med gitignore filer -1 #inte case sensitive
sudo apt install fd-find  #varinat på find, kommando: fdfind temp #söka i datorn
sudo apt install htop  #aktiviteshanterare
sudo  tmux  #finns från början  kommando:ctrl-b 1 0, variera mellan två terminaler
sudo apt install eza #varinat på ls  kommando: eza -1 --icons=auto


vim .zshrc  #lägga till alias :tex:  alias update="sudo apt update && sudo apt upgrade"  alias c="clear" alias ls="ls -l"
	    #lägga till egen path: export PATH="$PATH:$Home/bin"  #Skapat ett eget bin i home där jag lägger egna verktyg mm	
source .zshrc #ladda om filen
