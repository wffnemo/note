# <center> 远程连接jupyter</center>  

1. 首先参考[官方文档](https://jupyter-notebook.readthedocs.io/en/stable/public_server.html)
2. 我的步骤：  
    * 生成配置文件
    检查自己服务器中是否存在jupyter的配置文件`jupyter_notebook_config.py`，一般在linux中该文件的地址是`/home/USERNAME/.jupyter/jupyter_notebook_config.py`。  
    如果机器中存在该文件，则直接进行配置，如果不存在该文件，则需要先生成该配置文件，生成配置文件的代码是：  
    `$ jupyter notebook --generate-config`  

    * 密码设置
    手动产生一个哈希密码，使用代码`notebook.auth.security.passwd()`：  
    ![remote_jupyter_1](./picture/remote_jupyter_1.png)  

    * 添加哈希密码到jupyter配置文件中  
    修改配置文件中的参数：  
    ![remote_jupyter_2](./picture/remote_jupyter_2.png)

    * 使用ssl进行加密通信  
    通过certfile选项设置自签名证书，代码如图：  
    ![remote_jupyter_3](./picture/remote_jupyter_3.png)  
    然后使用openssl生成自签名证书。以下命令将创建一个有效期为365天的证书，并将密钥和证书数据都写入同一文件：  
    ![remote_jupyter_4](./picture/remote_jupyter_4.png)

    * 修改配置文件`jupyter_notebook_config`  
    直接在文件末尾添加即可，其中端口号可以任意设置，keyfile和certfile为上一步生成的mykey.key和mycert.pem两个文件的路径。  
    ![remote_jupyter_5](./picture/remote_jupyter_5.png)  

    * 然后就可以在浏览器中连接到jupyter了：  
    在浏览器中输入`https://IP:prot`即可，再输入第二步设置的密码  
    ![remote_jupyter_6](./picture/remote_jupyter_6.png)  

3. 外网连接jupyter  
外网连接jupyter步骤与内网连接基本一致，不同点是外网的IP与内网不同，同时外网连接的时候需要进行端口转发，端口转发的代码如下：  
![remote_jupyter_7](./picture/remote_jupyter_7.png)  
其中8888是自己任意选取的端口，4444是jupyter的端口，5602是服务器的端口。  
然后就可以再浏览器中输入`https://localhost:8888`连接jupyter了。  
