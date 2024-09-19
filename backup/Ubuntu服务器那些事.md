# Ubuntu服务器的使用说明
## 使用finalshell连接windows主机和服务器
> 本质上是利用ssh连接
### 连接步骤
1. 在windows系统上下载Finalshell软件
2. 在Ubuntu服务器的终端找到其IP地址
3. 在finalshell根据IP地址和用户名和密码连接到服务器
4. 就可以在本地操作Ubuntu的终端
### finalshell的实用功能
1. 可以直接在界面下方传输文件
2. 监控内存运行情况
3. GUI界面友好

### 利用ssh在服务器上配置环境
1. 对于anaconda自己配置的环境导出为environment.yml文件传输到服务器
''' conda env export > environment.yml '''
> 我觉的比较重要的一点就是理清楚自己在什么目录的位置，什么环境下进行的操作，因此conda的环境管理可以帮助我们

2. 服务器新建文件夹
- 默认根目录：`` /home/ubuntu  ``
- 嵌套创建新的路径：` mkdir ygr/env -p  `
- 展示当前路径下的内容：`ls `
- 回到上一目录：` cd .. `

3. 将yml文件传输到服务器
- csp指令传输文件可能遇到权限不够的问题，无法向服务器文件中写入文件
- 因此使用finalshell中的文件传输，此时权限为管理者权限

4. 下载miniconda `sudo apt install `

- 先添加清华源
- 再更新Ubuntu系统
- 就可以使用apt下载需要的包了
`wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh`


5. `bash` 解包

`bash Miniconda3-latest-Linux-x86_64.sh`

6. 添加到path

``export PATH="$HOME/miniconda3/bin:$PATH"
source ~/.bashrc``
> 中间小写的部分才是相对路径


4.进入到文件所在位置运行yml文件
- 用yml文件配置环境 ：` sudo conda env create -f environment.yml`

---


## 系统炸了~不嘻嘻
### 重装ubuntu系统
1. 官网安装iso镜像文件
> 分为server和desktop版本，server全是命令行，更贴近于服务器的功能

2. 用rusa把u盘变成驱动盘（会格式化u盘，iso文件不能放在U盘）
3.重装系统，需要在分区里选择自定义分区，删除之前所有的内容
4.拔掉u盘重启就安装好了

### server系统的那些事
**版本24.0**
> server系统相较于desktop系统来说抽象很多
问题1：连接不上网络
- 看网络连接：` sudo link show `
lo：本地地址
enp4s0：物联网地址，pci接口连接的网线
wlo1：wifi 
- 看网络连接状态： ` ip a` inet后面接的第一个是系统地址，第二个是广播地址
- 静态地址和动态地址（静态地址需要`ipconfig`来看相关地址，动态用dhpc4配置）
- 修改文件：`sudo nano <filename>`nano文件需要保证严格的缩进
- 运行netplan文件： ` sudo netplan try `
> 在修改了无数次netplan的配置文件后，了解了ip地址，dns，网关，掩码是什么，知道了ubuntu系统的基本操作，翻阅了官方的文档，仍然连网路连接的问题都解决不了
> 如果你还在和我一样因为server服务器更适合跑程序的这个优点而选择了他，自身对其没有了解的话，尽快跑吧，隔壁ubuntu桌面版程序都跑完了你还在配置呢

### ubuntu系统那些事
> 嗖的一下就安装完了
`sudo apt update`
`sudo apt upgrade`
`sudo install  openssh-server`
就可以继续使用finalshell连接了

### barrier的安装
> 随着barrier的安装，意味着本次的服务器事件已经到达了第一个里程碑，终于不用再两个电脑来回切换键盘和鼠标了，欣喜若狂
总结：
1. 要把linux系统作为主机，windows作为客机
2. 学会看日志找到自己当前的问题
3. 在设置里禁用ssl，或者自己弄一个ca证书
4. 端口可能被占用，24800改为24801试试

### 下载搜狗输入法
1. 安装框架` sudo apt-get install fcitx`
2. 解压`sudo dpkg -i sogoupinyin_版本号_amd64.deb`
3. 下载依赖项` sudo apt -f install`
4. 系统里调整fcitx为默认框架
5. 卸载 `ibus sudo apt purge ibus`
6. 重启

### 更改清华源地址
`etc/apt/sources.list.d/ubuntu.sources`

### 下载软件无法直接安装
1. 用sudo指令在终端安装
2. 把自己的用户该为管理者权限`sudo usermod -aG sudo username`

---

> 自此，轻重已过一重山，继续启航吧

---

# ubuntu的陨落
> 背景：使用macrium reflect把旧电脑上的所有文件转移到新电脑上，进行双系统的搭建，应该是默认是在整个磁盘上进行覆盖，我只能说这个软件真的是一比一的全部克隆过来，但双系统的同学真的切记切记要备份，现在我搭建的ubuntu大厦倒塌了，在里面的编程全军覆没（难过呜呜呜）
