# network_graph
## 系统部署
1、yum update  
2、yum install git
## 安装python环境
3、yum install python36...  
4、yum install pip36...  
5、pip install django  
6、pip install py2neo
## 安装java jdk
7、yum install java-1.8.0-openjdk
## 安装neo4j
8、wget https://neo4j.com/artifact.php?name=neo4j-community-3.4.12-unix.tar.gz  
9、tar -xzvf neo4j-community-3.4.12-unix.tar.gz
## 导入数据
10、neo4j-admin import --nodes nodes.csv --relationships links.csv
## 修改neo4j配置 远程访问并修改密码
11、vim neo4j.conf  
12、把54行dbms.connectors.default_listen_address=0.0.0.0注释去掉  
13、远程访问neo4j数据库 http://IP:7474/ 修改初始密码
## 拉取代码
14、git clone https://github.com/iaboaix/NetworkGraph.git
## 启动neo4j django
15、nohup ./neo4j console &  
16、nohup python3 manage.py runserver --insecure 0.0.0.0:80 & 

## tips
启动之前，将服务器外网IP地址加入django settings.py 的 ALLOWED_HOSTS  
若django sqlite报错  
vim /usr/local/lib64/python3.6/site-packages/django/db/models/base.py  
将版本检测代码段注释掉  
若django debug=false之后 静态文件找不到 启动时添加--insecure  
![Image text](https://github.com/iaboaix/NetworkGraph/blob/master/preview.jpg)
