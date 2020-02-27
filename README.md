# 实验室GPU服务器001用户须知
## 1. **安全性**
- 远程登陆
    - 服务器的账户由管理员分配（同时配发登陆用**密钥文件**），密钥文件由管理员半年更新一次
    - 服务器的账户密码自行设置强密码，请包含大写字母、小写字母、数字、特殊符号
    - 为防范勒索病毒等安全事故（实验室真实发生过），请务必**保管好**密钥文件、服务器账户信息
- 数据安全
    - **敏感涉密数据**需经教师同意，方可上传至服务器使用
    - 重要数据请及时**备份**（例如个人电脑、清华云盘、实验室移动硬盘）
- 权限
    - 为了保证服务器有序、稳定，仅管理员拥有sudo权限
    - 各用户的软件（如anaconda和相应的python环境）请安装于自己的home文件夹下，避免sudo需求
    - 必需sudo的需求，如果是公共需求或确有需求，联系管理员
    - 服务器的Docker软件具备sudo权限，因此：
        - 确有docker使用需求的用户，由管理员分配docker使用的权限
        - 具备docker权限的用户，请仔细了解docker的使用语法（目前版本19.03，[docs点这里](https://docs.docker.com/get-started/)）
        - Docker的container具备root权限，在container内务必谨慎操作（误删系统/他人文件，斩）
        - image和container及产生的数据都占用空间，请及时删除非必要image/container，否则磁盘满后系统卡死、崩溃（斩）
        - container与系统交互的路径，必须设定在自己home文件夹及以内（误删系统/他人文件，斩）
        - 使用示例：
        ```Bash
        echo "hello GitHub" #Bash
        ```
## 2. **资源分配**
- 存储
    - 各用户的软件和数据文件，请存放于自己的home文件夹下
    - 服务器硬盘槽已插满，home磁盘总空间约30T，目前共6个用户，请合理占用空间
    - 
- GPU
    - 请勿占满所有GPU
- 网络
    - 清华源
## **3. 一些使用介绍**
- tmux
- cuda driver

## Features
- **Functionality**:
    - **2D real-time multi-person keypoint detection**:
        - 15 or 18 or **25-keypoint body/foot keypoint estimation**. **Running time invariant to number of detected people**.
        - **2x21-keypoint hand keypoint estimation**. Currently, **running time depends** on **number of detected people**.
        - **70-keypoint face keypoint estimation**. Currently, **running time depends** on **number of detected people**.
    - **3D real-time single-person keypoint detection**:
        - 3-D triangulation from multiple single views.
        - Synchronization of Flir cameras handled.
        - Compatible with Flir/Point Grey cameras, but provided C++ demos to add your custom input.
    - **Calibration toolbox**:
        - Easy estimation of distortion, intrinsic, and extrinsic camera parameters.
    - **Single-person tracking** for further speed up or visual smoothing.
- **Input**: Image, video, webcam, Flir/Point Grey and IP camera. Included C++ demos to add your custom input.
