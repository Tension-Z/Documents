# 路由器设置教程

## Koolshare Modified ROM {#koolshare-modified-rom}

{% hint style="danger" %}
收到大量报告，称此客户端存在严重的稳定性与可靠性问题。
{% endhint %}

### 软件信息

Koolshare 推出的改版固件（多为 Merlin 改版，也存在官方固件改版）中的软件中心提供了 SSR 客户端，使得路由器上可以运行 SSR 客户端，提供网关级别的代理，实现整个路由器下的设备无需配置就可以使用 rixCloud 网络。

但是，由于大部分家用路由器的 CPU 都是 MIPS 或者 ARMv7 架构，同时主频较低，运算性能低下（NAT 大部分有硬件加速因此并不消耗 CPU 性能），导致使用 SSR 的速度可能很慢（平均为不到 50Mbps）。

同时，由于 Koolshare 的更新较多，几乎所有版本都未经代码审计和测试，因此某些版本可能存在严重 Bug 影响使用，导致一天之内更新多次版本，被戏称为 Nightly（每夜更新版）的进阶——Hourly（每小时更新版）

### 测试环境

{% hint style="warning" %}
此软件更新较为频繁且有多个版本，文档中的部分内容可能和实际存在差异。
{% endhint %}

{% hint style="info" %}
我们仅在特定平台和版本上进行过测试，并以此撰写文档
{% endhint %}

`ASUS GT-AC5300  
Koolshare Modified ROM 3.0.0.4.382_15984_koolshare  
KoolSS 1.1.6(Merlin)`

### 注意事项

由于使用 Koolshare Modified ROM（改版固件）的太多是普通家用路由器，其使用的 CPU 大都为 MIPS 或 ARMv7 架构，其性能可能不足，因此使用 KoolSS 可能无法达到较高速率。

目前经过 rixCloud 和 Koolshare 的测试，以下两款路由器使用 Koolshare Modified ROM 的 KoolSS 后可基本达到 200Mbps 的速率：

> ASUS GT-AC5300
>
> ASUS RT-AC86U

如果想要在路由器上达到较高 SS 连接速率，请考虑购买以上两款路由器或购买软路由使用 LEDE

以下是各常见路由型号使用 KoolSS 的大致连接速率：

我们会根据收集到的数据不断更新此表格，但用户提供的数据本身未经验证，仅供参考。你也可以提供你的测试数据，以便协助我们完善此内容。

| 型号 | 品牌 | 大致连接速率 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R6300v2 | NETGEAR | 60Mbps |
| R6400 | NETGEAR | 30Mbps |
| R6900 | NETGEAR | 60Mbps |
| R7000 | NETGEAR | 80Mbps |
| R8000 | NETGEAR | 未经测试 |
| R8500 | NETGEAR | 110Mbps |
| RT-N66U | ASUS | 未经测试 |
| RT-AC56U | ASUS | 20Mbps |
| RT-AC66U | ASUS | 30Mbps |
| RT-AC68U | ASUS | 60Mbps |
| RT-AC87U | ASUS | 70Mbps |
| RT-AC88U | ASUS | 100Mbps |
| RT-AC86U | ASUS | 200Mbps |
| RT-AC1900P | ASUS | 70Mbps |
| RT-AC3100 | ASUS | 未经测试 |
| RT-AC3200 | ASUS | 未经测试 |
| RT-AC66U-B1 | ASUS | 60Mbps |
| RT-AC5300 | ASUS | 120Mbps |
| GT-AC5300 | 玩家国度 | 250Mbps |
| EA6200 | Linksys | 未经测试 |
| EA6400 | Linksys | 未经测试 |
| EA6700 | Linksys | 未经测试 |
| EA6500v2 | Linksys | 未经测试 |
| EA6900 | Linksys | 未经测试 |
| WRT1900ACS | Linksys | 120Mbps |

（数据提供方表明此数据是通过何种渠道收集的）

{% hint style="info" %}
以上测试仅供参考，不同服务配置的情况下数值可能存在差异
{% endhint %}

### 从软件中心安装 KoolSS

{% hint style="danger" %}
安装前可能有额外操作
{% endhint %}

Koolshare Modified ROM 在使用软件中心前需要先清空并格式化 JFFS2 分区，由于此不属于我们文档应当包含的一部分，因此阁下需要自行前往 Koolshare 社区了解不同机型的不同清除方法。

通过浏览器访问 Koolshare Modified ROM（改版固件） 管理页面。

{% hint style="info" %}
由于 Koolshare Modified ROM 的页面存在一些兼容性问题，建议使用 Google Chrome 浏览器
{% endhint %}

在管理页面底部点击「软件中心」，然后点击「未安装」选项卡，然后点击「科学上网」插件来安装。



页面会提示正在安装。

![&#x6B63;&#x5728;&#x5B89;&#x88C5;&#x4E2D;](https://rixcloud-1255365801.file.myqcloud.com/image/dx00y.png)

如果安装完成，页面会自动跳转，并可以在「已安装」选项卡下看到此插件。

![&#x5B89;&#x88C5;&#x5B8C;&#x6210;](https://rixcloud-1255365801.file.myqcloud.com/image/spv3m.png)

  
复制订阅地址（关于如何创建订阅[参考教程](https://doc.biwcloud.com/windows#chuang-jian-ding-yue-lian-jie)）

![&#x590D;&#x5236;&#x8BA2;&#x9605;](.gitbook/assets/image%20%2830%29.png)

### 配置 KoolSS

点击「已安装」选项卡中的「科学上网」插件进入插件管理页面。

如果是第一次使用此插件，则可能弹出此会话框：

![&#x9996;&#x6B21;&#x4F7F;&#x7528;&#x63D0;&#x793A;](https://rixcloud-1255365801.file.myqcloud.com/image/xw3x7.png)

点击「订阅节点」按钮进入更新管理页面。

如果没有弹出此会话框，则手动打开 KoolSS 开关并点击「更新管理」选项卡。

![&#x66F4;&#x65B0;&#x7BA1;&#x7406;&#x9875;&#x9762;](https://rixcloud-1255365801.file.myqcloud.com/image/4t8kw.png)

进入「更新管理」页面后，滑动页面到下方的「SSR 订阅设置」区域。

![&#x914D;&#x7F6E;ssr&#x8BA2;&#x9605;](.gitbook/assets/image%20%2818%29.png)

在「订阅地址管理」中粘贴我们之前复制的 rixCloud API URI，然后进行如下设定

> 将「订阅节点模式设定」设置为「游戏模式」
>
> 将「订阅节点混淆参数设定」设置为「使用订阅设定」
>
> 将「下载订阅时走 SS 网络」设置为「不走 SS」
>
> 开启「订阅计划任务」，并选择一个你可能不会使用网络的时间。

设置完成后，点击「保存并订阅」按钮。页面会打开一个新的提示框并出现类似下图中的内容：

![](.gitbook/assets/image%20%2821%29.png)

订阅完成后，页面会自动跳转到主页面，此时 KoolSS 的开关可能将会再次出于关闭状态，点击开关来打开它。

![&#x6253;&#x5F00;KoolSS&#x5F00;&#x5173;](.gitbook/assets/image.png)

### 附加设置

为了使我们的使用更加舒适，我们需要进行一些附加设置。

点击「更新管理」选项卡，将「规则定时更新任务」设置为「开启」，然后选择一个你可能不会使用网络的时间段。并将所有规则的更新全部勾选，然后点击「保存设置」。

![&#x5F00;&#x542F;&#x89C4;&#x5219;&#x66F4;&#x65B0;](https://rixcloud-1255365801.file.myqcloud.com/image/7pfas.png)

页面将会自动跳转，完成后应当再次返回此页面，然后点击「立即更新」。以确保 KoolSS 已经获取到最新的规则。

点击「DNS 设定」选项卡，然后进行以下设定：

> 将选择国内 DNS 设置为运营商 DNS，如果你的运营商 DNS 存在劫持，则可以使用 `119.29.29.29` 或自定义设置为 `119.28.28.28`
>
> 将「选择国外 DNS」设置为 `ss-tunnel`，然后设置你喜欢的国外公共 DNS 服务提供商

![DNS &#x8BBE;&#x5B9A;](https://rixcloud-1255365801.file.myqcloud.com/image/1z7ik.png)

### 开启 KoolSS

完成附加设置后，点击「账号设置」选项卡，选择需要的接入点，然后点击底部的「提交」按钮。KoolSS 将会启动。

一段时间后，页面将会自动刷新并返回到账号设置页面，此时 KoolSS 会自动检测状态，如果国内国外均为 OK 状态即可正常使用。

![KoolSS &#x5DF2;&#x7ECF;&#x6B63;&#x5E38;&#x8FD0;&#x884C;](https://rixcloud-1255365801.file.myqcloud.com/image/wxhxb.png)

{% hint style="danger" %}
某些情况下，显示连接错误并非未能连接上，而是可能的测试失败，请实际使用浏览器打开网页测试。
{% endhint %}

## Koolshare LEDE {#koolshare-lede}

{% hint style="warning" %}
我们仅在特定平台和版本上进行过测试，并以此撰写文档
{% endhint %}

{% hint style="info" %}
此软件更新较为频繁且有多个版本，文档中的部分内容可能和实际存在差异。
{% endhint %}

### 测试环境

`Windows Server 2016 Datacenter  
Hyper-V Hypervisor  
Koolshare LEDE x64 v2.8  
KoolSS (Software center) 1.9.7`

### 安装 KoolSS

通过浏览器访问 LEDE 管理页面。

{% hint style="success" %}
由于 Koolshare LEDE 的页面存在一些兼容性问题，建议使用 Google Chrome 浏览器
{% endhint %}

点击左侧侧边栏的「酷软」。

![&#x6253;&#x5F00;&#x8F6F;&#x4EF6;&#x4E2D;&#x5FC3;](https://rixcloud-1255365801.file.myqcloud.com/image/3t9vc.png)

在软件中心的「未安装」列表中找到「科学上网插件」，如下图：

![](https://rixcloud-1255365801.file.myqcloud.com/image/ll4ht.png)

> 由于我们已经安装过此插件，因此显示为「更新」

点击插件的「安装」按钮安装，页面将会在安装完成够自动跳转。

### 复制订阅

复制订阅地址（关于此部分内容请参考Windows[创建订阅](https://doc.biwcloud.com/windows#chuang-jian-ding-yue-lian-jie)）

​![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LEQO1An5RNYdVixPhzO%2F-LETQk_R9ZHl25InppVO%2F-LETTw6tdJ-6wduxnhVW%2Fimage.png?alt=media&token=5f944e0f-f5c4-4191-906a-820dc8163b7b)  


### 配置 KoolSS

打开软件中心，然后从「已安装」的插件列表中打开 KoolSS。

如果 KoolSS 出于关闭状态，则点击开关打开它。

点击「节点管理」选项卡， 然后点击二级的「节点管理」选项卡。

![&#x8282;&#x70B9;&#x7BA1;&#x7406;](https://rixcloud-1255365801.file.myqcloud.com/image/olods.png)

在下方的 SSR 节点订阅中填写一些必要信息。

将我们刚才复制的 订阅地址 粘贴到「SSR 节点订阅地址」中；将「订阅节点模式设定」选择为「游戏模式」；然后将订阅节点混淆参数设定设置为「使用订阅设定」。

![&#x8BA2;&#x9605;&#x8BBE;&#x7F6E;](.gitbook/assets/image%20%2828%29.png)

配置完成后点击「保存订阅设置」，页面将会自动跳转。

完成后，再次返回此页面，并点击「手动更新订阅」。页面将会自动跳转并刷出类似下图的日志信息：

![&#x66F4;&#x65B0;&#x8BA2;&#x9605;](https://rixcloud-1255365801.file.myqcloud.com/image/k7zql.png)

此时 rixCloud 接入点信息已经添加到你的 KoolSS 中了，现在让我们来做一些附加设置以便更好地使用。

### KoolSS 附加设置

点击「规则管理」选项卡，将下方的 KoolSS 规则自动更新设置为「开启」，将时间设置为你可能不会使用网络的时间，然后勾选所有规则复选框。

![&#x8BBE;&#x7F6E;&#x89C4;&#x5219;&#x7BA1;&#x7406;](https://rixcloud-1255365801.file.myqcloud.com/image/u603p.png)

> 你可以只勾选图中红框框选的「chnroute」和「chn\_list」，但建议全部勾选。

点击「DNS 设定」选项卡，进行如下设定：

> 将「DNS 解析偏好」设置为「国外优先」

> 将「选择国内 DNS」设置为「运营商 DNS」或「自定义」，然后输入 `119.28.28.28`

> 将「选择国外 DNS」设置为「ss-tunnel」，然后选择你喜欢的国外公共 DNS 服务提供商

> 将「SS 服务器地址解析」设置为「nslookup 方式」，然后输入 `119.28.28.28`

> 勾选「chromecast 支持」以劫持局域网内设备的 DNS 解析，避免受到 DNS 缓存污染

![DNS &#x8BBE;&#x5B9A;](https://rixcloud-1255365801.file.myqcloud.com/image/jvmlx.png)

### 开启 KoolSS

返回到 KoolSS 主页面「账号设置」，选择需要使用的接入点，然后点击下方的「提交」按钮。

![&#x9009;&#x62E9;&#x63A5;&#x5165;&#x70B9;](https://rixcloud-1255365801.file.myqcloud.com/image/c4rjl.png)

页面会自动跳转并刷出类似下图的日志信息：

![KoolSS &#x542F;&#x52A8;&#x65E5;&#x5FD7;](https://rixcloud-1255365801.file.myqcloud.com/image/13gcg.png)

完成后，页面会自动跳转回主页面，并启动连接测试，如果如下图显示则连接成功，所有连接到此路由器的设备都可以通过我们网络连接到国际互联网。

![&#x8FDE;&#x63A5;&#x68C0;&#x67E5;](https://rixcloud-1255365801.file.myqcloud.com/image/soig9.png)

{% hint style="info" %}
某些情况下，显示连接错误并非未能连接上，而是可能的测试失败，请实际使用浏览器打开网页测试。
{% endhint %}

