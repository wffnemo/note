# <center> 远程连接jupyter</center>  

1. 首先参考[官方文档](https://jupyter-notebook.readthedocs.io/en/stable/public_server.html)
2. 我的步骤：  
    * 检查自己服务器中是否存在jupyter的配置文件`jupyter_notebook_config.py`，一般在linux中该文件的地址是`/home/USERNAME/.jupyter/jupyter_notebook_config.py`。如果机器中存在该文件，则直接进行配置，如果不存在该文件，则需要先生成该配置文件，生成配置文件的代码是：  
    `$ jupyter notebook --generate-config`  

    * stf