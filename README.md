# 新手快速搭建VPN科学上网教程3分钟一键脚本搞定 

此教程面向新手快速搭建VPN科学上网教程3分钟一键脚本搞定。

# 第一部分：环境信息

- 服务器系统：CentOS 7 以上版本系统兼容本教程
- VPS：我使用的是 Vultr
- 手机和电脑都支持搭建

# 第二部分：创建服务器

# 国外服务器vps注册创建教程


很多时候我们需要使用 Google 查询第一手资料，比如官方的文档网站，或者一些文献，虽然市面上有一些 VPN 工具，但是它们不是很稳定，并且不是很安全，比较好的方式就是自己搭建一个属于自己的 VPN 服务，自己掌控。

## 优惠购买云服务器vultr

在搭建之前需要一台境外的云服务器，而 [vultr](https://www.vultr.com/?ref=8944093-8H) 服务商比较稳定，安全，相当于境内的阿里云。

值得说的一点是， [vultr](https://www.vultr.com/?ref=8944093-8H) 给新用户的福利相当给力，充值 10 美元就可以获取 100 美元，你可以点击 [vultr 专属赠送新用户 100 美元](https://www.vultr.com/?ref=8944093-8H) 进去抢先注册。

右上角有注册按钮，你也可以切换成中文界面：

<img width="1446" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119019442-be0cc500-b98c-11eb-895b-0d6300dce93d.png">

![](https://user-images.githubusercontent.com/84239400/119019760-0d52f580-b98d-11eb-9837-aba0990f1dfb.png)

接着使用邮箱和密码就可以注册了。

![](https://user-images.githubusercontent.com/84239400/119020042-4ee3a080-b98d-11eb-8341-bfc30f4b103c.png)

进去之后你可以看到这个页面，说明你已经通过 [vultr 专属优惠链接](https://www.vultr.com/?ref=8872890-6G) 获得了 100 美元赠送的资格：

![](https://user-images.githubusercontent.com/84239400/119020173-733f7d00-b98d-11eb-8ecc-a1afeb556fe6.png)

现在你只要选择支付宝充值 10 美元以上，就可以获得额外赠送的 100 美元。

![](https://user-images.githubusercontent.com/84239400/119020280-966a2c80-b98d-11eb-9113-8f5f0b75c5ea.png)

接下来就可以在这个平台选购云服务器了。

点击页面左边菜单栏的 「Products」进入服务器选购页面。

### Choose Server 选择服务器

选择 Cloud Compute 即可：

![](https://user-images.githubusercontent.com/84239400/119020373-af72dd80-b98d-11eb-8478-02d735b82709.png)

### Server Location

服务器的位置，可以选择美国地区，比如纽约：

![](https://user-images.githubusercontent.com/84239400/119020467-cadde880-b98d-11eb-8927-d3d837bbc20c.png)

选择服务器配置，看个人情况。$5适合个人搭梯子。

### Server Type

服务器类型，CentOS 8 x64 系统：

<img width="1297" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119020720-198b8280-b98e-11eb-9df3-19bf5a187a1e.png">

### Server Size

内存，个人使用10G完全够用，这里选择3.5美元一个月，性价比高，注意不要选择IPv6 ONLY的，要不然无法搭建使用。

<img width="1240" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119020895-4a6bb780-b98e-11eb-9ac8-3cdd4f4397de.png">

选择完了之后，下面的其它东西都不需要填，直接点击右下角 Deploy Now 就可以了：

![](https://user-images.githubusercontent.com/84239400/119020981-68391c80-b98e-11eb-9f16-00c75de88eeb.png)

这时候你就拥有了自己的一台云服务器了：

<img width="1261" alt="VPN搭建教程" src="https://user-images.githubusercontent.com/84239400/119021075-86068180-b98e-11eb-82a9-71edb9934f23.png">


点击 Cloud Instance ，可以看到你服务器的 IP 地址和密码：

<img width="1308" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119021183-a20a2300-b98e-11eb-8ff4-7f18d3e3bb80.png">


## 连接到你的服务器

### windows 系统连接到 vultr 服务器

windows 可以下载[PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)工具。

打开之后选择 session，将你在 vultr 网上得到的服务器 ip 复制过来，输入到这里：

![](https://user-images.githubusercontent.com/84239400/119023900-037fc100-b992-11eb-85ea-525a61a69657.png)

Port 默认 22，Connection Type 选择 SSH，接着点击 Open，连接进去之后输入你云服务器的密码。

### Linux 和 MacOS 连接到 vultr 服务器

Linux 和 MacOS 可以打开终端，使用如下命令连接：

```
ssh root@xx.xx.xxx.xx
```

`xx.xx.xxx.xx`就是你的服务器上的 IP 地址。

连接进去之后输入 yes 后按回车，接着输入你云服务器的密码，即可使用云服务器。

<img width="772" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024049-32963280-b992-11eb-8c05-db6df1f7fbfa.png">

注意！有小概率情况是，如果你选日本机房，可能被自动分配到被墙的IP。如何判别呢？打开 http://ping.chinaz.com 输入你的服务器IP测试。如果Ping不通，说明IP被墙了。立即删掉这台服务器，重新创建一个。

# V2Ray搭建

新的一键V2Ray脚本，经过笔者的测试，安装简单方便，自动关闭防火墙，自动安装BBR加速，因此推荐大家使用！


安装命令：

输入以下命令，回车执行：

```
bash <(curl -s -L https://git.io/v2ray-setup.sh)
```

显示一下信息代表安装成功（可直接用以下配置进行连接）(以下配置在链接时使用)：

```
---------- V2Ray 配置信息 -------------

 地址 (IP Address) = 141.*.*.*

 端口 (Port) = 8888

 用户ID (User ID / UUID) = 38b272ba-8a91-*-*-*

 额外ID (Alter Id) = 0

 传输协议 (Network) = tcp

 伪装类型 (header type) = none

---------- END -------------

V2Ray 客户端使用教程: https://git.io/v2ray-client

提示: 输入 v2ray url 可生成 vmess URL 链接 / 输入 v2ray qr 可生成二维码链接

---------- V2Ray vmess URL / V2RayNG v0.4.1+ / V2RayN v2.1+ / 仅适合部分客户端 -------------

vmess://ewoidiI6I*****g==

```


配置文件要注意(建议直接复制安装结果中 vmess://**** 地址，直接导入，避免自己填配置出错)：

```
Network(传输协议)： tcp
type(伪装类型)：none
不对的话连不上！！！
```


好了到这里我们就搭建成功了(^▽^)

相关命令：


```

v2ray info 查看 V2Ray 配置信息
v2ray config 修改 V2Ray 配置
v2ray link 生成 V2Ray 配置文件链接
v2ray infolink 生成 V2Ray 配置信息链接
v2ray qr 生成 V2Ray 配置二维码链接
v2ray ss 修改 Shadowsocks 配置
v2ray ssinfo 查看 Shadowsocks 配置信息
v2ray ssqr 生成 Shadowsocks 配置二维码链接
v2ray status 查看 V2Ray 运行状态
v2ray start 启动 V2Ray
v2ray stop 停止 V2Ray
v2ray restart 重启 V2Ray
v2ray log 查看 V2Ray 运行日志
v2ray update 更新 V2Ray
v2ray update.sh 更新 V2Ray 管理脚本
v2ray uninstall 卸载 V2Ray

```


vmess协议配置

查看配置文件(该配置在后面链接时使用)：

```
cat /etc/v2ray/config.json

```


# 客户端链接V2Ray

各平台的v2ray客户端地址：



## Windows v2ray客户端：
下载方式一：网盘(直接解压可用)

【v2rayN】：https://cloud.degoo.com/share/f-Vljc2ZjhmcPyHbi5Pw0A 或 https://github.com/xyz690/cloudimg/blob/main/data/v2rayN-3.29.zip

解压【【【点击v2rayN.exe启动】】】

## 下载方式二：GitHub

## 客户端：下载v2rayN.zip

【v2rayN.exe Github Releases】 https://github.com/2dust/v2rayN/releases/download/3.29/v2rayN.zip

内核：下载v2ray-windows-64.zip文件

【v2ray-windows-64.zip Github Releases】 https://github.com/v2fly/v2ray-core/releases/download/v4.31.0/v2ray-windows-64.zip

对v2ray-windows-64.zip 和 v2rayN进行解压，然后将 v2rayN 目录下所有文件复制到v2ray-windows-64解压后的目录，即两个下载好的文件需要在同一目录。

【【【点击v2rayN.exe启动】】】

注意电脑右下角 V 图标，双击图标，点右上角 服务器 ，添加[VMess]服务器。

(^▽^)(^▽^)(^▽^)(^▽^)(^▽^)(^▽^)

## 进行配置:

客户端的配置需要根据你的服务端进行相应的配置，因为你的服务端协议可能是vmess等。

如果你的服务端配置是协议vmess，则配置如下：

![image](https://user-images.githubusercontent.com/98797623/152635998-2ec4cd1d-4a4c-4a9b-aa2d-ac3eaff41ce2.png)

保存后，右键电脑右下角 V 图标

![image](https://user-images.githubusercontent.com/98797623/152636040-d490972e-b11b-4faf-b01b-d74697a9adb7.png)

Android v2ray客户端：
## 下载方式一：网盘(APK直接安装)

【APK】：https://cloud.degoo.com/share/msgcYbsWQVoz2EIbSXr5bw 或 https://github.com/xyz690/cloudimg/blob/main/data/v2rayNG_1.4.13_arm64-v8a.apk

## 下载方式二：GitHub
一般手机是arm架构，我就直接给出对应客户端了，其他架构需要你去网上找设备相应的CPU架构并进行选择下载：
【v2rayNG Github Releases】https://github.com/2dust/v2rayNG/releases/download/1.4.13/v2rayNG_1.4.13_arm64-v8a.apk

## 使用方法:

```
(1）打开 v2rayNG APP
(2）点击右上角 + 号
(3）选择 手动输入[Vmess]
(4）别名随意，地址(填服务器外网IP地址)，端口(你设置的V2Ray端口)，用户ID，额外ID:0，加密方式:auto，其他设置默认
(5）右上角 √ 保存
(6）右下角 V图标 点击启动.
(7）打开浏览器试试吧
```

## MacOS v2ray客户端:
https://github.com/Cenmrev/V2RayX/releases


## Linux内核 v2ray客户端：
Debian、Ubantu、CentOS等电脑桌面发行版（不能完全通用，可以尝试一下）
https://github.com/jiangxufeng/v2rayL/releases


## IOS v2ray客户端：
需要国外账号，推荐shadow（小火箭）rocket，quantumult（圈），kitsunebi


测试
打开浏览器，访问www.google.com，如下：

![image](https://user-images.githubusercontent.com/98797623/152636071-8edac5d4-b91b-484c-be3a-eb3481884877.png)

v2ray搭建教程到此结束，祝大家春风得意！

## 第六部分：v2ray提速之BBR

本文脚本对支持BBR加速的系统，自动安装BBR加速！

CentOS查看BBR是否运行，输入以下命令，回车执行：
```
lsmod | grep bbrCOPY
```

有返回则成功！


