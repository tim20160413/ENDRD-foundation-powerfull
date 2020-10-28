# User-Agent
User-Agent，简称UA，又成用户代理，当用户通过浏览器向web服务器发送请求时，向服务器提供的浏览器及版本、操作系统及版本、浏览器内核等信息，web服务器通过解析UA获取当前浏览器所支持的特性来返回适合用户体验的代码信息（代码包括了排版信息+渲染信息，不同浏览器有不同的排版引擎和JavaScript引擎）。  

## 浏览下UA信息（参考[2]）
```
PC：
Chrome浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.186 Safari/537.36
Safari浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0.3 Safari/604.5.6
Firefox浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10.13; rv:58.0) Gecko/20100101 Firefox/58.0
QQ浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.101 Safari/537.36 QQBrowser/4.3.4986.400
Edge浏览器：
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/42.0.2311.135 Safari/537.36 Edge/13.10586
IE11：
Mozilla/5.0 (Windows NT 6.3; Win64, x64; Trident/7.0; rv:11.0) like Gecko
IE10：
Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; Win64; x64; Trident/6.0)

Mobile：
Safari浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0 Mobile/15D100 Safari/604.1
Chrome浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.1.34 (KHTML, like Gecko) CriOS/64.0.3282.112 Mobile/15D100 Safari/604.1
QQ内置浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 QQ/7.5.0.407 V1_IPH_SQ_7.5.0_1_APP_A Pixel/750 Core/UIWebView Device/Apple(iPhone 7) NetType/WIFI QBWebViewType/1
QQ浏览器：
Mozilla/5.0 (iPhone 91; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0 MQQBrowser/8.0.2 Mobile/15D100 Safari/8536.25 MttCustomUA/2 QBWebViewType/1 WKType/1
UC浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X; zh-CN) AppleWebKit/537.51.1 (KHTML, like Gecko) Mobile/15D100 UCBrowser/11.8.8.1060 Mobile AliApp(TUnionSDK/0.1.20.2)
WeChat内置浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 MicroMessenger/6.6.3 NetType/WIFI Language/zh_CN
Baidu浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11. Mobile/15D100 Safari/600.1.4 baidubrowser/4.13.0.16 (Baidu; P2 11.2.6)
Sougou浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 SogouMobileBrowser/5.11.10
 Weibo内置浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 Weibo (iPhone9,1__weibo__8.2.0__iphone__os11.2.6)
```

## 带着问题学习：
问题一：为什么所有的浏览器的UA都是Mozilla开头？  
问题二：UA由什么格式组成？  
问题三：UA有哪些应用？  

## 问题一：为什么所有的浏览器的UA都是Mozilla开头？
Mozilla渊源是一个很有意思的故事（内容引用[1]，参考 [4]）  
浏览器历史发展：  
Nexus（1990）-> Mosaic(1993) -> Netscape(Mozilla 1994) -> IE(1995)  -> Firefox(2002) -> Safari(2003)  -> Chrome(2008)   

* 1989年，蒂姆·伯纳斯-李（Tim Berners-Lee）发明了万维网（World Wide Web，简称3W），1990创建了世界上第一个浏览器WorldWideWeb，后改为Nexus，世界第一条链接http://info.cern.ch/ 于1991年8月6日上网（放入浏览器体验下它的神奇）；
* Nexus仅仅支持文本，1993年Mosaic浏览器出现了，它不仅支持文本还支持图片，让网页焕发色彩；此时对于web服务开发者来说不知道是哪个浏览器过来的请求，不知道发送文本还是发送文本+图片，此时Mosaic 提出向服务器请求时表明自己的身份，这就是UserAgent的由来，Mosaic的UserAgent为：NCSA_Mosaic/2.0 (Windows 3.1)
NCSA_Mosaic代表自己是什么浏览器，2.0代表版本号，Windows 3.1表示自己可以在什么系统下运行
* 1994年，Mozilla登场了，话说大名鼎鼎的网景公司，当时扮演了挑战Mosaic地位的角色，要“吃掉”Mosaic，Mozilla由“Mosaic Killa”（Killa是俚语中Killer的拼法）变化而来，并且是怪兽Godzilla（哥斯拉）的谐音，即“Godzilla eat the Mosaic！”，NetScape当时支持了html框架，让页面布局更加美观；为了表明自己的身份，网景将User-Agent 写为：Mozilla/1.0 (Win3.1)；
* 1995年IE也面世，IE（Internet Explore）简称探索者，微软由于操作系统的优势，IE浏览器也是迅速占领市场，IE同样面临一个问题，开发者对于html框架只认识Mozilla身份，贱贱的IE带起了装扮之风，User-Agent 改为：Mozilla/1.22 (compatible; MSIE 2.0; Windows 95)  告诉开发者我是Mozilla支持html框架，同时告诉大家我是 MSIE（Microsoft IE 2.0版本）；
* 2002年，Mozilla再次登场，曾经的Mozilla大神，使用排版引擎Gecko（壁虎），发明了Firefox火狐浏览器；UserAgent为：Mozilla/5.0 (Windows; U; Windows NT 5.1; sv-SE; rv:1.7.5) Gecko/20041108 Firefox/1.0，其中Gecko为排版引擎，Firefox/1.0为火狐浏览器1.0版本；
* 小插曲，在IE和FireFox互相竞争的时候，一款基于Linux的浏览器诞生，Konqueror浏览器（Conqueror的变体，征服者），Konqueror使用了KHTML排版引擎，提供更优质的页面，但是Gecko排版引擎已经被开发者接受，怎么办！继续学习微软装扮身份，于是User-Agent为：Mozilla/5.0 (compatible; Konqueror/3.2; FreeBSD) (KHTML, like Gecko)
* 于是后面的登场好像都顺理成章了，2003年，safari浏览器诞生，苹果公司使用了WebKit内核，包括了排版引擎和JavaScript引擎，其中排版引擎使用了KHTML，并进行了改进；User-Agent为
Mozilla/5.0 (Macintosh; U; PPC Mac OS X; de-de) AppleWebKit/85.7 (KHTML, like Gecko) Safari/85.5。
* 谷歌使用了苹果的开源Webkit引擎，2008年，chrome诞生，终于出现了程序员的最爱，
Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US) AppleWebKit/525.13 (KHTML, like Gecko) Chrome/0.2.149.27 Safari/525.13

回过头来看，Mozilla是排版引擎的引路人，编制大家为正规军；而内核的出现更规范了User-Agent；  

## 问题2： UA由什么格式组成
User-Agent 格式大致可以解析为：  
Mozilla/版本 （操作系统及版本或者内核） 内核或者引擎  浏览器及版本  
```
例如：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.186 Safari/537.36
Mozilla/5.0 ：5.0版本
Macintosh：代表mac
Intel Mac OS X 10_13_3：代表mac的版本
AppleWebKit/537.36：浏览器内核是WebKit 及版本， (KHTML, like Gecko) 代表支持KHTML排版引擎，WebKit内核在KHTML上开发而来；
Chrome/64.0.3282.186 Safari/537.36： 为chrome浏览器及版本，其中继承Safari浏览器版本537.36的内核，由此开发而来；
```
其他如，iPhone为移动端iphone操作系统，Trident为微软开发的浏览器内核，Windows NT 6.3代表win7操作系统；  

## 问题3：UA有哪些应用
这里引用（参看[3]）  
我们可以用代码模拟浏览器请求，获取页面信息，比如我们进行爬虫获取想要的数据信息；但是一些web服务设置UA反爬虫措施，也就是没有UA是不能访问的；所以在请求web服务器时，需要设置UA，但是机器发送请求太频繁的时候会被屏蔽，需要制作多个UA进行轮流发送。

## 参考：
[1] http://www.woshipm.com/it/4202257.html  
[2] https://zhuanlan.zhihu.com/p/97973031  
[3] https://zhuanlan.zhihu.com/p/35625779  
[4] https://www.cnblogs.com/cherryblossom/p/5194469.html  

## 扩展学习：
浏览器内核  
浏览器内核技术：排版渲染引擎、JavaScript引擎、其他；  
https://www.cnblogs.com/ada-zheng/p/4308581.html  
w3c标准  
