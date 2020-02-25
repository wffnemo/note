# <center>安装anaconda</center>

* 首先在anaconda官网下载最新的anaconda的linux版本
![install_anaconda_1](./picture/install_anaconda_1.png)
* 将安装包上传到服务器中，或直接下载到服务器中，然后切换到安装包的路径，执行`bash Anaconda3-2019.10-Linux-x86_64.sh`:
![install_anaconda_2](./picture/install_anaconda_2.png)
* 接着一直按yes即可，其中在选择安装路径时，输入想要安装的路径即可
* 最后还需要配置anaconda的环境变量，切换到用户根目录下，`cd ~`，修改`.bashrc`文件，在文件最后添加代码`export PATH="/home/wffnemo/API/anaconda3/bin:$PATH`  
![install_anaconda_3](./picture/install_anaconda_3.png)
* 更新环境变量，切换到用户根目录下，执行代码`source .bashrc`即可
* 输入`anaconda`，如下图则表示安装成功  
![install_anaconda_4](./picture/install_anaconda_4.png)
