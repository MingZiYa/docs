
## 数据库安装

### 环境:
  * 系统: Centos8.2
  * 数据库版本: mysql 5.7

### 安装

1. 进入官方网站 `<https://dev.mysql.com/downloads/repo/yum/>`
  1. 选择相应的Centsos版本，由于我使用的是*`Centos 8.2`* , 所有我选择 

    * Red Hat Enterprise Linux 8 / Oracle Linux 8 (Architecture Independent), RPM Package 
	  (mysql80-community-release-el8-1.noarch.rpm)  源文件

  2. 使用*wget*下载源文件

	* https://repo.mysql.com// + (要下载的源文件)  
	`https://repo.mysql.com//mysql80-community-release-el8-1.noarch.rpm`

2. 安装数据源	
   
    `rpm -Uvh https://repo.mysql.com//mysql80-community-release-el8-1.noarch.rpm`
   
3. 安装mysql

	`yum install mysql-community-server` (提示y/n 按y继续)  
	输入 *y* 等待安装完成

4. 启动mysql服务

	`service mysqld start`  

	* 8.0的版本使用 
	`systemctl start mysqld.service`

5. 查看服务

	`service mysqld status`
	* 8.0使用以下  
	`systemctl status mysqld.service` (有active (running)绿色显示成功)

6. 使用grep命令查看日志 `/var/log/mysqld.log` 

	`grep 'temporary password' /var/log/mysqld.log`  
	提示如下信息**(root@localhost: GM&=Sda;a2Rk)**

7. 使用刚才查看的密码 登陆并修改密码

	`mysql -uroot -p`  
	提示输入密码 **GM&=Sda;a2Rk**

8. 进入mysql,更改超级管理员的密码为*root*

	`ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';`

9. 保存修改

	`flush privileges`

10. 退出mysql登录

	`quit`