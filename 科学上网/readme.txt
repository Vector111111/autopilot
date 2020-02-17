公布者：bit wlz 2020.2.17

前言：
本部分主要介绍我科学上网的一点总结，水平有限，如有错误望批评指正。希望大家掌握科学上网的方法并且将其用在合法的领域。在此感谢前辈们的各种博客以及github分享。
科学上网有很多种方式，可以用vpn节点+梯子，也可以用ss/ssr节点+梯子,我用的是ssr。
首先，需要购买节点，推荐aity.ml，网速还算可以，主要是便宜。链接如下：
https://aity.ml/
其次，需要下载科学上网的梯子，windows和ubuntu的梯子是不同的，根据所用系统选择下载。
如果不想花钱，可以利用浏览器插件的方式，比如setup vpn，缺点是网速不好，当然也可以升级到VIP用户，但是比较贵了。
参考链接：
https://github.com/qingshuisiyuan/electron-ssr-backup/releases
https://alanlee.fun/2018/05/18/ubuntu-ssr/
https://blog.csdn.net/wf19930209/article/details/78725745 

windows10：
1.下载了ShadowsocksR-win-4.9.0之后，点击4.0.exe打开，在系统桌面的右下角有一个白色的纸飞机，看不到的话就在^里面隐藏着。
2.鼠标放在纸飞机上，右键-服务器订阅-ssr服务器订阅设置-add-把买的节点的订阅地址复制粘贴到“网址”这里-确定。
3.服务器订阅-更新服务器订阅（不通过代理）。
4.服务器-月结-选择想用的节点。
5.系统代理模式-全局模式（PAC也可以，省一些流量，但是可能有的网址打不开）。
6.系统代理规则-绕过局域网和大陆。
7.正常的话等一会有更新成功的提示，按道理就可以打开google浏览器上网了，可以登Youtube试一下。
注意：
1）其他地方可以不用修改，如果连接了宽带，建议改成英文名。
2）用google浏览器的话，记得把自己额外装的插件禁掉，比如下面讲到的setup vpn。
3）用搜狐浏览器的话，记得首选项-代理-使用系统代理设置（找不到代理在那里就用搜索）。

ubuntu18.04：
1.下载了electron-ssr-0.2.6之后，鼠标左键双击electron-ssr，可以看到一个小飞机在桌面的右上角。（有时候双击没效果，那就关机重启多次尝试）
2.左键点击一下小飞机，配置-选项设置-订阅管理-添加-ctrl+v的方式粘贴（鼠标粘贴不好使）-enter。
3.左键点击一下左边的小方框选中该订阅地址-更新-显示已更新0个节点
4.通用设置-pac端口:2333 本地监听端口：1080 http端口:xxxxx(买的节点自带，我的是5位) 局域网共享与http代理勾选，开机自启动是否勾选看你的心情了。
5.服务器-月结-选择想用的节点
6.系统代理模式-全局模式（PAC也可以，省一些流量，但是可能有的网址打不开）
7.ubuntu桌面-设置-网络-网络代理-自动，这样，基本的配置就ok了。
注意：
1）想要终端翻墙还要继续操作如下：
终端打开，输入：
sudo gedit /etc/proxychains.conf
注释掉最下面自带的sock4等，改为以下两行：
socks5  127.0.0.1 1080
https   127.0.0.1 8080
保存退出
sudo apt install proxychains
sudo find /usr/ -name libproxychains.so.3
正常情况下返回：
/usr/lib/x86_64-linux-gnu/libproxychains.so.3
终端继续输入：
sudo gedit /usr/bin/proxychains
完成一步替换：
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libproxychains.so.3
保存退出
测试：
proxychains curl www.google.com
如果不报错就ok了，每次想用终端科学上网的时候，除了打开ssr（小飞机开启应用），终端命令行前加一个proxychains，比如：
proxychains pip install xxx
终端用proxychains的好处就是，外网下东西能达到2M/S，相当快。
2）用google浏览器的话，记得把自己额外装的插件禁掉，比如下面讲到的setup vpn。
3）用搜狐浏览器的话，记得首选项-代理-使用系统代理设置（找不到代理在那里就用搜索）。

浏览器插件setup vpn：
google浏览器：
1）下载一个蓝灯，用每月提供的免费流量作为梯子
2）google商城找一个setup vpn的东西，加载到google插件里面
3）浏览器界面，右上角云朵处点击一下，注册之后，就可以免费选服务器使用了
火狐浏览器：
附加组件-搜索setup就能看到，全程不需要fq，用法和google浏览器一样。



