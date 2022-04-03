# Debian Preseed

## Tonton Jo  
### Join the community:
[![Youtube channel](https://github-readme-youtube-stats.herokuapp.com/subscribers/index.php?id=UCnED3K6K5FDUp-x_8rwpsZw&key=AIzaSyA3ivqywNPQz0xFZBHfPDKzh1jFH5qGD_g)](http://youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw?sub_confirmation=1)
[![Discord Tonton Jo](https://badgen.net/discord/members/N3ssTdTS?label=Discord%20Tonton%20Jo%20&icon=discord)](https://discord.gg/N3ssTdTS)
### Support the channel with one of the following link:
[![Ko-Fi](https://badgen.net/badge/Buy%20me%20a%20Coffee/Link?icon=buymeacoffee)](https://ko-fi.com/tontonjo)
[![Infomaniak](https://badgen.net/badge/Infomaniak/Affiliated%20link?icon=K)](https://www.infomaniak.com/goto/fr/home?utm_term=6151f412daf35)
[![Express VPN](https://badgen.net/badge/Express%20VPN/Affiliated%20link?icon=K)](https://www.xvuslink.com/?a_fid=TontonJo)  
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

