* JDK的安装：这里版本用的jdk-8u144-windows-x64.exe，JDK的 安装这里就不讲了。
* 下载：WebLogic安装包fmw_12.2.1.3.0_wls.jar。[WebLogic下载地址](http://www.oracle.com/technetwork/middleware/weblogic/downloads/index.html)
* 在windows中打开命令窗口CMD

    ```
        java -jar xxxxx
    ```
  (你的WebLogic安装包的地址，还有注意用管理员身份打开CMD)
  ![实例](https://t1.picb.cc/uploads/2017/10/11/MeIYK.md.png)
* 接下来，它会弹出安装程序框，我们只介绍需要修改和比较重要的设置
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Mee3e.md.png)<br>
     选着跳过自动更新，下一步。<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MenuN.md.png)<br>
        这里为安装路劲，最好不要在主盘的根目录下。（这里只是方便演示）
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeC67.md.png)<br>
        选择第一个。点击下一步。<br>
        后面的步骤基本就是下一步和安装，按照默认来，这里就不介绍了。<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MelUs.md.png)<br>
        至此一个WebLogic Server基本组件安装完成，怎么测试安装成功？<br>
        当我们点击完成后，我们需要等待一会，他将会给我们弹出一个创建一个WebLogic域，这样我们就可以看服务是否开启了。<br>
* 当进行完上一步，会自动弹出新建域的窗口<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MecO6.md.png)<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Merdr.md.png)<br>
        我们开始创建域<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeA30.md.png)<br>
        请各位一定要记住这里设置的名称和账号，后面很多时候都会使用。<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MemPT.md.png)<br>
        选择开发模式和自定义JDK<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeHpF.md.png)<br>
        选择管理服务器<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Me4gM.md.png)<br>
        后面一直默认配置，然后安装，然后点击完成。<br>
* Windows启动WebLogic<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeGHt.md.png)<br>
        在WebLogic的安装目录下找到startWebLogic.cmd双击<br>
        Eg：E:\Weblogic12.2.1.3\user_projects\domains\base_domain<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Me8CJ.md.png)<br>
        然后进入http://localhost:7001/console网址，<br>
        可能需要等待一会，网站加载。然后输入之前设置的账号密码。<br>
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeMs1.md.png)<br>
        即为安装成功<br>

  
