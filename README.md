# ansible_mysql_master_slave
#### 使用ansible部署mysql主从复制

##### 1. 安装ansible(部署机执行)

```
yum install epel-release-y

yum install ansible
```

##### 2. 部署机执行

```
ansible-playbook -i hosts.ini start_deploy.yml
```

##### 3. 脚本文件说明

 hosts.ini

> 所有的变量都在这个文件中修改

```
[mysql_servers]
ip ansible_ssh_user="部署机器用户" ansible_ssh_pass="用户登录密码" mysql_role=master server_id=1

[mysql_servers:vars]
master_ip
mysql_version

# mysql的临时密码，此处不用修改
mysql_root_tmp_password

# mysql的root密码，这里可以自定义
mysql_root_password

mysql_repl_user=mysql主从用户
mysql_repl_password
```

