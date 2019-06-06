
Ansible scripts by Nick Loman and Radoslaw Poplawski (originated during Porecamp project)

### Getting started

From Ubuntu 16.04 as ubuntu user:

- install Ansible:

```
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

- run playbook:
`sudo ansible-playbook -i hosts prepare_usb.yml`

### [USB images](https://artic.climb.ac.uk/)

#### Recommened USB writing software:
- dd
- [Etcher](https://etcher.io/)
- [Rufus](https://rufus.akeo.ie/)


### (Optional) Build your own Ubuntu image from scratch:

Prepare target drive (sdx):
-  partition the drive:
```
parted /dev/sdx
  mklabel gpt
  mkpart primary fat32 1MiB 500MiB
  mkpart primary ext4 500MiB 100%
  set 1 esp on
  set 2 legacy_boot on

```

- create filesystems:
```
mkfs.vfat /dev/sdx1
mkfs.ext4 /dev/sdx2
```

Start the Ubuntu installer:
  TODO:

Reinstall GRUB: `grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=boot --recheck`

Make drive BIOS bootable:
```
sudo dd if=/usrlib/syslinux/mbt/gptmbr.bin of=/dev/sdx bs=440 count=1
sudo rm /vmlinuz ; sudo ln -s /boot/vmlinuz-$(uname -r) /vmlinuz
sudo rm /initrd.img ; sudo ln -s /boot/initrd.img-$(uname -r) /initrd.img
sudo apt install extlinux
sudo extlinux --install /boot
```

- extlinux config (`/boot/extlinux.conf` (find UUID: `blkid /dev/sdx2`):
```
DEFAULT Ubuntu
PROMPT 1
TIMEOUT 50

LABEL Ubuntu
  KERNEL /vmlinuz
  INITRD /initrd.img
  APPEND root=UUID=$UUID
```
