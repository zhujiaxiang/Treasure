#Treasure
##Intro
遇到的有趣的题以及总结一些iOS开发的实用经验

##趣题

1.在同一侧的房号为1、2、3、4的四间房里，分别住着来自韩国、法国、英国和德国的四位专家。有一位记者前来采访他们
韩国人说：“我的房号大于德国人，且我不会说外语，也无法和邻居交流”；
法国人说：“我会说德语，但我却无法和我的邻居交流”；
英国人说：“我会说韩语，但我只可以和我的一个邻居交流”；
德国人说：“我会说我们这四个国家的语言。” 
那么，按照房号从小往大排，房间里住的人的国籍依次是(    )。

A.英国    德国    韩国    法国

B.法国    英国    德国    韩国

C.德国    英国    法国    韩国

D.德国    英国    韩国    法国

2.A、B两人玩猜字游戏，游戏规则如下：
A选定一个 [1,100]之间的数字背对B写在纸上，然后让B开始猜；如果B猜的偏小，A会提示B这次猜的偏小；一旦B某次猜的偏大，A就不再提示，此次之后B猜的偏小A也不会再提示，只回答猜对与否。请问：B至少要猜()次才能保证猜对？

A.12

B.13

C.14

D.15

3.一群人开舞会，每人头上都戴着一顶帽子。帽子只有黑白两种，黑的至少有一顶。每个人都能看到其它人帽子的颜色，却看不到自己的。主持人先让大家看看别人头上戴的是什幺帽子，然 后关灯，如果有人认为自己戴的是黑帽子，就打自己一个耳光。第一次关灯，没有声音。于是再开灯，大家再看一遍，关灯时仍然鸦雀无声。一直到第三次关灯，才 有劈劈啪啪打耳光的声音响起。问有多少人戴着黑帽子？

4.A、B两人玩猜字游戏，游戏规则如下：
A选定一个 [1,100]之间的数字背对B写在纸上，然后让B开始猜；如果B猜的偏小，A会提示B这次猜的偏小；一旦B某次猜的偏大，A就不再提示，此次之后B猜的偏小A也不会再提示，只回答猜对与否。请问：B至少要猜()次才能保证猜对？

5.对一批编号为1～100，全部开关朝上(开)的灯进行以下操作：凡是1的倍数反方向拨一次开关；2的倍数反方向又拨一次开关；3的倍数反方向又拨一次开关……100的倍数反方向又拨一次开关 ,问：最后为关熄状态的灯有几个。

6.32!的计算结果，尾数总共有几个零？

7.选一个最合适的字母填入括号中使之呈现一定规律：BDF CFI EI （）

8.a和b两个人每天都会在7点-8点之间到同一个车站乘坐公交车，a坐101路公交车，每5分钟一班【7:00,7:05……】，b坐102路公交车，每10分钟一班【7:03,7:13…】，问a和b碰面的概率是多少？
##实用经验
###消息同步问题
1.解决同步消息乱序（原因：时间戳精确到秒级，同一秒内的消息可能乱序）解决方案：不止按时间戳，综合考虑入库时间

2.解决同步消息时间过长， webservice改异步 
###reloadData-----在做filePreview时候遇到的线程问题
1.有如下情景 我下载一个文档，在block中下载完回调reloadData，这种时候就会出现崩溃等一系列奇怪的状况，不要在子线程进行ui操作！！ 

究其原因援引网上的结论：在子线程中是不能进行UI 更新的，而可以更新的结果只是一个幻像：因为子线程代码执行完毕了，又自动进入到了主线程，执行了子线程中的UI更新的函数栈，这中间的时间非常的短，就让大家误以为分线程可以更新UI。如果子线程一直在运行，则子线程中的UI更新的函数栈 主线程无法获知，即无法更新。
如有误请指教！

###一个推送与后台的问题（待解决）

手机登陆qq号A
电脑登陆qq号B

首先打开手机qq，登陆A，按home键使其进入后台。
然后用B给A发多条消息，接着手机收到了推送。
这时，把手机wifi和移动数据都关掉（不进入飞行模式，只是断网），再打开qq。
刚刚推送来的消息都接收到了。怎么做到的？

###专利检索三步走

1.工具

Rainpat（可批量导出）

Soopat

2.关键字：X、Y、Z

检索式：

TI=(X OR Y OR Z)

(TI,AB=(X OR Y OR Z)) NOT (TI=(X OR Y OR Z))

备注：TI=标题  AB=摘要  CLM=权利要求

3.分析检索结果
