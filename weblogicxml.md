# weblogic.xml配置
    weblogic Server允许通过设置weblogic应用程序扩展描述符（weblogic.xml）配置jsp容器，该文件通常位于web应用程序的web-inf目录下。
* keepgenerated
```
    <jsp-param>

       <param-name>keepgenerated</param-name>

       <param-value>true</param-value>

    </jsp-param>
```
        解释：该值表示是否在JSP编译过程中保存作为中间步骤生成的 Java 文件，如果设置为true，就可以在部署的环境查看jsp产生的.java文件，方便调试错误，否则编译完成后将删除所有中间 Java 文件。
* pageCheckSeconds
```
    <jsp-descriptor>

       <param-name>pageCheckSeconds</param-name>

       <param-value>-1</param-value>

    </jsp-descriptor>
``` 
        解释：pageCheckSecond表示检查JSP文件的时间间隔（秒），默认值是1，表示每隔1秒对JSP页面进行检查，检查JSP页面是否被修改、是否需要重新编译，

        如果已发生更改，还会检查依赖关系并递归重新加载，倘若为0，则表示总是检查页面。

        通常在系统上线前，需要对该默认值修改为-1，表示永不检查页面。修改为-1的一个缺点是：对于页面的修改需要重新部署整个WEB应用。
* precompile
```
    <jsp-descriptor>
    
           <param-name>precompile</param-name>
    
           <param-value>true</param-value>
    
    </jsp-descriptor>
```
        解释：如果设置为 true，当部署或重新部署 Web应用程序时，或启动 WebLogic时，WebLogic Server会自动预编译所有已修改的JSP。
* precompile-continue
```
    <jsp-descriptor>
    
           <param-name>precompile-continue</param-name>
    
           <param-value>true</param-value>
    
    </jsp-descriptor>
```
        解释：如果设置为 true，即使编译期间其中某些 JSP 失败，WebLogic Server也会继续预编译所有已修改的 JSP。仅当 precompile设置为true时才生效。
* servlet-reload-check-secs
```
    <container-descriptor>

       <servlet-reload-check-secs>-1</servlet-reload-check-secs>

    </container-descriptor>
```
        解释：该参数的默认值也是1，每隔1秒检查servlet是否被修改并需要重新编译。这里建议修改为-1，表示永不检查。
* prefer-web-inf-classes
```
    <container-descriptor>
    
           <prefer-web-inf-classes>true</prefer-web-inf-classes>
    
    </container-descriptor>
```
        解释：当该值为true时表示优先使用Web应用里加载的类。该参数常用来解决应用程序的jar包和weblogic下的jar包冲突。
* weblogic.xml
```
<? xml version="1.0" encoding="GB2312" ?>  <! DOCTYPE weblogic-web-app PUBLIC "-//BEA Systems, Inc.//DTD Web Application 8.1//EN" "http://www.bea.com/servers/wls810/dtd/weblogic810-web-jar.dtd"> 
<weblogic-web-app> 
</weblogic-web-app> 
```
* 这里只介绍了一些经常用的属性。
        更多查看文档：https://wenku.baidu.com/view/f27e776ef46527d3240ce0ab.html