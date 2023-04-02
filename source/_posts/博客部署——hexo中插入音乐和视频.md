---
title: hexo中插入音乐和视频
toc: true
date: 2023-03-30 17:49:30
tags:
- hexo插件
categories: 
- 博客部署
---

#### 一、前期准备

​	如果插入的音乐和视频是在本地存储的，则需要多进行一步。需要先把本地的音乐和视频上传到图床这一类工具上面，获取到可直接访问的网络链接。这里自己采用的是已购买的腾讯云上面的对象存储服务。这里有两种方法，一种是通过typora+PicGO+腾讯云实现自动生成链接；另一种就是直接进入腾讯云上传。

#### 二、下载hexo插件

  可以直接使用npm安装

1. hexo-tag-aplayer:https://github.com/MoePlayer/hexo-tag-aplayer

   ```bash
   npm install hexo-tag-aplayer
   ```

2. hexo-tag-dplayer:https://github.com/NextMoe/hexo-tag-dplayer

   ```bash
   npm install hexo-tag-dplayer
   ```

#### 三、通过aplayer在博客中插入音乐

  在markdown中添加如下代码：

```bash
{% aplayer "她的睫毛" "周杰伦" "http://home.ustc.edu.cn/~mmmwhy/%d6%dc%bd%dc%c2%d7%20-%20%cb%fd%b5%c4%bd%de%c3%ab.mp3"  "http://home.ustc.edu.cn/~mmmwhy/jay.jpg" %}
```

  效果如下所示：
{% aplayer "她的睫毛" "周杰伦" "http://home.ustc.edu.cn/~mmmwhy/%d6%dc%bd%dc%c2%d7%20-%20%cb%fd%b5%c4%bd%de%c3%ab.mp3"  "http://home.ustc.edu.cn/~mmmwhy/jay.jpg" %}

#### 四、通过dplayer在博客中插入视频

  在markdown中添加如下代码：

```bash
{% dplayer "url=http://home.ustc.edu.cn/~mmmwhy/GEM.mp4"  "pic=http://home.ustc.edu.cn/~mmmwhy/GEM.jpg" "loop=yes" "theme=#FADFA3" "autoplay=false" "token=tokendemo" %}
```

  效果如下所示：
{% dplayer "url=https://mu-1311836296.cos.ap-nanjing.myqcloud.com/murentutu/cloudimages/188%E7%9A%84love%20story.mp4" "loop=yes" "theme=#FADFA3" "autoplay=false" "token=tokendemo" %}


## 参考资料

> - [Hexo博客中插入音乐/视频/](https://www.jianshu.com/p/26a7fc7cc185)

