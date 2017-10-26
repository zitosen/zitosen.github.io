# 计算机

标签：computer

## 磁盘相关
  ldisk -l    #查看磁盘
  lsusb -l   #查看usb设备
  fsck   #磁盘检查，修复
  mkfs.vfat -l /dev/xxx   格式化磁盘，并建立vfat文件系统

  updatedb #更新索引
  locate #查找

## 网络

  hosts更新网址：https://laod.cn/hosts/2016-google-hosts.html
  修改hosts文件后，重启网络
  sudo systemctl restart NetworkManager

- Xshell与Windows文件传输
  yum install lrzsz
 上传： rz 下载：sz

## 系统管理

- ubuntu中共可以使用 6 个控制台，分别用快捷键 Ctrl+Alt+F1 到 Ctrl+Alt+F6 进行切换； Ctrl+Alt+F7切换回桌面模式

- 死机处理
ctrl+alt+t 调出终端; sudo kill pid 或者 sudo pkill Xorg 注销
ctrl+alt+f1 进入tty1控制台; sudo kill pid 或者 sudo pkill Xorg 注销

- 查看内存
dmidecode --type memory
- 查看硬件信息
sudo apt-get install hardinfo
- 查看操作系统版本
cat /proc/version
uname -a

### 程序安装和卸载
- 利用deb格式安装
  deb是debian linux的安装格式，跟red hat的rpm类似，基本命令： dpkg -i xxx.deb
- 查看已安装软件包列表
  dpkg --list
- 完全移除程序
  sudo apt-get --perge remove xxx
- 保留配置文件
  sudo apt-get remove xxx
- 添加源（repository）
  sudo add-apt-repository xxx:xxx
  sudo apt-get update
- Python
  python安装
  下载Python-2.7xxx.tgz; ./configure --prefix=/usr/local/lib; make; make install
- pip安装
  python get-pip.py #失败
  服务器无法联网，从source安装
 下载setuptools-xxx.zip; python setup.py build; python setup.py install
 下载pip-xxx.tar.gz; python setup.py build; python setup.py install
- ase安装
下载ase-xxx.tgz; python setup.py build; python setup.py install
由于服务器无法联网，download 'flask' failed

## Github
- github建立ssh连接
  首先生成本地ssh key
```bash
ssh-keygen -t rsa -C "your_email"
```
your_email为github上的注册邮箱，这会在~/下生成.ssh文件夹，~/.ssh/id_rsa.pub文档中为生成的key，复制到github网页相应位置。
  验证是否成功
```
ssh -T git@github.com
```
