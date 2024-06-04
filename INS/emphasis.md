# Emphasis

## 第1章 引言

1. <span style="background-color:yellow">信息安全的四个目标：

答：<u>保密性、完整性、可用性、合法使用</u>。


2. <span style="background-color:yellow">信息系统中常见的威胁：

答：

基本威胁有<u>信息泄露、完整性破坏、拒绝服务、非法使用</u>；

主要可实现威胁有<u>渗入威胁、植入威胁</u>，前者包括<u>假冒、旁路控制、授权侵犯</u>，后者包括<u>特洛伊木马、陷门</u>；

潜在威胁有<u?>网络窃听、流量分析、操作人员不慎导致信息泄露、媒体废弃物导致信息泄露</u>。


3. <span style="background-color:yellow">什么是安全策略？安全策略分几个等级？

答：

安全策略指<u>某个安全域内施加给所有与安全相关活动的一套规则</u>。

安全策略分为<u>安全策略目标、机构安全策略、系统安全策略</u>三个等级。


4. <span style="background-color:yellow">什么是访问控制策略？它有哪些类型？这些访问控制策略有何区别？

答：

访问控制策略隶属于<u>系统级安全策略</u>，其迫使计算机系统和网络自动地执行<u>授权</u>。

访问控制策略分为<u>强制访问策略、自主访问策略</u>，也分为<u>基于角色的访问控制、基于任务的访问控制、基于对象的访问控制</u>。


5. <span style="background-color:yellow">什么是安全域？划分安全域原则是什么？如何划分安全域？

答：安全域指<u>属于某个组织机构的一系列处理进程和通信资源</u>。划分安全域的原则是<u>最小权限原则，或最小知悉原则</u>。


6. <span style="background-color:yellow">什么是授权？用户授权有何作用？常用于哪些应用场景？

答：授权是安全策略的一个基本组成部分，它指<u>主体（用户、终端、程序等）</u>对<u>客体（数据、程序等）</u>的支配权限，规定了谁可以对什么做些什么。


7. <span style="background-color:yellow">安全攻击分为几大类？常见的攻击形式有哪些？

答：

安全攻击可分为<u>被动攻击、主动攻击</u>，前者包括<u>信息泄露、流量分析</u>，后者包括<u>伪装、重放、消息篡改、拒绝服务</u>。

常见形式有<u>口令窃取、欺骗攻击、缺陷和后门攻击、认证失效、协议缺陷、信息泄露、指数攻击、拒绝服务攻击</u>。

8. <span style="background-color:yellow">熟记X.800标准中的5类安全服务和8种特定安全机制，并简述安全服务与安全机制之间的关系。

答：

5类安全服务为<u>认证、访问控制、数据保密性、数据完整性、不可否认性</u>。

8种安全机制为<u>加密、数字签名、访问控制、数据完整性、认证交换、流量填充、路由控制、公证</u>。

一类安全服务由一种或多种安全机制实现。

<p align="center">
    <img width="400" src="figs/1-1.png"/><br>
    <b>图1 安全服务与安全机制的关系</b>
</p>


9. <span style="background-color:yellow">理解并画出网络安全模型和网络访问模型。

答：

<p align="center">
    <img width="350" src="figs/1-2.png"/>
    <img width="350" src="figs/1-3.png"/><br>
    <b>图2 网络安全模型与网络访问安全模型</b>
</p>


## 第2章 计算机网络基础

1. <span style="background-color:yellow">熟记OSI的七层参考模型、TCP/IP的四层模型。

答：

OSI七层参考模型为<u>物理层、数据链路层、网络层、传输层、会话层、表示层、应用层</u>。

TCP/IP的四层模型为<u>网络接口层、网络层、传输层、应用层</u>。


2. <span style="background-color:yellow">什么是面向连接的服务？什么是无连接的服务？

答：面向连接的服务（如TCP）指通信双方首先需要建立一条信道，方可进行数据传输；无连接的服务（如IP、UDP）指双方无需事先建立信道，数据分组无序传输。


3. <span style="background-color:yellow">必须知道IPv4及IPv6地址的格式及长度。

答：IPv4为32位，IPv6为128位。


4. <span style="background-color:yellow">必须知道MAC地址的长度。

答：MAC地址为48位。


5. <span style="background-color:yellow">IP地址与MAC地址转换靠哪个网络协议？

答：依靠ARP协议（数据链路层）。


6. <span style="background-color:yellow">IPv4的地址分哪几类？给定一个IP地址，要能够分析判断出该地址属于哪一类地址。

答：IPv4的地址分为A、B、C、D、E五类。给定一个IP，根据其点分十进制表示，可判断属于哪一类地址：

<p align="center">
    <img width="400" src="figs/2-1.png"/><br>
    <b>图3 判断IP地址类别的方法</b>
</p>


7. <span style="background-color:yellow">给定一个IPv4地址和子网掩码，要求能够计算出网络地址。

答：网络地址等于IPv4地址与子网掩码的逐位与。


8. <span style="background-color:yellow">熟悉CIDR的表示方法。给定一个CIDR地址，能够写出该地址的表示范围。如一个CIDR地址为：128.14.32.0/20，它表示的地址块范围和子网掩码是什么？

答：CIDR地址的表示方法为<u>IP地址/net-id位数</u>。

CIDR地址128.14.32.0/20的子网掩码为255.255.240.0，地址块范围为128.14.32.1-128.14.47.254。


9. <span style="background-color:yellow">什么是“端口号”？“端口号”在网络通信中起什么作用？

答：

端口用于标识一台计算机中特定<u>进程</u>所提供的服务。

端口号在网络通信中起到的作用为区分同一台设备上不同的应用程序，为其提供端对端的数据通道连接。


## 第3章 

1. <span style="background-color:yellow">熟记http/ftp/telnet/pop3/smtp/imap/ssh/dns等常用通信协议的功能。

答：

|  协议     |   功能        |
|  :----    |   :----      | 
| HTTP(TCP 80)        |  超文本传输协议是一个<u>客户端</u>和<u>服务器端</u>请求和应答的标准，是互联网上应用最广泛的一种网络协议         |
| FTP(TCP 20/21)       |  文本传输协议是Internet文件传送的基础         |
| Telnet(TCP 23)    |  远程登陆协议是Internet远程登陆服务的标准协议和主要方法         |
| POP3(TCP 110)      |  邮局协议是一个邮件接收协议         |
| SMTP(TCP 25)      |  简单邮件传输协议用于发送邮件         |
| IMAP4(TCP 143,993)      |  消息访问协议是一个邮件获取协议         |
| SSH(TCP 22)       |  安全壳协议是一种在不安全网络上建立安全远程登陆或其他安全网络服务的协议         |
| DNS(TCP 53)       |  域名系统协议用于实现域名与IP地址之间的映射         |


2. <span style="background-color:yellow">熟记一些常用网络协议的端口号。

答：如前。


3. <span style="background-color:yellow">网际层协议有哪些？传输层协议有哪些？应用层协议有哪些？

答：


4. <span style="background-color:yellow">为什么要进行网络地址转换（NAT）？

答：


5. <span style="background-color:yellow">ARP协议的作用是什么？

答：


6. <span style="background-color:yellow">为什么UDP比TCP协议更加容易遭到攻击？

答：


7. <span style="background-color:yellow">IMAP协议与POP3协议相比，它的安全性有哪些提升？

答：


8. <span style="background-color:yellow">SSH协议与Telnet协议相比，它的安全性有哪些提升？

答：


9. <span style="background-color:yellow">什么是ICMP重定向攻击？如何防止此类攻击？

答：


10. <span style="background-color:yellow">在网络中，为什么不能仅仅靠识别数据包的IP地址，来判断一个数据包就是来自该IP地址的主机？

答：

