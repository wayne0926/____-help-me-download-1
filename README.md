# @Travis-CI,你帮我下载文件行吗QvQ

## 前言

此项目是一个**鰯鲫**下午在学校用下载Github下载PicGo时的无力吐槽。

网传加速Github的项目有很多种，包括但不限于：

- Gitee加速克隆 【缺点：账号在异地登陆很有可能风控需要手机验证码（然而人在学校没有手机】
- cnpm加速 【缺点：无法下载Release】
- CloudFlareWorkers加速 【缺点：电信网络下下载速度比百度网盘稍微好些，而且丢包严重】
- jsdelivr加速 【缺点：无法下载>20MB的文件，并且官方屏蔽exe下载】

此项目均解决以上问题，但是仍有缺点：

- 第一次配置略麻烦
- 每下载一次文件需要修改一次Github
- 若大文件下载分包较多麻烦

## 开始

第一次配置

1. 先Star该仓库 ~~【可选】~~
2. Fork此仓库
3. 修改 `.travis.yml` 14行单引号括起来的链接地址，将其设置为你所需要下载的链接。

> **注意，其中不得包含特殊字符如\&**

> 实际上我可以把它写在travis-ci的变量里，可以避免公布下载链接，但是个人测试，github访问速度比travis-ci快多了，而且travis-ci登陆还是要Github...

4. 进入你的Github个人资料，(https://github.com/settings/tokens)[新建一个token] ，权限至少repo读写、profile读【建议全勾】，生成token并复制，妥善保管。

5. 进入 <https://travis-ci.org> 或 <https://travis-ci.com>，用github账号登入，进入dashboard-setting，设置环境变量：变量名字: `GH_TOKEN` ，变量值: 你生成的TOKEN，tigger此项目。

6. 大约一分钟，这个项目就会变绿，如果没有，请检查日志；成功后进入仓库，选择 `gh-pages` 分支，你大概会看到以下文件：

```
gh-pages
  - re\
    - ...
  - 
```



[没写完，留坑]

copy /b dl.tar.bz2.* dl.tar.bz2
