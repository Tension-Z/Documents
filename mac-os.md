# Mac OS

## ShadowsocksX-NG-R {#shadowsocksx-ng-r}

### 软件信息

{% hint style="danger" %}
此客户端已经近乎停止更新。
{% endhint %}

`我们 为此客户端提供「主流支持」，Yeah~`

ShadowsocksX-NG-R 是目前在 macOS 上使用 SSR 协议的最佳选择。

由于 SSR 项目删库的影响，此客户端的开发者也将项目的主分支设置为了一个 `rm` 分支并近乎停止了开发，我们 将可能根据评估结果将此客户端转为「扩展支持」。

### 系统环境

`Mac OS High Sierra 10.13.4 Beta (17E139j)  
SSX-NG-R 1.4.3-R8(2)`

### 安装 SSX-NG-R

{% hint style="warning" %}
以下操作将可能需要使用终端
{% endhint %}

从[这里](https://github.com/qinyuhang/ShadowsocksX-NG-R/releases/download/1.4.3-R8-build3/ShadowsocksX-NG-R8.dmg)下载 SSX-NG-R。

在 Finder 中双击 SSX-NG-R 打开宗卷，然后用 Finder 打开「应用程序」目录。  


在 SSX-NG-R 的宗卷中，用鼠标将 SSX-NG-R 拖动到 Finder 的应用程序目录。

![&#x5B89;&#x88C5; SSX-NG-R](https://rixcloud-1255365801.file.myqcloud.com/image/ec6iv.png)

由于 SSX-NG-R 是未经 Apple 签名的应用程序，因此 macOS 可能会阻止运行此程序。

打开「系统偏好设置」-「安全性与隐私」，可以查看到你的 macOS 可能仅允许使用来自 App Store 或受信任开发者的应用程序。

![&#x5B89;&#x5168;&#x6027;&#x4E0E;&#x9690;&#x79C1;&#x8BBE;&#x7F6E;](https://rixcloud-1255365801.file.myqcloud.com/image/jfntg.png)

打开「终端」。

![&#x7EC8;&#x7AEF;](https://rixcloud-1255365801.file.myqcloud.com/image/qigzs.png)

在终端的窗口中输入如下指令，并按下回车键。

```text
sudo spctl --master-disable
```

由于申请了 sudo 权限，需要输入你当前账户的密码，在 Shell 中输入密码是不可见的，只需要输入密码后按下回车即可。

再次访问「安全性与隐私」页面，将可以看到你的 macOS 已经允许「任何来源」的应用程序运行。

![&#x4EFB;&#x4F55;&#x6765;&#x6E90;](https://rixcloud-1255365801.file.myqcloud.com/image/jgkvg.png)

### 配置软件

复制订阅地址（关于此部分内容请参考Windows[创建订阅](https://doc.biwcloud.com/windows#chuang-jian-ding-yue-lian-jie)）

![&#x590D;&#x5236;&#x8BA2;&#x9605;](.gitbook/assets/image%20%288%29.png)

打开 SSX-NG-R，打开后将会在状态栏上出现一个灰色的纸飞机图标。

![&#x7F16;&#x8F91;&#x8BA2;&#x9605;](.gitbook/assets/image%20%2814%29.png)

在新的「订阅设置」窗口中点击 `+` 号，然后将刚才复制的 订阅地址 粘贴到「订阅地址」一栏上。点击「OK」

![&#x6DFB;&#x52A0;&#x8BA2;&#x9605;](.gitbook/assets/image%20%2810%29.png)

再次点击 SSX-NG-R 的图标，如图所示勾选「打开时自动更新订阅」并点击「手动更新订阅」。

![&#x66F4;&#x65B0;&#x8BA2;&#x9605;](.gitbook/assets/image%20%2820%29.png)

如果一切顺利，将会收到通知消息提示订阅更新成功。

![&#x6210;&#x529F;&#x8BA2;&#x9605;](.gitbook/assets/image%20%2813%29.png)

在服务器分组中选择需要的接入点。  


![&#x9009;&#x62E9;&#x8282;&#x70B9;](.gitbook/assets/image%20%2819%29.png)

选择所需的代理模式，然后点击「打开 Shadowsocks」即可使用

### 为 Shell 设置代理

如果需要在终端中使用，则需要单独进行设置。

首先查看 SSX-NG-R 当前将本地代理工作在哪个端口。

在已经开启 SSX-NG-R 并启用系统代理时，打开「系统偏好设置」-「网络」，选择当前使用的网络设备，点击「高级」。

点击「代理」选项卡，其中的 HTTP / HTTPS / SOCKS 代理应当已经被勾选。我们需要查看他们的端口。

![&#x67E5;&#x770B;&#x4EE3;&#x7406;&#x7AEF;&#x53E3;](https://rixcloud-1255365801.file.myqcloud.com/image/5geaj.png)

在本例中，SSX-NG-R 的 HTTP/HTTPS 代理工作在 `1087` 端口，SOCKS 5 代理工作在 `1086` 端口。

打开终端，在 Shell 中键入如下指令：

```text
export https_proxy=http://127.0.0.1:1087;export http_proxy=http://127.0.0.1:1087;export all_proxy=socks5://127.0.0.1:1086
```

此时 Shell 已经设置为通过 SSX-NG-R 进行代理，可以通过以下指令来检测：

```text
curl ip.sb
```

查看 IP 地址是否为 我们的 接入点的出口 IP 地址。



