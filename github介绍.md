## Git 与Github 介绍

### 1.1 什么是git 有什么用？

Git 是一个版本控制管理工具：
- 保存历史记录(版本管理、版本回退)
- 多人协同交互

Git 翻译过来就是 饭桶 的意思，老外就是喜欢这样的命名。
### 1.2 安装和配置 Git 环境(最新版本2.13.1)

下载地址：https://git-for-windows.github.io/

历史版本地址：https://github.com/git-for-windows/git/releases

确认是否有 git 环境：

```bash
$ git --version
```

如果看到能输出一个版本号 `git version 2.10.1.windows.1`（版本不一定一致），说明没有问题。

### 1.3 初始设置

```bash
$ git config --global user.name "yourname"
$ git config --global user.email "your_email@example.com"
```
第一次安装了 git 环境之后配置一下即可。
如果想要修改，可以使用上面命令重新执行即可修改

### 1.4基本操作

- `git init` 初始化厂库
- `git status` 查看文件状态  *
- `git add *`    添加到git目录*
- `git commit -m "项目描述"` 提交到本地厂库*
- `git push`   提交到远程厂库*
- `git log`    查看提交日志*

### 1.5 推送至远程仓库

- `git push -u origin master`
  + 推送到名称为 origin 远程仓库地址下的 master 分支下


###  上传成功的状态就是这样的


### 2.1 Git 与 github 关系
+ GitHub是个免费的代码托管平台
+ Git 与GitHub 的关系？

git是一张弓，github是靶子，你的源代码是箭

### github的基本使用(下载别人的源代码)



### 3. 免登陆的设置

1. 原理：设置公钥关联到github 上，实现免登陆

2.  方法：在桌面上 右键打开  gitbash   输入  ssh-keygen    按三次enter 出现![](./img/20171206124016.png)

   已经生成了共钥了。

3. 检测方式：C:\Users\sjm\.ssh     在你的用户下  有一个.ssh 文件夹  里面有两个文件![](./img/test.png)

   ​

### 资源共享

前端导航[https://ganjs.github.io/FrontEndGuide/]

掘金网[https://juejin.im/]

学习博客[http://colinued.leanote.com/]



## 第二块  hexo 博客搭建

##### 1、环境配置：

​	1.1 安装node 环境  如果已经安装过node环境了就不用再安装了   安装检测   node -v

​	出现版本号：v6.11.0

​	1.2 安装node环境的同时会自带npm 包    安装检测   npm -v   出现版本号：5.5.1

##### 2、NPM 工具介绍

2.1、NPM的简称：Node Package Manager

2.2、作用：是一个用来安装管理Node包和前端包的一个工具

- 3.1 一是托管node 环境或者浏览器环境用到的一些第三方的包
- 3.2 二是提供了一个用来共享或者检索的一个平台

2.3、是一共命令行工具可以用来下载npm网站上托管的包

##### 3、NPM 的基本使用

3.1、本地安装:

```bash
 npm install [--save]包名
```

- 注意：下载项目中使用的第三方包，要切换到项目的根目录，然后执行 `npm install jquery` 下载完成后包就在`node_modules`文件夹下
- 其中 `node_modules`文件夹中

3.2、全局安装：

- 在任意目录执行都可以

```bash
npm install -global 包名(工具名)
```

- 例子 比如全局安装less：

```
npm i -g  less(缩写)
```

- 可以通过 `npm root -g` 查看全局安装的目录

  ##### 4、部署静态Blog

  4.1、 通过[hexo 来部署 网站](https://hexo.io/zh-cn/)

  4.2、 所需要的环境

  - Node 环境、 npm 全局安装  、github 账号

  4.3、安装hexo 环境 `npm install -g hexo-cli`

  - 检查是否安装成功：`hexo --version `,出现版本号则表示安装成功

  4.4、博客初始化 ` hexo init blog`

  ​

  ##### 5、博客的发布

  ##### 5.1、修改配置文件

  - 找到blog 文件夹，找到config 文件，找到  `deploy` 、 ` type: ` 设置成键值对的形式：;
  - ` type: git ` 
  - `repo: 生成的io 文件，在文件的前面加上用户名：密码@加github地址 ` 
  - 例如： https://IThostpink:sjm147269@github.com/IThostpink/IThostpink.github.io.git
  - 在项目的跟目录下（也就是说blog 下执行gitbash 命令 `npm install hexo-deployer-git --save`）  检测方式：![](./img/deployer.png)
  - 在上面的基础上执行 `hexo deploy --generate`  就可以提交成功了
  - 通过用户名加github.io 就可以访问了`https://hostpink.github.io/` 

#####           6、奇淫技巧：修改时间

​	1、用命令生成md 文件：hexo new  "名字"

​	![](./img/data.png)

##### 	7、购买域名   +  域名解析