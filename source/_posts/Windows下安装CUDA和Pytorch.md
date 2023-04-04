---
title: Windows下安装CUDA和Pytorch
toc: true
date: 2023-04-03 20:19:31
tags:
- Pytorch
- Anaconda
categories:
- 毕设
---

#### 确认有NVIDIA GPU以及CUDA版本

​	方法一：打开任务管理器，在“性能”选项下查看是否有GPU的显示。

​	方法二：通过“设备管理器-显示适配器”查看电脑是否有独立显卡，需要是英伟达的！

​	直接在桌面上右键打开“NVIDIA控制面板”，点击左下角“系统信息”，再点击“组件”查看CUDA支持版本。

![image-20230403214607942](https://mu-1311836296.cos.ap-nanjing.myqcloud.com/murentutu/cloudimages/202304032146596.png)

#### 安装CUDA

​	官网下载地址：https://developer.nvidia.com/cuda-toolkit-archive

​	考虑到C盘内存空间不是很够，所以全部安装在D盘了。

![image-20230403223703306](https://mu-1311836296.cos.ap-nanjing.myqcloud.com/murentutu/cloudimages/202304032237285.png)

​	检查CUDA是否安装成功，在cmd输入***nvcc -V***查看，如下图所示：

![image-20230403233823954](https://mu-1311836296.cos.ap-nanjing.myqcloud.com/murentutu/cloudimages/202304032338353.png)

#### 安装cuDNN

​	安装地址:https://developer.nvidia.com/rdp/cudnn-archive

​	选择版本：11.0

​	下载并解压后将文件夹内的内容移动到CUDA的数据目录下：***D:\ProgramData\NVIDIA Corporation\CUDA Samples\v11.0***

#### 安装Anaconda

​	安装包路径：https://www.anaconda.com/products/distribution

​	下载完安装包以后，右键以管理员身份运行进行安装，安装时注意安装路径，其他则默认选项下一步即可。

​	安装完以后发现开始菜单找不到anaconda的入口，进入anaconda安装目录，进入scripts文件夹，右键进入命令行模式，输入命令***conda install -c anaconda anaconda-navigator\***。安装anaconda-navigator即可。

#### 安装pytorch

1. 打开***anaconda prompt***，输入命令***conda create -n pytorch python=3.6***这一步是创建了pytorch虚拟房间。

   ```bash
   conda create -n pytorch python=3.6	# 创建pytorch虚拟房间
   
   conda info --envs	# 查看已经创建的房间
   ```

2. 安装pytorch，使用如下命令激活pytorch房间。

   ```bash
   conda activate pytorch
   ```

3. 在pytorch官网获取安装命令，找到CUDA 11.0对应的conda命令

   官网地址：https://pytorch.org/get-started/previous-versions/

   ```bash
   # CUDA 11.0
   conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=11.0 -c pytorch
   ```


#### 安装d2I和Jupyter

#### 下载d2I记事本运行测试

#### 测试Pytorch

​	在pytorch房间进入python

![image-20230404104315103](https://mu-1311836296.cos.ap-nanjing.myqcloud.com/murentutu/cloudimages/202304041043612.png)

```python
>>> import torch
>>> print(torch.cuda.is_available())
True
```

​	返回True表示GPU成功被调用。

## 参考资料
> - [Windows 下安装 CUDA 和 Pytorch 跑深度学习 - 动手学深度学习v2](https://www.bilibili.com/video/BV18K411w7Vs/?spm_id_from=333.999.0.0&vd_source=461925c02f33b1b655879d0d5113004a)
> - [GPU版Pytorch1.6安装教程--基于Win10+MX250+CUDA10.2+cuDNN7.6.5](https://blog.csdn.net/hedgehog__/article/details/117997540)
