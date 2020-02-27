# NELN实验室GPU服务器用户须知
## 1. **网络安全**
- **服务器使用**
    - 服务器的账户由管理员分配（同时配发登陆用**密钥文件**），密钥文件由管理员半年更新一次
    - 服务器的账户密码自行设置强密码，请包含大写字母、小写字母、数字、特殊符号
    - 为防范勒索病毒等安全事故（真实发生过），请务必**保管好**密钥文件、服务器账户信息
    - 重要数据请做好备份（例如清华云盘、实验室移动硬盘）

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
