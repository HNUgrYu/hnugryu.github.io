> 用移动硬盘作为ubuntu系统盘，实现双系统
# 前期提要
#6 
# 实现步骤
1. 内容备份
2. 系统盘制作
3. 安装过程中选择磁盘擦除（一定要选择自己的移动硬盘）
4. 清华源的替换（注意版本问题）（pycharm中直接在终端添加插件下载的清华源，网上的教学都过时了）
[解决方案](https://www.cnblogs.com/sdlyxyf/p/18455559)
5. 输入法安装（搜狗暂时没有解决无法输入中文问题，fcitx5暂时主流输入法都不适配，需要先卸载后安装fcitx）
` sudo apt install fcitx fcitx-googlepinyin `
6.  压缩下载包
`tar -zxvf /home/gryu/下载/pycharm-community-2024.3.1.tar.gz`
`sudo dpkg -i /home/gryu/下载/sogoupinyin_4.2.1.145_amd64.deb`
7. 代理设置
从微信传输压缩包，使用指令 `sudo dpkg -i packname.deb`,ubuntu系统的文件类型为x86/amd64
8. 创建桌面快捷方式
` nano ~/桌面/pycharm.desktop ` 
```
[Desktop Entry]
Version=1.0
Type=Application
Name=PyCharm
Icon=/home/gryu/pycharm-community-2024.3.1/bin/pycharm.png
Exec=/home/gryu/pycharm-community-2024.3.1/bin/pycharm
Comment=Develop with pleasure!
Categories=Development;IDE;
Terminal=false
```
# 文件备份 启动盘下完成（需提前用timeshift创建快照）
```
sudo apt update
sudo apt install timeshift
```
分区确定
```
sudo fdisk -l
lsblk
```
文件复原
```
sudo mkdir /etc/timeshift
sudo mount /dev/sdb2 /etc/timeshift
sudo timeshift-launcher

```


