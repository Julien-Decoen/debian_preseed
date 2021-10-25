# debian_preseed

## Tonton Jo - 2021
Join me on Youtube: https://www.youtube.com/c/tontonjo

This little tool aim to get smalls one-time configurations for Proxmox Virtual environement and backup server hosts in no time.
It automatically will find if the host is a pve or a pbs host and setup accordingly.

If you find this usefull, please think about
<a href="https://www.buymeacoffee.com/tontonjo"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png"></a>
and to [Subscribe to my youtube channel](http://youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw?sub_confirmation=1)

You can watch a demonstration of the tool [with Joix OS](https://www.youtube.com/watch?v=XqYi9IQea68) 

## How-to:  
### Download your ISO and upload it on your host  
### Create a directory where the ISO will be mounted on  
```shell
mkdir /mnt/iso
```
### Create a directory where the ISO will be mounted on  
```shell
mount -o loop "/root/debian.iso" /mnt/iso
```
### Copy the content of the ISO in a new folder  
```shell
cp -r /mnt/iso "/root/iso/"
```

### Generate your new customized ISO  
```shell
genisoimage -o /root/preseeded_debian.iso -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -r .
```

