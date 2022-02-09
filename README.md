# CHFI
Repositorio con recursos relacionados a los capitulos de la certificacion CHFIv10 de EC-Council
Repository with information related to the CHFIv10 certification chapters

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
