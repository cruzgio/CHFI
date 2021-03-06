# CHFI
Repositorio con recursos relacionados a los capitulos de la certificacion CHFIv10 de EC-Council
Este trabajo se encuentra bajo una licencia [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

Repository with information related to the CHFIv10 certification chapters
This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

## Demos

### Informacion EFI / EFI Info - Linux 
efibootmgr -v

### Particiones y Sistema de Archivos / Partitions and Filesystem - Linux
df -Th

### Superblocks - Linux
dumpe2fs [nombre_de_disco (/dev/algo)] | grep -i superblock

### Sleuthkit
```
mmls -V
fsstat -f list
fsstat [archivo de imagen / image file]
istat -f fat [archivo de imagen / image file] 2 
istat -f fat [archivo de imagen / image file] 3 
fls [archivo de imagen / image file]
img_stat -i list
img_stat -i raw [archivo de imagen / image file]
```

### Editor Hexadecimal / Hex Editor - Linux
```
xxd quote-7.jpg
xxd sample_640×426.bmp | less
xxd giphy.gif | less
xxd chfi-brochure.pdf | less
xxd RFQ\ for\ Training\ Services\ for\ Cyber\ security-CND\ and\ CHFI\ FINAL.doc | less
```

### dcfldd
```
dcfldd if=/dev/sdb1 of=/media/disk/test_image.dd hash=md5,sha1 hashlog=/media/disk/hashlog.txt
dcfldd if=/dev/sdb1 vf=/media/disk/test_image.dd verifylog=/media/disk/verifylog.txt
```

### NTFS - Linux
sudo parted -l

### PowerShell Hash
```
Get-FileHash [nombre_del_archivo / file_name]
Get-FileHash [nombre_del_archivo / file_name] -Algorith MD5
```

### quemu-img 
```
qemu-img convert –f <file format> <Source_Image_filename> –O vhdx <destination_filename.vhdx>
```

### Identificacion de Imagen / Image Identification
fdisk -l [nombre_del_archivo / file_name]

### Papelera de Reciclaje / Recycle Bin
dir /s/a <letradelaunidad / ddriveletter>:\$Recycle.Bin

### NTFS Data Stream
```
gci -recurse | % { gi $_.FullName -stream * } | where stream -ne ':$Data' - Powershell
```

### Dispositivos USB conectados / Connected USB devices
Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Enum\USB\*\*\ 
Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Enum\USB\*\*\ | Select FriendlyName

### Windows Forensics

### Informacion Volatil / Volatile Information
```
date /t & time /t
net sessions (admin)
PsLoggedon64.exe (Sysinternals)
logonsessions64.exe (Sysinternals + admin)
net file (admin)
nbtstat -c
netstat -ano
netstat -r
tasklist /v
pslist.exe (Sysinternals)
pslist.exe -x (Sysinternals)
listdlls.exe (Sysinternals)
handle.exe (Sysinternals)
handle.exe -p [#_de_proceso / process_number] (Sysinternals)
netstat -o
ipconfig /all
wmic service list brief
wmic service list brief | more
doskey /history
net share
```

### Revision del Sistema de Archivos / Examining File Systems
```
En la carpeta / Under WINDOWS\system32 
dir /o:d
```

### Windows.edb
\ProgramData\Microsoft\Search\Data\Applications\Windows\Windows.edb

### Process-Dump
```
Primera ejecucion en un sistema limpio / Before first execution in a clean system
pd -db gen
pd -db genquick

tasklist

pd64.exe -system
pd64.exe -closemon
pd64.exe -p chrome.exe
pd -pid 419
```

### LECmd
LECmd.exe -d C:\Users\[nombredelusuario / username]\AppData\Roaming\Microsoft\Windows\Recent
LECmd.exe -f C:\Users\[nombredelusuario / username]\AppData\Roaming\Microsoft\Windows\Recent\[nombredelarchivo / filename]

### JumpList
cp C:\Users\[nombredelusuario / username]\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations\* [carpetadetrabajo / workfolder]
cp C:\Users\[nombredelusuario / username]\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations\* [carpetadetrabajo / workfolder]

### wevtutil
wevtutil el
wevtutil gl [nombredellog / logname]

### Linux Forensics 

### Informacion Volatil / Volatile Information
```
hostname
date
cat /etc/timezone
date +%s (epoch)
uptime
top
ip a
ifconfig [interfaz / inteface]
netstat -a | less
netstat -anp
netstat -i
netstat -r
ip r
lsof (sudo)
lsof -u [usuario / username]
mount
df
lsmod
modinfo [modulo del kernel / kernel module]
id [usuario / username]
ausearch -ui [uid] --interpret
readelf --file-header [ruta / path]
ps -ef
ps -auxf
ps -r
ps -x
cat /proc/partitions
cat /proc/swaps
dmesg
```
### Informacion del Sistema / System Information
```
cat /proc/cpuinfo
cat /proc/self/mounts
cat /proc/version
cat /etc/passwd
w
last -f /var/log/wtmp
cat /var/log/auth.log
cat /var/log/dpkg.log
sudo rkhunter --check --rwo
sudo chkrootkit
file [archivo / filename]
strings [archivo / filename]
strings -t d [imagen / imagefile] | grep -iE "[termino / string]"
find / -writable -type f 2>/dev/null | grep [termino / string]
```
### Volatility
```
python3 vol.py -h
python3 vol.py -f [archivo de imagen / image file] windows.info
python3 vol.py -f [archivo de imagen / image file] windows.pslist
python3 vol.py -f [archivo de imagen / image file] windows.psscan
python3 vol.py -f [archivo de imagen / image file] windows.pstree
python3 vol.py -f [archivo de imagen / image file] windows.malfind
python3 vol.py -f [archivo de imagen / image file] windows.malfind.Malfind
python3 vol.py -f [archivo de imagen / image file] windows.filescan
python3 vol.py -f [archivo de imagen / image file] windows.registry.hivescan
python3 vol.py -f [archivo de imagen / image file] windows.netscan
python3 vol.py -f [archivo de imagen / image file] windows.netstat
python3 vol.py -f [archivo de imagen / image file] windows.cmdline
python3 vol.py -f [archivo de imagen / image file] banners.Banners
```

### MacOS Forensics
### Informacion del Sistema / System Information
```
cat /System/Library/CoreServices/SystemVersion.plist
stat -x [archivo / filename]
tail .bash_history
```

## Recursos Externos / Links

### aff
https://www.kali.org/tools/afflib/

### Montaje NTFS / NTFS Mounting - Linux
https://phoenixnap.com/kb/mount-ntfs-linux

### Rainbow Tables
https://freerainbowtables.com

### BIOS Passwords
https://cseweb.ucsd.edu/~hopper/windows/How_to_Bypass_BIOS_Passwords.htm

### Windows.edb
https://www.thewindowsclub.com/windows-edb-file

### Malware Analysis Memory Forensics with Volatility 3
https://newtonpaul.com/malware-analysis-memory-forensics-with-volatility-3/

### How to extract forensic artifacts from pagefile.sys?
https://andreafortuna.org/2019/04/17/how-to-extract-forensic-artifacts-from-pagefile-sys/

### How to perform a digital forensic analysis using only free tools
https://andreafortuna.org/2021/02/13/how-to-perform-a-digital-forensic-analysis-using-only-free-tools/

### DumpChk
https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/dumpchk

### Metashield CleanUp
https://metashieldclean-up.elevenpaths.com

### Eric Zimmerman's tools
https://ericzimmerman.github.io/#!index.md

### Audit Logon Events
https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/basic-audit-logon-events

### How to use Netstat on Linux
https://www.howtogeek.com/513003/how-to-use-netstat-on-linux/

### KAPE Facilitando la tarea de recolectar evidencia
https://blog.csiete.org/2019/02/kape-facilitando-la-tarea-de-recolectar.html

### Recolección de evidencia, super timelines y Cacería de amenazas: Un aproximación a la identificación de amenazas
https://blog.csiete.org/2020/06/recoleccion-de-evidencia-super.html

### Más secretos en la memoria del computador con AVML
https://youtu.be/4HJ-dCDD5Bs

### DFIR Training - Herramientas Forenses Gratuitas / Free Forensic Tools
https://www.dfir.training/tools/search-results?order=alpha&dir=3&query=all&usematch=1&matchall=jr_licensetype&filter=118&jr_licensetype=free

## Imagenes para laboratorio / Images to practice

### File Carving
https://cfreds-archive.nist.gov/FileCarving/index.html

### Esteganografia y File Carving and Steganography
https://cfreds.nist.gov/all/NIST/RhinoHunt

### Windows 10 RAM 
https://www.osforensics.com/downloads/WinDump.zip

### MAC 10.9.3 RAM
https://www.osforensics.com/downloads/MacDump.zip

### Ubuntu 16.04 RAM
https://www.osforensics.com/downloads/LinuxDump.zip

### Imagenes Basicas de Memoria / Basic Memory Images
https://cfreds.nist.gov/all/NIST/BasicMemoryImages

### Imagenes de Memoria / Memory Samples
https://github.com/volatilityfoundation/volatility/wiki/Memory-Samples

## Herramientas / Tools

### FTK Imager
https://accessdata.com/product-download/ftk-imager-version-4-7-1

### Autopsy
https://www.autopsy.com/download/

### zsteg
```
https://github.com/zed-0xff/zsteg
Instalacion / Instalation - Linux
gem install zsteg
```

### The Sleuth Kit
```
http://sleuthkit.org
Instalacion / Instalation - Linux
sudo apt update
sudo apt install sleuthkit
```

### OSForensics
https://www.osforensics.com/osforensics.html

### OSFClone
https://www.osforensics.com/tools/create-disk-images.html

### Volatility Workbench
https://www.osforensics.com/tools/volatility-workbench.html

### dban
https://dban.org

### balenaEtcher
https://www.balena.io/etcher/

### grr
https://github.com/google/grr

### Eraser
https://eraser.heidi.ie

### TestDisk
https://www.cgsecurity.org/wiki/TestDisk_Download

### analyzeMFT
https://github.com/dkovar/analyzeMFT

### CrypTool 2
https://www.cryptool.org/en/ct2/

### Sysinternals
https://docs.microsoft.com/en-us/sysinternals/downloads/

### LogonSessions
https://docs.microsoft.com/en-us/sysinternals/downloads/logonsessions

### ListDLLs
https://docs.microsoft.com/en-us/sysinternals/downloads/listdlls

### Handle
https://docs.microsoft.com/en-us/sysinternals/downloads/handle

### Process Explorer
https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer

### ESE Database View
https://www.nirsoft.net/utils/ese_database_view.html

### Hirens Boot CD
https://www.hiren.info/pages/bootcd

### xmount
https://github.com/mika/xmount

### USBDeview
https://www.nirsoft.net/utils/usb_devices_view.html

### DriveLetterView
https://www.nirsoft.net/utils/drive_letter_view.html

### Process-Dump
https://github.com/glmcdona/Process-Dump

### Redline
https://www.fireeye.com/services/freeware/redline.html

### RegRipper
https://github.com/keydet89/RegRipper3.0

### AutoRUns
https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns

### MzCacheView
https://www.nirsoft.net/utils/mozilla_cache_viewer.html

### MzCookiesView
https://www.nirsoft.net/utils/mzcv.html

### MzHistoryView
https://www.nirsoft.net/utils/mozilla_history_view.html

### ChromeCacheView
https://www.nirsoft.net/utils/chrome_cache_view.html

### ChromeCookiesView
https://www.nirsoft.net/utils/chrome_cookies_view.html

### ChromeHistoryView
https://www.nirsoft.net/utils/chrome_history_view.html

### EdgeCookiesView
https://www.nirsoft.net/utils/edge_cookies_view.html

### WinPrefetchView
https://www.nirsoft.net/utils/win_prefetch_view.html

### ShellBags Exlorer
https://f001.backblazeb2.com/file/EricZimmermanTools/net6/ShellBagsExplorer.zip

### HxD
https://mh-nexus.de/en/hxd/

### LECmd
https://f001.backblazeb2.com/file/EricZimmermanTools/net6/LECmd.zip

### JumpList Explorer
https://f001.backblazeb2.com/file/EricZimmermanTools/net6/JumpListExplorer.zip

### DFIR_scripts
https://github.com/edchavarro/DFIR_scripts

### kape
https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape

### exiftool
https://www.exiftool.org

### Volatility3
https://github.com/volatilityfoundation/volatility3/

### AVML
https://github.com/microsoft/avml

## Distribuciones Forenses / Forensic Distributions

### CAINE
https://www.caine-live.net

### Tsuguri Linux
https://tsurugi-linux.org

## Documentacion / Documentation

### NIST 800-88 Guidelines for Media Sanitization
https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf

### RFC 3227 - Guidelines for Evidence Collection and Archiving
https://datatracker.ietf.org/doc/html/rfc3227

## Licencia / License

[![CC-BY](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/by.svg)](https://creativecommons.org/licenses/by/4.0/)

Este trabajo se encuentra licenciado bajo / This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
