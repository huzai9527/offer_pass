## 　先换源,注释掉其他的
```ｂａｓh
deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian buster contrib
deb http://security.debian.org/debian-security jessie/updates main 
deb http://ftp.de.debian.org/debian buster main 

```

## 下载ｖｉｒｔｕａｌｂｏｘ,链接如下（注意对应版本号）

```ｂｓａｈ
https://www.virtualbox.org/wiki/Linux_Downloads
```

## 　解决依赖问题，除了libvpx5，其他都能解决
－ libvpx5 通过下载deb直接安装，下载链接
```ｂａｓｈ
https://packages.debian.org/buster/amd64/libvpx5/download
```

## 安装内核依赖文件(卸载dkms 重新装)
-  在装dkms的时候要注意导源，我这里是一个一个添加的，一定要注意版本对应！！

```bash
sudo apt-get autoremove virtualbox-dkms
sudo apt-get install build-essential linux-headers-`uname -r` dkms virtualbox-dkms
```

## 能够获得module

```bash
sudo modprobe vboxdrv
sudo modprobe vboxnetflt
```
