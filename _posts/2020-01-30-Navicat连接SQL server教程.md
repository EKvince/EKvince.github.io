# 1.使用到的软件

SQL server 2019

Navicat Premium 15



# 2.配置SQL server登陆用户名

登陆Microsoft SQL Server Management Studio

![photo](../images/SQL%20server%20连接Navicat/2.1.png)

点开安全性->登录名->右键登录名->新建登录名

![photo](../images/SQL%20server%20连接Navicat/2.2.png)

如图创建新的服务器登陆账号

![photo](../images/SQL%20server%20连接Navicat/2.3.png)

服务器角色中勾选public和sysadmin

![photo](../images/SQL%20server%20连接Navicat/2.4.png)

用户映射中勾选需要访问到的数据库

![photo](../images/SQL%20server%20连接Navicat/2.5.png)

允许连接到数据库引擎

至此,配置登录用户名已经结束

# 3.配置服务器安全性

## 3.1配置服务器身份验证

![photo](../images/SQL%20server%20连接Navicat/2.6.png)

右击服务器，选择‘属性’，点击‘安全性’，服务器身份验证设置为SQL Server和Windows身份验证模式

## 3.2设置 SQL Server 网络配置

![photo](../images/SQL%20server%20连接Navicat/3.2.png)

打开WIN菜单,打开Sql Server Configuration Manager

![photo](../images/SQL%20server%20连接Navicat/3.2.2.png)

打开SQL Server 网络配置->MSSQLSERVER 的协议

确认TCP/IP已经启用

右键TCP/IP,属性,将IPALL的端口更改为1433(默认端口)

![photo](../images/SQL%20server%20连接Navicat/3.2.3.png)

同理设置好SQL Native Client 11.0配置中的客户端协议,确认TCP/IP已经启用,并且端口为1433

## 3.3 设置防火墙出入站规则

如果我们用Navicat访问服务器,就需要设置好防火墙

打开设置->Windows 安全中心->防火墙和网络保护->高级设置

![photo](../images/SQL%20server%20连接Navicat/4.1.png)

![photo](../images/SQL%20server%20连接Navicat/4.2.png)

左侧选择'入站规则',右栏选择新建规则

依次选择:

规则类型:端口

协议和端口: TCP,特定本地端口:1433

配置文件: 勾选''域''和''专用'',不勾选公用

名称:任意填写即可,建议填写较为便于识别的名称

---------------------------------------------------------


如果只是想使用Navicat连接,那么只要设置入站规则就可以了.

如果有其他需求,也可以同理设置出站规则

# 4.Navicat连接服务器

完成上述步骤后,就可以打开Navicat,点击连接,新建连接,选择SQL Server

按照刚才设置好的数据填写,即可连接数据库

![photo](../images/SQL%20server%20连接Navicat/5.1.png)

![photo](../images/SQL%20server%20连接Navicat/5.2.png)



