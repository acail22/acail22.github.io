---
layout:     post
title:     ipsecvpn_sangforvpn
subtitle:   ipsecvpn_sangforvpn
date:       2020-12-01
author:     BY Acail
header-img: img/post-bg-2.jpg
catalog: true
tags:	
    - sangfor
    - test
---

IPSECVPN建立过程实验

1.  实验环境如图：

![](media/37e019a69ce54ee18df5c77a344acdad.png)

1.  实现要求：实现深圳172.172.2.200和长沙202.96.139.99建立VPN通道。

2.  实验步骤如下：

    1、在深圳AF1设备上建立端口映射，映射UDP500和UDP4500端口到172.172.2.200上。

![](media/7df6e0da296b01bd1253ce45d2d88df3.png)

1.  在172.172.2.200上配置IPSECVPN。

第一阶段配置

![](media/afe1e27d568c6df772147d4ad792c2a1.png)

点击高级后配置

![](media/6706f7d6b4f41f38a66887e51b9a6cdb.png)

第二阶段配置

入站策略

![](media/0e2880df779290e206e0c7c0c9a4a808.png)

出站策略

![](media/57164457a428ccfee2cf34af1b8e87bd.png)

1.  长沙端配置

第一阶段

![](media/ab5c45b03b5e562bb7bcbdabd0d3b08c.png)

高级配置

![](media/a7d8c5cab5b0dd2d944cb9c638e3da0d.png)

第二阶段

出站策略

![](media/ce9cab887b88374116dee1216bb87775.png)

入站策略

![](media/5b2fc62a291278b872e4355036a8b586.png)

1.  实验验证如下：

1、深圳vpn状态

![](media/096de7107c5975c11f9c4c1f14686921.png)

1.  长沙vpn状态

![](media/d8dded67a6164a1006a017fb86ee2542.png)

3、测试终端互ping

![](media/dd84bc4c85109e74b8af4b13d3de1908.png)

![](media/c114012750ed53704f6853c8ff9e4ae8.png)

测试成功

SANGFORVPN实验操作步骤

1.  实验环境如图：

![](media/37e019a69ce54ee18df5c77a344acdad.png)

1.  实现要求：实现深圳172.172.2.200和长沙202.96.139.99建立sangforvpn通道。

2.  实验步骤如下：

3.  在深圳AF1设备上建立端口映射，映射TCP/UDP4009端口到172.172.2.200上。

    ![](media/496b6afbe14acc889733d3309bcd6a1f.png)

4.  在深圳SSLVPN设备上，配置sangforvpn功能

    ![](media/d1869ba69d270f23ffcdf539e9d465e1.png)

    webagent测试

    ![](media/bbc9e39ba7321a2b9deef517d4324f04.png)

    新增用户及组

    ![](media/348a9e2c8f92fb4511d56b1ab291cbd9.png)

    ![](media/6a2ec1a5ca941a4aaabeab01fbc408cc.png)

    配置AF路由

    ![](media/9ce4d2d17fee934c9b8b2534461636a0.png)

5.  长沙sangforvpn配置

![](media/c3716396021fce305e164be2d513cf94.png)

1.  长沙vpn状态

    ![](media/320e1feb855b461f9b7adff4719c0ed7.png)

2.  深圳vpn状态

    ![](media/a6852372cf6bb315a66b7c1ee0d9af2b.png)

    ![](media/9ea31f1e655558741204f89fa12859fd.png)

    ![](media/5eed945a85732a930726b237ccdc2d7b.png)

证明sangforVPN成功连通。
