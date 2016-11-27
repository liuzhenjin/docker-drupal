> 宁皓网推荐使用 Docker 运行 Drupal ：）

## 服务列表
- db：使用 mariadb 作为应用的数据库
- php：解释 php 脚本，使用 php-fpm
- web：使用 NGINX 作为应用的 web 服务器
- console：常用工具
- redis：缓存
- phpmyadmin：管理数据库的 web 界面

## 介绍与启动

在本地电脑，如果你把 Drupal 放到共享的数据卷去运行，速度会非常慢。找到了个用 [unison](https://github.com/EugenMayer/docker-sync) 同步文件的方法，可以非常有效的解决这个问题。这个方法目前只能用在 macOS 上。

[宁皓网](http://ninghao.net) 先下载 docker for windows 或 docker for mac ，然后启动 docker 。再执行下面这些步骤：

1 → 安装

```
gem install docker-sync
brew install fswatch
brew install unison
brew install rsync
```

1 → 克隆仓库到本地
```
git clone git@github.com:ninghao/docker-drupal.git
```
2 → 进入项目所在目录
```
cd docker-drupal
```
3 → 运行同步服务
```
docker-sync start
```
4 → 运行应用需要的服务
```
docker-compose -f docker-compose-dev.yml up -d
```
5 → 在浏览器里打开
```
http://localhost:8080
```
6 → 登录
用户名：wanghao
密码：123123

[ninghao.net](http://ninghao.net)
