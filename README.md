
自己搭梯子就是用更少的钱去独享这个科学上网的高速服务；而购买别人的科学上网就是跟众多的人一起同时使用这个翻墙工具，速度肯定不如独享的快速，同时也更不安全。

一、服务器选择
搭建梯子要用到海外服务器（比如香港、日本、韩国、新加坡、美国等服务器） 

如果你嫌自己搭建梯子比较麻烦，还可以直接购买，推荐一下我在用的梯子，节点多、速度快、稳定。

https://github.com/yiyi1979/VPN_Tool_for_2026

二、梯子搭建教程
本梯子使用的V2ray多合一脚本，支持VMESS+websocket+TLS+Nginx、VLESS+TCP+XTLS、VLESS+TCP+TLS等。

V2ray一键脚本功能强大，支持常规VMESS协议、VMESS+websocket+TLS+Nginx、VLESS+TCP+XTLS、VLESS+TCP+TLS等多种组合，支持CentOS 7/8、Ubuntu 16.04以上、Debian 8以上系统，以及相关衍生系统。

1、V2ray一键脚本使用步骤如下：
①、境外服务器准备工作
如果用VMESS+WS+TLS或者VLESS系列协议，则还需一个域名。对域名没有要求，国内/国外注册的都可以，不需要备案，不会影响使用，也不会带来安全/隐私上的问题。

值得一提的是本V2ray一键脚本支持ipv6 only服务器，但是不建议用只有ipv6的VPS用来科学上网。

②、开放80和443端口
如果vps运营商开启了防火墙（阿里云、Ucloud、腾讯云、AWS、GCP等商家默认有，搬瓦工/hostdare/vultr等商家默认关闭），请先登录vps管理后台放行80和443端口，否则可能会导致获取证书失败。此外，本脚本支持上传自定义证书，可跳过申请证书这一步，也可用在NAT VPS上。

③、ssh连接到服务器。
需要下载一个ssh客户端，然后用ssh登录服务器。（购买服务器后，会给你相关的IP、帐号、密码）教程略，网上有很多，不会的自己搜一下。

④、命令安装脚本
复制（或手动输入）下面命令到终端

bash <(curl -sL https://storage.googleapis.com/tiziblog/setup.sh)

按回车键，将出现如下操作菜单。

如果菜单没出现，CentOS系统请输入：

yum install -y curl

Ubuntu/Debian系统请输入：

sudo apt install -y curl

然后再次运行上面的命令：

![图片](https://github.com/yiyi1979/-VPN-/blob/main/3536fd4d-623c-474e-b69d-a952d8c4db48.png)

目前V2ray一键脚本支持以下功能：
VMESS，即最普通的V2ray服务器，没有伪装，也不是VLESS

VMESS+KCP，传输协议使用mKCP，VPS线路不好时可能有奇效

VMESS+TCP+TLS，带伪装的V2ray，不能过CDN中转

VMESS+WS+TLS，即最通用的V2ray伪装方式，能过CDN中转，推荐使用

VLESS+KCP，传输协议使用mKCP

VLESS+TCP+TLS，通用的VLESS版本，不能过CDN中转，但比VMESS+TCP+TLS方式性能更好

VLESS+WS+TLS，基于websocket的V2ray伪装VLESS版本，能过CDN中转，有过CDN情况下推荐使用

VLESS+TCP+XTLS，目前最强悍的VLESS+XTLS组合，强力推荐使用（但是支持的客户端少一些）

trojan，轻量级的伪装协议

trojan+XTLS，trojan加强版，使用XTLS技术来提升性能

**注意：**目前一些客户端不支持VLESS协议，或者不支持XTLS，请按照自己的情况选择组合

5. 按照自己的需求选择一个方式。
例如6，然后回车。接着脚本会让你输入一些信息，也可以直接按回车使用默认值。需要注意的是，对于要输入伪装域名的情况，如果服务器上有网站在运行，请联系运维再执行脚本，否则可能导致原来网站无法访问！
![图片](https://github.com/yiyi1979/-VPN-/blob/main/3210985378.png)


6. 脚本接下来会自动运行，一切顺利的话结束后会输出配置信息：
![图片](https://github.com/yiyi1979/-VPN-/blob/main/1184729940.png)

到此服务端配置完毕，服务器可能会自动重启（没提示重启则不需要），windows终端出现“disconnected”，mac出现“closed by remote host”说明服务器成功重启了。

对于VLESS协议、VMESS+WS+TLS的组合，网页上输入伪装域名，能正常打开伪装站，说明服务端已经正确配置好。如果运行过程中出现问题，请在本页面下方查找解决方法或留言。
