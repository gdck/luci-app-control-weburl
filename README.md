# luci-app-control-weburl
魔改版luci-app-control-weburl，和原版相比可以多种控制模式：关键字过滤、MAC黑名单

源文地址：https://www.right.com.cn/forum/thread-4052342-1-5.html

魔改版luci-app-control-weburl，和原版相比可以多种控制模式：关键字过滤、MAC黑名单、时间控制
说是魔改，其实相当于重做，shell脚本几乎完全重写了，但为了尊重前辈的辛苦付出，依然保留原版的名称、版权信息。毕竟前辈走出的路，可以让我们更快到达目的地。
原版来自于KS一位前辈高人做的一组控制组件，但是仅仅可以关键字过滤并且没有星期设置（组件中另外还有“访问控制”、”时间控制“）。
经过魔改，可以关键字过滤、MAC黑名单、时间控制。另外随手添加了ip6支持。
如果填了url关键字，则是关键字过滤。
如果填了MAC，url关键字留空，则是纯MAC黑名单。
如果填了MAC又留空url关键字又设定了时间或星期，则是MAC时间控制模式。
一个插件集合了url关键字过滤、访问控制、时间控制3个部件的功能。另外iptables命令经过优化，不全使用时间、星期、url的话可以更加减轻cpu负担。
需要说明的是关键字过滤聊胜于无，并不是十分理想，只能说部分有效。

另外还有个问题，原版的shell脚本稍微弱智，不论你添加了几条规则（即使一条都没有），它也要无脑循环读取200次，耗时耗力。我这个有几条就读取几次。

最新版：会在防火墙自定义规则添加一条命令，防止防火墙重启时规则丢失。并且更加简化了命令。
闲得无聊，给加上了端口控制，省得再去自定义防火墙里面设了！这玩意被我玩成了过滤军刀。 

本帖隐藏的内容
 luci-app-control-weburl_1.5-20200923_all.zip (5.48 KB, 下载次数: 10)
 luci-app-control-weburl.zip (7.19 KB, 下载次数: 10)




这是另一个软件重启计划（计划任务的加强luci）：
