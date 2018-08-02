# OpLin1.0
自动化运维平台：CMDB，CI / CD，DevOps的，资产管理，任务编排，持续交付，系统监控，运维管理，配置管理

# 运行环境介绍

系统：Windows

软件：Python3.6，Django1.11.3，MySQL5.7

注意：项目还在开发阶段，不能用于线上，如果想在线上用，自行完善哦，这里代码只提供思路和框架。
OpMan2.0

运行环境介绍

系统：苹果

软件：Python3.6，Django1.11.3，MySQL5.7

注意：项目还在开发阶段，不能用于线上，如果想在线上用，自行完善哦，这里代码只提供思路和框架。

全新UI



部署方法

创建uwsgi，nginx的进程运行的用户
useradd opman

安装MySQL5.7，并设置的my.cnf
character-set-server = utf8

character-set-client-handshake = FALSE

sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES,NO_AUTO_CREATE_USER

登录MySQL的，并授权项目账号
GRANT ALL PRIVILEGES ON devop.* TO dbuser_op@'%' IDENTIFIED BY 'devop@2015***';

MySQL的连接配置在opman-的Django / devop / settings.py
DATABASES = { 'default': { 'ENGINE': 'django.db.backends.mysql', 'NAME': 'devop', 'USER': 'dbuser_op', 'PASSWORD': 'devop@2015***', 'HOST': 'localhost', 'PORT': '', } }

安装的Redis
https://niubilety.com/redis%E5%85%A5%E9%97%A8%E4%B8%80/

执行ansible如果用密码的方式需要安装sshpass命令
yum install sshpass -y

克隆代码
cd /data/webroot

git clone https://github.com/hgz6536/opman-django.git

cd opman-django && pip3 install -i https://pypi.douban.com/simple/ -r requiremen
