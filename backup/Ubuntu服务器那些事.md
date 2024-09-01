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
3.将yml文件传输到服务器
- csp指令传输文件可能遇到权限不够的问题，无法向服务器文件中写入文件
- 因此使用finalshell中的文件传输，此时权限为管理者权限
4. 下载miniconda

6. 

4.进入到文件所在位置运行yml文件
- 用yml文件配置环境 ：` sudo conda env create -f environment.yml`

---

## Ubuntu服务器跑程序
### 

