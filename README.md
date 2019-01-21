# Vultr-Shadowsocks
# Vultr
`搭建背景`
> 因为自己是程序员出身，加上身边的朋友有一些是做设计工作的，对FQ有一定的需求，所以呢我就开始填坑啦，成功之后分享给有需要的朋友看看，自己也可以尝试搭建一个代理服务器。
**需要注意的一点是：我们一定要自己注册帐号，千万不要找人代购，因为代购存在很大的风险，VPS可能被植入后门程序，十分危险，而且被主机商发现会被封号处理。**

`具体步骤`
* 注册[Vultr](https://buy.shangyufeidi.com/vultr/go/?f=gm1)账户还是很简单的，基本上3-5分钟就可以搞定。下面就给大家详细讲解[Vultr](https://buy.shangyufeidi.com/vultr/go/)的购买流程。
1.注册`Vultr`账号
打开[Vultr官网](https://buy.shangyufeidi.com/vultr/go/?f=gm2)，输入邮箱和密码，点击“Create Account” 即可。
![](https://upload-images.jianshu.io/upload_images/1130813-8f1e9f416af73f70.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2.账户激活
新用户注册完了，登录之后会跳转到充值界面，如下图所示，我们可以选择不同的充值方式，这里推荐**支付宝**充值，因为方便！最低的充值金额为`$10`，`$10`买`$2.5`可以用四个月，没什么限制，完全够用了。
![](https://upload-images.jianshu.io/upload_images/1130813-68bb9da3c50d1567.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](https://upload-images.jianshu.io/upload_images/1130813-084bf28f9a2ef522.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3.创建**VPS**服务器实例
点击左侧菜单的`Servers`，进入创建VPS界面，或者在任意页面直接点击右侧+号，进入创建VPS界面。可见下面两张图的提示。
![](https://upload-images.jianshu.io/upload_images/1130813-a4e23f8a66c6f637.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3.1选择节点位置
目前我们首选`日本`直连机房，其次是`美国西海岸`的机房（加州和洛杉矶）。
因为东京节点离我们物理距离较近，而且是中国直连线路，整体效果优秀。Ping值也好些，ping值大概在80~120ms左右波动。
![](https://upload-images.jianshu.io/upload_images/1130813-a20c3f93bfed7431.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3.2选择操作系统
Vultr基本覆盖了几乎所有主流操作系统，包括Linux、Windows(需支付正版费用，十分贵)。同时还提供了自定义ISO安装，可谓业界良心。但正常Windows镜像无法在Vultr安装，这点需要注意。我们这里选择`Debian`。
![](https://upload-images.jianshu.io/upload_images/1130813-14a23535095d1e48.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3.3选择套餐
根据CPU核数、内存、流量的不同，我们可以选择多个方案，这些都根据需求的用途决定的，后期我们也可以进行项目方案的升级。这里我们选择`$5`的玩玩。
![](https://upload-images.jianshu.io/upload_images/1130813-19a2e9fa6cd6994a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3.4其他选项
有IPv6，自动备份，DDoS防护，机器标签等，大家可以按需要选择。
![](https://upload-images.jianshu.io/upload_images/1130813-616684f107f72ed6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3.5 Deploy Now
点击“Deploy Now” 进行安装 VPS服务器，通常一两分钟就能完成整个VPS服务器的创建，请耐心等待。
![](https://upload-images.jianshu.io/upload_images/1130813-47a969f48fb2e321.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4. 查看服务器信息
安装好后可以进入信息面板，点击Server Details。如果服务器显示Installing状态，则代表安装中，请等待一下，如看到Runing就可以使用。
![](https://upload-images.jianshu.io/upload_images/1130813-b53345fb8e296de4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**可以看到有 IP，用户名root，密码(点击查看按钮或复制按钮)等信息，恭喜你，VPS就已经购买成功了。**
![](https://upload-images.jianshu.io/upload_images/1130813-000c0f848c96a63f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 科学上网搭建
``我们打开终端（windows 可以使用 SSH 工具 度娘一下就好）``
> 在终端里输入代码：ssh root@207.246.77.136
> root： 是刚建立的服务器的用户名，上一张最后让大家记录下来的
> 207.246.77.136：也是上一张让大家记录的IP地址

![](https://upload-images.jianshu.io/upload_images/1130813-a05d81eed5700aa7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
出现这个提示的时候输入`yes`，然后就会提示输入密码。
![](https://upload-images.jianshu.io/upload_images/1130813-731b117f80183872.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在这个页面把刚才保存的密码粘贴过来（不会有显示，粘贴过来就行）然后敲一下回车键
![](https://upload-images.jianshu.io/upload_images/1130813-e0fb2631a4f6215a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
当终端出现这个提示的时候，说明已经连接上了我们的服务器。然后我们就可以开始进行下一步了。
一次输入如下三条语句（从冒号后边开始，输入一条敲一次回车）
* 1) :wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh
* 2):chmod +x shadowsocks-libev-debian.sh
* 3):./shadowsocks-libev-debian.sh 2>&1 | tee shadowsocks-libev-debian.log
最后一条输入完之后会出现如下界面。
![](https://upload-images.jianshu.io/upload_images/1130813-321cc36b0a4346b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在光标处设置一个 SS `密码`，然后按回车键。
![](https://upload-images.jianshu.io/upload_images/1130813-bd82685518432a0d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后是设置 SS `端口号`， 再按回车键。
![](https://upload-images.jianshu.io/upload_images/1130813-05bb01693814b1dd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这一项是设置加密方式**注意：这里最好选择aes-256-cfb 亲测windows，mac，iPhone，Android都有效**，输入数字7就好（`aes-256-cfb`）加密方式，输入完之后按两次回车键开始自动配置安装，此时等待就好。配置安装结束后，终端会出现你的配置信息，如下图。
![](https://upload-images.jianshu.io/upload_images/1130813-3eb6aa5b486715de.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
保存以上`ip，端口，密码，加密方式`等信息。
> 最后去下载对应平台的工具就好啦~


















