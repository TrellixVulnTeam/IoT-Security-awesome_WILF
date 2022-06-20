# awesome IoT Security [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

# Tools

[radare2](https://github.com/radareorg/radare2)

```
git clone https://github.com/radareorg/radare2
cd radare2
sys/install.sh
```

[ExplIoT](https://expliot.readthedocs.io/en/latest/)

```
pip3 install expliot --user
```

[Docker](https://www.docker.com/)

```
curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
echo 'deb [arch=amd64] https://download.docker.com/linux/debian buster stable' > /etc/apt/sources.list.d/docker.list
apt-get update
apt-get remove docker docker-engine docker.io
apt-get install docker-ce

Ater installation, Docker service will be started, but not enabled (i.e. it will not be started automatically after reboot). To start it:
systemctl start docker

To start Docker automatically upon reboot (do it on your own risk!):
systemctl enable docker

```

[IoTSecFuzz](https://gitlab.com/invuls/iot-projects/iotsecfuzz)

```
pip3 install --upgrade setuptools
pip3 install prompt-toolkit==3.0.2
git clone https://gitlab.com/invuls/iot-projects/iotsecfuzz.git
cd iotsecfuzz
python3 setup.py install
```

[Attify Badge](https://github.com/attify/attify-badge)

```
git clone https://github.com/attify/attify-badge
cd attify-badge
chmod +x install.sh
.\install.sh
```

[Baudrate.py](https://github.com/devttys0/baudrate)

```
git clone https://github.com/devttys0/baudrate
cd baudrate
chmod u+x baudrate.py

```

[Ghidra](https://ghidra-sre.org/)

```
sudo apt-get install openjdk-11-jdk
Download and extract ghidra
```

[fwanalyzer](https://github.com/cruise-automation/fwanalyzer)

```
git clone https://github.com/cruise-automation/fwanalyzer
cd fwanlyzer
docker build -t fwanalyzer .
docker run -it fwanalyzer -v /dir/on/host:/dir/inside/container
make deps
make
```

[Firmware Mod Kit](https://github.com/rampageX/firmware-mod-kit)

```
sudo apt-get install git build-essential zlib1g-dev liblzma-dev python-magic bsdmainutils
git clone https://github.com/rampageX/firmware-mod-kit

```

[Firmware Analysis Toolkit](https://github.com/attify/firmware-analysis-toolkit)

- Install Binwalk

```
git clone https://github.com/devttys0/binwalk.git
cd binwalk
sudo ./deps.sh
sudo python ./setup.py install
sudo apt-get install python-lzma  :: (for Python 2.x) 
sudo -H pip install git+https://github.com/ahupp/python-magic
```

- Setting up firmadyne

```
sudo apt-get install busybox-static fakeroot git kpartx netcat-openbsd nmap python-psycopg2 python3-psycopg2 snmp uml-utilities util-linux vlan qemu-system-arm qemu-system-mips qemu-system-x86 qemu-util
git clone --recursive https://github.com/firmadyne/firmadyne.git

cd ./firmadyne; ./download.sh
Edit firmadyne.config and make the FIRMWARE_DIR point to the current location of Firmadyne folder.

```

- Setting up the database

```
sudo apt-get install postgresql
systemctl start postgresql.service
systemctl enable postgresql.service 
sudo -u postgres createuser -P firmadyne, with password firmadyne
sudo -u postgres createdb -O firmadyne firmware
sudo -u postgres psql -d firmware < ./firmadyne/database/schema
```

- Setting up Firmware Analysis Toolkit

```
pip install pexpect
git clone https://github.com/attify/firmware-analysis-toolkit
mv firmware-analysis-toolkit/fat.py .
mv firmware-analysis-toolkit/reset.py .
chmod +x fat.py 
chmod +x reset.py
```

Adjust the paths to firmadyne and binwalk in fat.py and reset.py. Additionally, provide the root password. Firmadyne requires root privileges for some of its operations. The root password is provided in the script itself to automate the process.

```
# Configurations - change this according to your system
firmadyne_path = "/home/ec/firmadyne"
binwalk_path = "/usr/local/bin/binwalk"
root_pass = "root"
firmadyne_pass = "firmadyne"
```

- Setting up Firmware-mod-Kit

```
sudo apt-get install git build-essential zlib1g-dev liblzma-dev python-magic
git clone https://github.com/brianpow/firmware-mod-kit.git
```

Find the location of binwalk using which binwalk . Modify the file shared-ng.inc to change the value of variable BINWALK to the value of /usr/local/bin/binwalk (if that is where your binwalk is installed). .

- Setting up MITMProxy

```
pip install mitmproxy or apt-get install mitmproxy
```

- Setting up Firmwalker

```
git clone https://github.com/craigz28/firmwalker.git
```

- Running

```
python fat.py <firmware file>

```

- Provide the firmware filename as an argument to the script. If not provided, the script would prompt for it at runtime.

- The script will then ask you to enter the brand name. Enter the brand which the firmware belongs to. This is for pure database storage and categorisational purposes.

- The script would display the IP addresses assigned to the created network interfaces. Note it down.

- Finally, it will say that running the firmware. Hit ENTER and wait until the firmware boots up. Ping the IP which was shown in the previous step, or open in the browser.

- Congrats! The firmware is finally emulated. The next step will be to setup the proxy in Firefox and run mitmproxy.

To remove all analyzed firmware images, run

```
python reset.py 
```

[Firmwalker](https://github.com/craigz28/firmwalker)

```
git clone https://github.com/craigz28/firmwalker
```

[The Firmware Analysis and Comparison Tool (FACT)](https://github.com/fkie-cad/FACT_core)

```
git clone https://github.com/fkie-cad/FACT_core
./start_all_installed_fact_components
```

[Checksec.sh](https://github.com/slimm609/checksec.sh)

```
git clone https://github.com/slimm609/checksec.sh
```

[Firmadyne](https://github.com/firmadyne/firmadyne)

```
sudo apt-get install busybox-static fakeroot git dmsetup kpartx netcat-openbsd nmap python-psycopg2 python3-psycopg2 snmp uml-utilities util-linux vlan
git clone --recursive https://github.com/firmadyne/firmadyne.git
```

Install Binwalk

```
git clone https://github.com/devttys0/binwalk.git
cd binwalk
sudo ./deps.sh
sudo python ./setup.py install
For python2.x sudo apt-get install python-lzma
sudo -H pip install git+https://github.com/ahupp/python-magic
sudo -H pip install git+https://github.com/sviehb/jefferson
```

Database

```
sudo apt-get install postgresql
sudo -u postgres createuser -P firmadyne with password firmadyne
sudo -u postgres createdb -O firmadyne firmware
sudo -u postgres psql -d firmware < ./firmadyne/database/schema
```

Binaries

```
cd ./firmadyne; ./download.sh
```

QEMU

```
sudo apt-get install qemu-system-arm qemu-system-mips qemu-system-x86 qemu-utils

```

USAGE

- Set FIRMWARE_DIR in firmadyne.config to point to the root of this repository.

- Download a firmware image, e.g. v2.0.3 for Netgear WNAP320

```
wget http://www.downloads.netgear.com/files/GDC/WNAP320/WNAP320%20Firmware%20Version%202.0.3.zip
```

- Use the extractor to recover only the filesystem, no kernel (-nk), no parallel operation (-np), populating the image table in the SQL server at 127.0.0.1 (-sql) with the Netgear brand (-b), and storing the tarball in images

```
./sources/extractor/extractor.py -b Netgear -sql 127.0.0.1 -np -nk "WNAP320 Firmware Version 2.0.3.zip" images
```

- Identify the architecture of firmware 1 and store the result in the image table of the database.

```
./scripts/getArch.sh ./images/1.tar.gz
```

- Load the contents of the filesystem for firmware 1 into the database, populating the object and object_to_image tables.

```
/scripts/tar2db.py -i 1 -f ./images/1.tar.gz
```

- Create the QEMU disk image for firmware 1

```
sudo ./scripts/makeImage.sh 1
```

- Infer the network configuration for firmware 1. Kernel messages are logged to ./scratch/1/qemu.initial.serial.log

```
./scripts/inferNetwork.sh 1
```

- Emulate firmware 1 with the inferred network configuration. This will modify the configuration of the host system by creating a TAP device and adding a route

```
./scratch/1/run.sh
```

- The system should be available over the network, and is ready for analysis. Kernel messages are mirrored to ./scratch/1/qemu.final.serial.log

```
./analyses/snmpwalk.sh 192.168.0.100
./analyses/webAccess.py 1 192.168.0.100 log.txt
mkdir exploits; ./analyses/runExploits.py -t 192.168.0.100 -o exploits/exploit -e x (requires Metasploit Framework)
sudo nmap -O -sV 192.168.0.100
```

- The default console should be automatically connected to the terminal. Note that Ctrl-c is sent to the guest; use the QEMU monitor command Ctrl-a + x to terminate emulation. For the sample firmware above, you will first need to delete the file /etc/securetty from the filesystem to login as root with password password

- The following scripts can be used to mount/unmount the filesystem of firmware 1. Ensure that the emulated firmware is not running, and remember to unmount before performing any other operations.

```
sudo ./scripts/mount.sh 1
sudo ./scripts/umount.sh 1
```

[ByteSweep](https://gitlab.com/bytesweep/bytesweep)

```

Follow https://gitlab.com/bytesweep/bytesweep/blob/master/INSTALL.md
Install Docker
git clone https://gitlab.com/bytesweep/bytesweep.git
cd docker
./build-bytesweep.sh 
./start-bytesweep.sh 

```

[Volatility](https://www.volatilityfoundation.org/)

[RopGadget](https://github.com/JonathanSalwan/ROPgadget)

```
sudo pip install capstone
git clone https://github.com/JonathanSalwan/ROPgadget

Usage 1:
 ROPgadget.py

Usage 2:
 python setup.py install
 ROPgadget

Usage 3:
 pip install ropgadget
 ROPgadget
```

[Qemu](https://www.qemu.org/)

```
sudo apt-get install qemu-system-arm qemu-system-mips qemu-system-x86 qemu-utils
sudo apt-get install qemu
```

#### Android

[Jadx](https://github.com/skylot/jadx/releases)

[Dex2Jar](https://github.com/pxb1988/dex2jar)

[Apktool](https://ibotpeaches.github.io/Apktool/)

#### Network

[MitmProxy](https://mitmproxy.org/)

```
Download https://mitmproxy.org/downloads/

OR

sudo apt install python3-pip
sudo pip3 install -U pip
sudo pip3 install mitmproxy

```

[KillerBee](https://github.com/riverloopsec/killerbee)

```
apt-get install python-gtk2 python-cairo python-usb python-crypto python-serial python-dev libgcrypt-dev
git clone https://github.com/secdev/scapy
cd scapy
python setup.py install
git clone https://github.com/riverloopsec/killerbee
python setup.py install

```

[Attify ZigBee Framework](https://github.com/attify/Attify-Zigbee-Framework)

```
git clone https://github.com/attify/Attify-Zigbee-Framework
./installer.sh

```

[Ubertooth](https://github.com/greatscottgadgets/ubertooth)

[GnuRadio](https://www.gnuradio.org/)

```
apt install gnuradio
```

[GQRX](http://gqrx.dk/)

#### Hardware

[OpenOCD](https://installlion.com/kali/kali/main/o/openocd/install/index.html)

```
sudo apt-get install openocd

```

[Flashrom](https://www.flashrom.org/Flashrom)

```
sudo apt-get install flashrom
```

[minicom](https://linux.die.net/man/1/minicom)

[ubi_reader](https://github.com/jrspruitt/ubi_reader)
UBI Reader is a Python module and collection of scripts capable of extracting the contents of UBI and UBIFS images, along with analyzing these images to determine the parameter settings to recreate them using the mtd-utils tools.

```
sudo apt-get install liblzo2-dev
sudo pip install python-lzo

```

Latest Version

```
git clone https://github.com/jrspruitt/ubi_reader
cd ubi_reader
sudo python setup.py install

OR

wget https://github.com/crmulliner/ubi_reader/archive/master.zip -O ubireader.zip && unzip ubireader.zip && cd ubi_reader-master && python setup.py install
```

Or

```
sudo pip install ubi_reader
```

[uboot write](https://www.denx.de/wiki/view/DULG/Manual)

```
sudo apt-get install u-boot-tools
```

[elfutils](https://installlion.com/kali/kali/main/e/elfutils/index.html)

```
sudo apt-get install elfutils
```

[pax-utils](https://installlion.com/kali/kali/main/p/pax-utils/install/index.html)

```
sudo apt-get install pax-utils

```

[prelink](https://installlion.com/kali/kali/main/p/prelink/install/index.html)

```
sudo apt-get install prelink

```

[lddtree]

```
Already installed
```

[mtools,etools,squashfs-tools,cpio]

```
apt install e2tools mtools file squashfs-tools unzip python-setuptools cpio

```

## References Tools

- <https://github.com/V33RU/IoTSecurity101>
- <https://github.com/adi0x90/attifyos>
- <https://github.com/scriptingxss/EmbedOS>
- <https://medium.com/@airman604/installing-docker-in-kali-linux-2017-1-fbaa4d1447fe>

# Firmware

- [DVRF](https://github.com/praetorian-code/DVRF)
- [IoTGoat](https://github.com/scriptingxss/IoTGoat)

# OS

- [EmbedOS](https://github.com/scriptingxss/EmbedOS)
- [AttifyOs](https://github.com/adi0x90/attifyos)
- [Kali](https://www.kali.org/)
