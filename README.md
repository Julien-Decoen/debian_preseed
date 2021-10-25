# debian_preseed



```shell
mkdir /mnt/iso
```
```shell
mount -o loop "/root/debian.iso" /mnt/iso
```
```shell
mount -o loop "/root/debian.iso" /mnt/iso
```
```shell
cp -r /mnt/iso "/root/iso/"
```
```shell
cp -r /mnt/iso "/root/iso/"
```
```shell
genisoimage -o /root/preseeded_debian.iso -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -r .
```

