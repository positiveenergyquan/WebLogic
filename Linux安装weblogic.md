* JDK的安装：这里版本用的jdk-8u144-linux-x64.rpm。
* 下载：WebLogic安装包fmw_12.2.1.3.0_wls.jar。[WebLogic下载地址](http://www.oracle.com/technetwork/middleware/weblogic/downloads/index.html)
* 将JDK和WebLogic的安装包放在opt文件夹下
* 创建weblogic组和用户，并且设置密码
```
groupadd weblogic
useradd -g weblogic weblogic
passwd weblogic
```
* 安装JDK(注意windows和linux的jdk安装包是不一样的)
```
rpm -ivh jdk-8u144-linux-x64.rpm
```
* 设置用户Java环境变量
```
vim /home/weblogic/.bashrc
```
添加语句
```
JAVA_HOME=XXXXX (你的JDK路径)
PATH=$PATH:$JAVA_HOME/BIN
export JAVA_HOME PATH
```
更新环境（马上生效不用重启）
```
source /home/weblogic/.bashrc
```
* 安装WebLogic前期工作

 设置/opt/目录权限
```
chmod -R 777 /opt/
```
 准备oraLnst.loc文件,写入信息。在opt目录下
```
vim oraLnst.loc
```
```
inst_group=weblogic 
inventory_loc=/opt/weblogic/oraInventory1
```
 准备wls.rsp,写入信息。在opt目录下
```
[ENGINE] 
#DO NOT CHANGE THIS. 
Response File Version=1.0.0.0.0 
[GENERIC] 
ORACLE_HOME=/opt/weblogic/Oracle/Middleware 
INSTALL_TYPE=WebLogic Server 
MYORACLESUPPORT_USERNAME= 
MYORACLESUPPORT_PASSWORD=<SECURE VALUE> 
DECLINE_SECURITY_UPDATES=true 
SECURITY_UPDATES_VIA_MYORACLESUPPORT=false 
PROXY_HOST= 
PROXY_PORT= 
PROXY_USER= PROXY_PWD=<SECURE VALUE> 
COLLECTOR_SUPPORTHUB_URL=
```
* 安装
```
java -jar fmw_12.2.1.0.0_wls.jar -silent -responseFile /opt/wls.rsp -invPtrLoc /opt/oraInst.loc
```
* 安装可能遇到的问题Checking swap space: 0 MB available, 524 MB required. Failed <<<<
        参考文献http://www.cnblogs.com/a9999/p/6957280.html就能解决。
* 创建域（文件中直接就可以看出端口和用户名，密码，根据自己需要修改）
```
vim create_domain.rsp
```
```
read template from "/opt/weblogic/Oracle/Middleware/wlserver/common/templates/wls/wls.jar";
set JavaHome "/opt/jdk1.8.0_60";               
set ServerStartMode "dev";
find Server "AdminServer" as AdminServer;
set AdminServer.ListenAddress "";
set AdminServer.ListenPort "8001";
set AdminServer.SSL.Enabled "true";
set AdminServer.SSL.ListenPort "8002";
//We can directly create a new managed server.
create Server "base" as BASE;
set BASE.ListenAddress "";
set BASE.ListenPort "8003";
//set BASE.SSL.Enabled "true";
//set BASE.SSL.ListenPort "8004″;
//Create Machine
create Machine "base" as Machinename;
//use templates default weblogic user
find User "weblogic" as u1;
set u1.password "weblogic123";
//create a new user
create User "weblogic2" as u2;
set u2.password "weblogic123";
write domain to 
"/opt/weblogic/Oracle/Middleware/user_projects/domains/base_domain/";
// The domain name will be "demo-domain"
close template;
```
* 运行配置
```
./config.sh -mode=silent -silent_script=/opt/create_domain.rsp -logfile=/opt/weblogic/create_domain.log
```
* 开启服务器
```
cd  /opt/weblogic/Oracle/Middleware/user_projects/domains/base_domain/
./startWebLogic.sh& 
```
* 检查是否安装成功
        http://你机器IP:8001/console
       （网页打开即为成功，住8001使我们配置上面 create_domain.rsp配置域是将默认的7001改为了8001，所以这里端口号我们访问8001，具体看自身需要）