# VirtualBox kernel module signing w/ Fedora

## Initial setup
```
sudo wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo
sudo dnf upgrade
sudo dnf install binutils qt gcc make patch libgomp glibc-headers glibc-devel kernel-headers kernel-devel dkms VirtualBox-5.0
sudo usermod -a -G vboxusers serge
openssl req -new -x509 -newkey rsa:2048 -keyout MOK.priv -outform DER -out MOK.der -nodes -days 36500 -subj "/CN=Serge/"
chmod 400 MOK*
sudo mokutil --import MOK.der
sudo reboot
```
- MOK = Machine Owner Key, used for signing VBox kernel modules

## Module signing (necessary after every kernel upgrade)

```
sudo /usr/src/kernels/$(uname -r)/scripts/sign-file sha256 ./MOK.priv ./MOK.der $(modinfo -n vboxdrv)
sudo /usr/src/kernels/$(uname -r)/scripts/sign-file sha256 ./MOK.priv ./MOK.der $(modinfo -n vboxpci)
sudo /usr/src/kernels/$(uname -r)/scripts/sign-file sha256 ./MOK.priv ./MOK.der $(modinfo -n vboxnetadp)
sudo /usr/src/kernels/$(uname -r)/scripts/sign-file sha256 ./MOK.priv ./MOK.der $(modinfo -n vboxnetflt)
sudo modprobe vboxdrv vboxpci vboxnetadp vboxnetflt
```
