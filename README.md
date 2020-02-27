# 实验室GPU服务器001用户须知
## 1. **安全性**
- SSH远程登陆
    - 服务器的账户由管理员分配（同时配发登陆用**密钥文件**），密钥文件由管理员半年更新一次
    - 服务器的账户密码自行设置强密码，请包含大写字母、小写字母、数字、特殊符号
    - 为防范勒索病毒等安全事故（实验室真实发生过），请务必**保管好**密钥文件、服务器账户信息
- 数据安全
    - **敏感涉密数据**需经教师同意，方可上传至服务器使用
    - 重要数据请及时**备份**（例如个人电脑、清华云盘、实验室移动硬盘）
- 权限
    - 为了保证服务器有序、稳定，仅管理员拥有sudo权限
    - 各用户的软件（如anaconda和相应的python环境）请安装于自己的home文件夹下，避免sudo需求
    - 必须sudo的需求，如果是公共需求或确有需求，联系管理员
    - 服务器的Docker软件具备sudo权限，因此：
        - 确有docker使用需求的用户，由管理员分配docker使用的权限
        - 具备docker权限的用户，请仔细了解docker的使用语法（目前版本19.03，[docs点这里](https://docs.docker.com/get-started/)）
        - Docker的container具备root权限，在container内务必谨慎操作（误删系统/他人文件，斩）
        - Image和container及产生的数据都占用空间，请及时删除非必要image/container，否则磁盘满后系统卡死、崩溃（斩）
        - 可利用他人的image创建自己的container，但请勿编辑他人的image/container
        - Container与系统交互的路径，必须设定在自己home文件夹及以内（误删系统/他人文件，斩）
        - 使用示例：
        ```Bash
        docker run --rm -it --name $CONTAINER_NAME --gpus '"device=5,6"' -v /home/example_user/:/mnt $IMAGE_NAME /bin/bash
        ```
        其中`--rm`指退出后删除该container，`-it ... /bin/bash`以交互模式进入container的命令行，`--name`命名container便于不同用户分辨，`--gpus`指定container可见的gpu，`-v`指定系统路径与container路径的映射关系。更多信息，请阅读docker [docs](https://docs.docker.com/get-started/)。
## 2. **资源分配**
- 存储
    - 各用户的软件和数据文件，请存放于自己的home文件夹下
    - 服务器硬盘槽已插满，home磁盘总空间约30T，目前共6个用户，请合理占用空间
- GPU*（目前使用率较低，若没有使用冲突，此条不强制执行）*
    - 请勿占满所有GPU，请<=4
    - tensorflow、pytorch等均可在代码内指定可见GPU编号，或者在bash内设定CUDA_VISIBLE的GPU
    - 若确需占用许多甚至全部GPU，请提前与所有用户确认，征得同意后使用
- 网络
    - anaconda、pip、apt-get等可设置为[清华源](https://mirrors.tuna.tsinghua.edu.cn/)，速度快
    - 减少非必要的流量，否则将影响10楼其他实验室的网络
## **3. 一些使用介绍**
- 使用tmux来维持进程
    - ssh连接断开后，相应进程将停止，为了维持进程，服务器安装了tmux，在tmux内的进程不会停止
    - tmux的使用请自行检索
- 显卡驱动
    - 服务器已安装显卡驱动版本440.44
    - 服务器已安装CUDA 10.2
- 大量的小文件上传/下载
    - 建议用`zip`/`tar`等指令压缩、归档为一个文件，再上传/下载

