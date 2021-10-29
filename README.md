# Debian Preseed

## Tonton Jo - 2021

If you find this usefull, please consider supporting my work:  
- Join me on my [Youtube Channel](http://youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw?sub_confirmation=1)  
- <a href="https://www.buymeacoffee.com/tontonjo"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png"></a> <a href="https://www.infomaniak.com/goto/fr/home?utm_term=6151f412daf35"><img src="https://i.ibb.co/KjWSd95/banner-bleu.png"></a> </a> <a href="https://www.xvinlink.com/?a_fid=TontonJo"><img src="https://upload.wikimedia.org/wikipedia/en/thumb/7/79/ExpressVPN-logo.svg/261px-ExpressVPN-logo.svg.png"></a>  

## Informations:  
You can watch a demonstration of a preseeded installation [with Joix OS](https://www.youtube.com/watch?v=XqYi9IQea68) 

## How-to:  
### Download your new ISO and upload it on your host  
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
cp -r /mnt/iso "/root/extracted_iso/"
```
### Once the copy is done, unmount the iso - you can then delete it if you want
```shell
umount /mnt/iso
```  
### Download the content of debian_preseed repository and copy all the files in "/root/extracted_iso/iso"
https://github.com/Tontonjo/debian_preseed/archive/refs/heads/main.zip

### Edit configurations as you need:  
- By default all settings are commented
- You'll have to pass trough many attemps to get your perfect configuration  
Preseed file is located in /root/extracted_iso/jo/preseed.cfg  
Custom menu file is located in /root/extracted_iso/isolinux/txt.cfg  

### Install Genisoimnage:  
```shell
apt-get install -y genisoimage
```  
### CD into iso files folder:  
```shell
cd /root/extracted_iso
```  
### Generate your new customized ISO  
```shell
genisoimage -o /root/preseeded_debian.iso -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -r .
```

### Run your ISO!
Export the new generated iso file and run it!

