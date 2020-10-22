# CloudMusic-LevelUp

> 网易云音乐刷歌升级脚本
>
> [项目 GitHub 地址](https://github.com/Secriy/CloudMusic-LevelUp)

## 脚本功能

1. 登录网易云音乐
2. 执行签到，并显示奖励的积分数值
3. 刷音乐播放量，返回具体数值
4. 使用 GitHub Actions 挂脚本

## 使用方式

### 安装依赖

```shell
pip install -r requirements.txt
```

### 执行脚本

脚本使用命令行参数输入变量

```shell
python action.py 手机号 32位MD5密码加密值
```

密码的 MD5 值计算可以在[MD5 在线加密](https://md5jiami.51240.com/)上进行，取 32 位小写值

![](README/image-20200829112617823.png)

执行结果：

![](README/image-20200830161354842.png)

因为我今天已经刷满了，所以就不累计听歌量了。

### 自定义歌单

鉴于网易云每天推荐的歌单不太够，就增加了自定义歌单的功能，也是使用参数的形式，支持多个歌单输入，例如：

```shell
python action.py 手机号 32位MD5密码加密值 5173689994 4901511925
```

## GitHub Actions 部署

### 1. Fork 该仓库

### 2. 创建 Secrets

创建 PHONE，填入手机号

创建 PASSWORD，填入 32 位 MD5 密码加密值

![](README/image-20200829120257532.png)

### 3. 启用 Action

点击 Actions，选择 **I understand my workflows, go ahead and enable them**

真的是过了很久之后才发现**由于GitHub Actions的限制，直接fork来的仓库不会自动执行！！！**

必须手动修改项目提交上去，最简单的方法就是修改下图的README.md文件（右侧有网页端编辑按钮）。

![image-20201022185210937](README/image-20201022185210937.png)

随便修改什么都行，修改完commit就可以了。

之后**每天 0 点**会自动执行一次脚本

![](README/image-20200829120815423.png)

![](README/image-20200829120847583.png)

### 4.手动执行

这一步可以省略，给自己的仓库点一下star就可以手动执行一次GitHub Actions。

## 注意事项

- 网易云音乐限制每天最多计算 300 首
- 脚本每次限制最多 400 首，反复刷没什么用处
- 必须手动修改内容，不然不会自动执行！

## TODO:

这种刷歌的方式不太好，每次推荐的四个歌单似乎不到 300 首，以后有时间再改吧。
