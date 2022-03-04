- #+BEGIN_NOTE
  作为图床的仓库最好**不能超过 1G**，因为仓库超过 1G 后会有人工审核仓库内容。一旦发现用于图床可能会被删库也可能会被封号！！！所以建议在 1G 之前就换个仓库
  仓库是**公开**的，所以图片放上去要注意隐私问题，特别是单位的一些涉密资料
  #+END_NOTE
- # 一. 使用场景
  
  用于 Markdown 文档书写时引用图片，可配合 Typora 使用（粘贴图片后自动生成），方便后续在博客上发布
- # 二. 软件选型
  
  1.  Markdown 编辑器：[Typora](https://www.typora.net/)
  2.  上传工具：[PicGo](https://picgo.github.io/PicGo-Doc/zh/)
  3.  图床：[Github repo](https://github.com/)
  4.  CDN： [jsDelivr](https://www.jsdelivr.com/)
# 三. 搭建过程
### 1. 创建 GitHub 图床仓库

这里就不再赘述了，需要注意的是仓库一定要是 **Public**
### 2. 生成 Access token

**操作路径：Setting------Developer settings------Personal access tokens**
#### 2.1. 创建
#### ![](https://img-blog.csdnimg.cn/img_convert/31c3ef5683e8ec739fb8a51defaf2773.bmp)2.2. 设置
#### ![](https://img-blog.csdnimg.cn/img_convert/123fffb24fdf07ea90a9d1f511a26f65.bmp)2.3. 生成
### ![](https://img-blog.csdnimg.cn/img_convert/8872bac7f116cd0837202a279e67c23a.bmp)3. 设置 PicGo

![](https://img-blog.csdnimg.cn/img_convert/2382648a58ed989439f7458ad481dc75.png)带 * 号的按规定内容填入即可

制定存储路径：填入`XXX/xxx/`会自动在仓库生成相应的目录

设定自定义域名：国内建议使用 jsDelivr 进行加速，格式如下：`https://cdn.jsdelivr.net/gh/+仓库名`
- ### 4. 设置 Typora
  
  **操作路径：Setting------ 偏好设置 ------ 图像**
  
  ![](https://img-blog.csdnimg.cn/img_convert/9fd4dd2c0a07a9bb8f2bc55e0cbcdf62.bmp){:height 375, :width 714}
- # 四. 呈现效果
  
  1.  复制粘贴图片到 Typora
  ![](https://cdn.jsdelivr.net/gh/sksuai/picture/img/icon_256x256.png)
  2. 文本中图片的连接地址：`https://cdn.jsdelivr.net/gh/sksuai/picture/img/icon_256x256.png`