# 快手协议ulog快手did注册激活，sig3爬虫抓取签名加密算法

## 快手多个版本sig3参数逆向分析
```
目前已更新:
7.2
7.6
7.7版本
我们需要分析的是sig3参数，所以直接在ida中搜索是否有相关的引用，具体细节略过，有不懂的可以加我交流
我们先看一下大概流程。

```
![image.png](https://cdn.nlark.com/yuque/0/2020/png/97322/1607476855382-1e22cd03-1e29-44a4-b963-59a1f15d0dcb.png#align=left&display=inline&height=514&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1028&originWidth=1788&size=464447&status=done&style=none&width=894)<br>![image.png](https://cdn.nlark.com/yuque/0/2020/png/97322/1607476868618-7a119589-df8a-4e0f-a4ee-674805af0807.png#align=left&display=inline&height=662&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1324&originWidth=1934&size=308719&status=done&style=none&width=967)<br>sig3的复杂程度已经超过dy了，包括动态库加载的方式。<br>jniOnload倒不需要花太大时间研究，直接hook register方法就能拿到doCommandNative的函数地址。还有就是里面大概率有一些花指令要写脚本修复一下，<br>关键的是doCommandNative内部的根据command转发的函数地址是动态注册的，当时研究的时候他们的签名没有用VMP，主要还是花指令和代码膨胀要花些时间处理。<br>
<br>

>
> TiToData：专业的短视频、直播数据接口服务平台。
> 
> 更多信息请联系： [TiToData](https://www.titodata.com?from=douyinarticle)
> 
> 覆盖主流平台：抖音，快手，小红书，TikTok，YouTube

