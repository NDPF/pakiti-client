# pakiti-client
Client for Pakiti patching status monitoring system

## Debian package build instructions

Setting up a build machine is easiest with pbuilder. Make sure to install the latest
versions of debootstrap and pbuilder from sid if possible. 

```sh
wget https://github.com/NDPF/pakiti-client/archive/v3.0.2.tar.gz
tar tfz v3.0.2.tar.gz 
mv v3.0.2.tar.gz pakiti-client-3.0.2.tar.gz
tar xfz pakiti-client-3.0.2.tar.gz 
cd pakiti-client-3.0.2/
dpkg-buildpackage -S
cd ..
sudo pbuilder create --distribution bionic --mirror http://archive.ubuntu.com/ubuntu
sudo pbuilder build --distribution bionic pakiti_3.0.2.dsc 
```
