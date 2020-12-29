SSLVPN配置实验

1.  实验环境如图：

![](media/680a0ff1b733f1e2f1bcf6588b82a618.png)

1.  实现要求：

    1、SVPN中泛域名WEB访问，允许访问https://www.baidu.com,但不允许访问tieba.baidu.com不允许访问。

    2、SVPN中尝试什么情况下直接输入内网地址进行访问。

    3、EDR对接AF,AC,SIP,抓取恶意流量，观察rdp或ssh或smb或ftp暴破情况。

    4、EDR自动监测系统漏洞，并报告结果，不需要自动打补丁；定期进行基线检查并报告结果。

2.  实现步骤：

    实验1步骤如下：

3.  登录vpn配置泛域名

    ![](media/dc89653218e84c74a06e651e34d6bd04.png)

4.  登录ad配置dns

    ![](media/8c23b87e2d517ff1d853a7132e29ce69.png)

    ![](media/ab8fd9c92f500c58c109d23b56903dba.png)

    ![](media/21e095942e98234febc3f4e2ebb7ff92.png)

    ![](media/55881165ce15b42f47c01c3f320daceb.png)

    ![](media/cc49813cdc136fe103ab2b169d158931.png)

    ![](media/168e159a1b38c3a2a28f60c00d979f7f.png)

    ![](media/0cab59def6d517072247330590b94b45.png)

    ![](media/0a8d51b106ef65171b908fddcd9a70f3.png)

5.  登录af配置

    ![](media/9a87374291f5b17bf15491b981d71fd0.png)

    ![](media/b7d59f565867468c23f5e132b36ce579.png)

6.  登录长沙，修改dns

    ![](media/f4047d815b2e629fc13eeaf64d92da06.png)

    ![](media/dd5307b9da1d2352f86330f737ee216d.png)

7.  登录vpn新增应用

    ![](media/1514a29d7d782d94858028365b27930d.png)

    ![](media/c60ccff4b34e1c1863d97b2ccf8c98fe.png)

实验3需求如下：

>   EDR对接AF,AC,SIP,抓取恶意流量，观察rdp或ssh或smb或ftp暴破情况。

实验3步骤如下：

1.  EDR开启联动设置

![](media/4a17eac32d235f6d68f841af22889aa3.png)

1.  EDR联动AC

在AC上连接EDR

![](media/516f0b42cd58ccf1467f232ec03d9b60.png)

![](media/d89e0a1976f2e6f416d478541a0179e7.png)

连接成功

1.  EDR联动SIP

在SIP上操作

![](media/8447aff8017130d1e5eb17002d9dedc2.png)

![](media/56cae985f19dc5ababea94180e2f65ab.png)

![](media/65383d4be8543c5caff095b3af1c65e7.png)

1.  EDR联动AF

![](media/815cc3fc71797b358899eddc0817b07b.png)

![](media/41805e9dc87f801fb43d9528d091f6f9.png)

1.  EDR上查看联动状态

![](media/5fd58ed17a5da57abc73febb5c0d906f.png)

1.  观察rdp或ssh或smb或ftp暴破情况

现将edr终端软件包安装在172.150.3.150 172.172.3.100上

![](media/7510c3bd6faeb56905499394eb1692ff.png)

cmd进入爆破工具目录 C:\\hydra-8.1-windows

使用命令 hydra.exe -t 4 -V -l administrator -P Passwd.txt rdp://172.172.3.150

hydra.exe -t 4 -V -l root -P Passwd.txt ssh://172.172.3.100

对两个ip进行爆破

![](media/b8fb84d2b0724d760c8c535d7b46eff8.png)

![](media/2398b1d644401c76c855f3291f4f8c25.png)
