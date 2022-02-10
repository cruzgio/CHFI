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

### 

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

### NTFS Data Stream
```
gci -recurse | % { gi $_.FullName -stream * } | where stream -ne ':$Data' - Powershell
```

### Dispositivos USB conectados / Connected USB devices
Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Enum\USB\*\*\ 
Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Enum\USB\*\*\ | Select FriendlyName

### Windows Forensics - Informacion Volatil / Volatile Information
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

### Windows Forensics - Revision del Sistema de Archivos / Examining File Systems
```
En la carpeta / Under WINDOWS\system32 
dir /o:d
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

## Imagenes para laboratorio / Images to practice

### File Carving
https://cfreds-archive.nist.gov/FileCarving/index.html

### Esteganografia y File Carving and Steganography
https://cfreds.nist.gov/all/NIST/RhinoHunt

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
