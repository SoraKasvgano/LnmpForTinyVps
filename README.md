# LnmpForTinyVps

Author:https://www.gubo.org/debian-lemp-script/ & Actgod

one key script to install lnmp on tiny small ram vps.
backup only.

# Debian 10 五分钟/一键安装Wordpress
```
#Debian8下载脚本
wget http://w3.gubo.org/pubfiles/tylemp/10/tylemp.sh 
#安装稳定版Nginx+PHP+MariaDB
bash tylemp.sh stable
#安装wordpress，www.yourdomain.com即为你的域名
bash tylemp.sh wordpress www.yourdomain.com
```

# 五分钟/一键安装typecho
```
#Debian8下载脚本
wget http://w3.gubo.org/pubfiles/tylemp/10/tylemp.sh 
#安装稳定版Nginx+PHP+MariaDB
bash tylemp.sh stable
#安装Typecho，www.yourdomain.com即为你的域名，数据库用户名和密码会显示在屏幕上
bash tylemp.sh typecho www.yourdomain.com
```

# 更改SSH端口
```
#更改端口为22022，数字可以自由更换
bash tylemp.sh sshport 22022
#重启使新端口生效
reboot
```

# 命令列表说明
```
bash tylemp.sh system # 优化系统，删除不需要组件，dropbear替代sshd 
bash tylemp.sh exim4 # 更轻量级邮件系统 
bash tylemp.sh mysql # 安装mysql 
bash tylemp.sh nginx # 安装nginx，默认一个进程，可调整
bash tylemp.sh php # 安装php，包含php5-gd，可使用验证码
bash tylemp.sh stable # 安装上面所有，软件是debian官方stable源，版本较旧
bash tylemp.sh wordpress www.yourdomain.com # 一键安装wordpress, 数据库自动配置好。 
bash tylemp.sh vhost www.yourdomain.com # 一键安装静态虚拟主机。
bash tylemp.sh dhost www.yourdomain.com # 一键安装动态虚拟主机，方便直接上传网站程序。
bash tylemp.sh typecho www.yourdomain.com # 安装typecho，提供数据库名，密码等自主添加完成安装
bash tylemp.sh phpmyadmin www.yourdomain.com # 一键安装phpmyadmin 数据库管理软件，用http://www.yourdomain.com/phpMyAdmin访问 
bash tylemp.sh addnginx 2 #调整nginx进程，这里2表示调整后的进程数，请根据vps配置（cpu核心数）更改
bash tylemp.sh sshport 22022 #更改ssh端口号22022，建议更改10000以上端口。重启后生效。
bash tylemp.sh rainloop www.yourdomain.com  # 增加Gmail的web客户端一键安装
bash tylemp.sh carbon www.yourdomain.com  # 增加Carbon Forum的一键安装
```


## 配置文件列表

```
/etc/nginx/nginx.conf #nginx配置文件，可根据vps的cpu核心数更改进程数最大限度利用

/etc/php5/fpm/php.ini #php配置文件

~/.my.cnf #mysql root密码保存文件

/etc/nginx/conf.d/ #nginx下各个具体网站配置文件所在文件夹
```

# 日志Log文件列表
```
/var/log/nginx #nginx的log文件所在文件夹，所有网站都在一个文件中

/var/log/php5-fpm.log #php的log文件，所有网站都在一个文件中
```

# Tyleamp.sh相关命令列表参考

这些都是系统自带的, 列出来供参考
```
#MySQL命令

service mysql {start|stop|status|restart|reload|force-reload}

#Nginx命令

service nginx {start|stop|status|restart|reload|force-reload}

#查看php版本, 例如7.0.33-0+deb9u8, 大版本就是7.0

php -v

#查看php版本, Debian9的大版本号是php7.0, 则

service php7.0-fpm {start|stop|status|restart|reload|force-reload}
```
