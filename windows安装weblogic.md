* JDK的安装：这里版本用的jdk-8u144-windows-x64.exe，JDK的 安装这里就不讲了。
* 下载：WebLogic安装包fmw_12.2.1.3.0_wls.jar。[WebLogic下载地址](http://www.oracle.com/technetwork/middleware/weblogic/downloads/index.html)
* 在windows中打开命令窗口CMD

    ```
        java -jar xxxxx
    ```
  (你的WebLogic安装包的地址，还有注意用管理员身份打开CMD)
  ![实例](https://t1.picb.cc/uploads/2017/10/11/MeIYK.md.png)
* 接下来，它会弹出安装程序框，我们只介绍需要修改和比较重要的设置
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Mee3e.md.png)
        选着跳过自动更新，下一步。
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MenuN.md.png)
        这里为安装路劲，最好不要在主盘的根目录下。（这里只是方便演示）
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeC67.md.png)
        选择第一个。点击下一步。
        后面的步骤基本就是下一步和安装，按照默认来，这里就不介绍了。
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MelUs.md.png)
        至此一个WebLogic Server基本组件安装完成，怎么测试安装成功？
        当我们点击完成后，我们需要等待一会，他将会给我们弹出一个创建一个WebLogic域，这样我们就可以看服务是否开启了。
* 当进行完上一步，会自动弹出新建域的窗口
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MecO6.md.png)
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Merdr.md.png)
        我们开始创建域
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeA30.md.png)
        请各位一定要记住这里设置的名称和账号，后面很多时候都会使用。
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MemPT.md.png)
        选择开发模式和自定义JDK
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeHpF.md.png)
        选择管理服务器
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Me4gM.md.png)
        后面一直默认配置，然后安装，然后点击完成。
* Windows启动WebLogic
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeGHt.md.png)
        在WebLogic的安装目录下找到startWebLogic.cmd双击
        Eg：E:\Weblogic12.2.1.3\user_projects\domains\base_domain
    ![实例](https://t1.picb.cc/uploads/2017/10/11/Me8CJ.md.png)
        然后进入http://localhost:7001/console网址，
        可能需要等待一会，网站加载。然后输入之前设置的账号密码。
    ![实例](https://t1.picb.cc/uploads/2017/10/11/MeMs1.md.png)
        即为安装成功

  