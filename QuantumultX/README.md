



### 懒人配置 Profiles


> <details>
> <summary>  DivineEngine - ConnersHua </summary> 
> 
> * `出国` [Global](https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Outbound.conf) 
>
> * `回国` [China](https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Inbound.conf) 
> </details>
```ini
# Global 出国版
国内直连、海外加速
使用公共 DNS 达到快速、准确、稳定及安全的解析
海外流媒体（部分）及大陆流媒体面向港澳台限定（部分）服务指定节点
拦截应用广告、网页广告以及运营商劫持、臭名昭著的欺诈网站，保护隐私

# China 回国版
国内流媒体服务解锁
拦截应用广告、网页广告
```
&nbsp; 



### 使用指南 Usage  

> 下载预配置文件
```
# 复制配置文件链接

https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Outbound.conf

# 进入配置下载页面

[打开QuanX] > [小风车按钮] > [配置文件 - 下载]

# 下载远程配置文件

[粘贴配置链接 - 确认] > [配置文件编辑界面 - 保存] 
```


> 生成并配置证书
```
# 生成证书

[打开QuanX] > [小风车按钮] > [MitM - 生成证书] ，提示 `证书已保存`

# 配置证书

[MitM - 配置证书] > 此时会跳转至 Safari，提示 `此网站...下载一个配置描述文件。您要允许吗？`，点击`允许`，网页提示 `已下载描述文件`

[iOS系统设置] > [通用] > [描述文件] > [已下载的描述文件 - Quantumult X CA... - 安装]，输入密码******完成描述文件安装

[iOS系统设置] > [通用] > [关于本机] > [证书信任设置] > [针对根证书启用完全信任 - Quantumult X CA... - 启用]

# 开启重写、MitM

[打开QuanX] > [小风车按钮] > [重写 - 启用] > [MitM - 启用]
```

> 服务器节点订阅
```
# 复制订阅链接

复制你机场提供 ss/ssr 订阅，以及标明支持 quantumultX 格式的 V2/http/trojan 订阅

若机场不提供支持QuanX的订阅格式，可使用 '资源解析器' 或 '订阅API转换' 进行转换

# 订阅API转换 

[ https://sub.dler.io ] > [进阶模式] > [客户端 - QuantumultX] > [输出为Node List] > [生成订阅链接]

# 获取节点资源

[打开QuanX] > [小风车按钮] > [节点 - 引用（订阅）] > [资源列表（节点） - 右上角 ' + ' ] > [粘贴订阅链接 - 确认] 
```
&nbsp; 



### 个人定制 Customization 

> <details>
> <summary>  图标组 </summary>
> 
>> * [Qure](https://github.com/Koolson/Qure) - 一套专为 Quantumult X 内策略组而精心设计的图标组
>>
>> * [Orz-3](https://github.com/Orz-3/mini) - 包含了机场订阅图标，Task图标，节点地区图标，策略组图标等
> </details>
```ini
# 使用方法以及示例  [打开QuanX] > [配置文件 - 编辑] > [粘贴复制的资源链接]

[server_remote] > 节点远程订阅
https://raw.githubusercontent.com/crossutility/Quantumult-X/master/server-complete.txt, tag=Sample, as-policy=static, img-url=https://raw.githubusercontent.com/xxxx/repo/master/name.png, enabled=false

[policy] > 策略组设置
static=policy-name-1, Sample-A, Sample-B, Sample-C, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/name.png

[task_local] > 构造请求

注意此句和前后句都要用英文逗号隔开，逗号后先要空一格，且应加在 enable＝true 之前 
```

> <details>
> <summary>  分流规则 </summary>
> 
>> * [DivineEngine](https://github.com/DivineEngine/Profiles/tree/master/Quantumult/Filter)
>>
>> * [blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/QuantumultX)
> </details>
```ini
# 使用方法以及示例  [打开QuanX] > [配置文件 - 编辑] > [粘贴复制的资源链接]

[filter_remote] > 规则分流远程订阅
https://raw.githubusercontent.com/crossutility/Quantumult-X/master/filter.txt, tag=Sample, force-policy=your-policy-name, enabled=true

[filter_local] > 本地分流规则
;user-agent, ?abc*, proxy
;host, www.google.com, proxy
;host-keyword, adsite, reject
;host-suffix, googleapis.com, proxy
```

> <details>
> <summary>  Rewrite/MitM 解密 </summary>
> 
>> * [NobyDa去广告](https://github.com/NobyDa/ND-AD) - 超过4万条广告规则, 阻止常见的APP广告/隐私/行为/数据/流量/劫持的统计和追踪.
>>
>> * [毒奶去广告](https://github.com/limbopro/Adblock4limbo) - 针对iOS浏览器网页广告（弹窗横幅等），如Pornhub，奈菲影视，低端影视等，提升观影或网页浏览体验
>>
>> * [blackmatrix7去广告](https://github.com/blackmatrix7/ios_rule_script/tree/master/rewrite/QuantumultX/Advertising) - 定时爬取互联网上开源的去广告复写规则，将其进行清洗、去重、合并、优化后，形成单一的复写规则文件，旨在解决引用大量外部规则造成规则重复的问题
>>
>> * [NobyDa脚本库](https://github.com/NobyDa/Script/tree/master)
>>
>> * [blackmatrix7脚本库](https://github.com/blackmatrix7/ios_rule_script)
>>
> </details>
```ini
# 使用方法以及示例  [打开QuanX] > [配置文件 - 编辑] > [粘贴复制的资源链接]

[rewrite_remote] > 远程复写模块
https://raw.githubusercontent.com/crossutility/Quantumult-X/master/sample-import-rewrite.txt, tag=Sample, enabled=true

[rewrite_local] > 本地复写模块
^http://example\.com/resource1/1/ url reject
^http://example\.com/resource1/2/ url reject-img
```

> <details>
> <summary>  更多玩法 </summary>
> 
>> * 文字教程 : [Quantumult-X 不完全教程](https://www.notion.so/Quantumult-X-1d32ddc6e61c4892ad2ec5ea47f00917) &emsp;`Shawn`
>>
>> * 视频教程 : [Quantumult-X 系列教学](https://www.youtube.com/playlist?list=PLt2SU1VzKrncv4y3Lf-DZCB0QqoFfm-m-) &emsp;`Hell Cell`
> 
>> * 文字教程 : [BoxJs 手册](https://chavyleung.gitbook.io/boxjs) &emsp;`chavyleung`
>>
>> * 视频教程 : [BoxJs 你的多账号会话管理神器](https://www.youtube.com/watch?v=eIpBrRxiy0w&t=74s) &emsp;`Hell Cell`
> 
>> * 视频教程 : [Scriptable 年轻人的第一个小组件？](https://www.youtube.com/watch?v=nT7yGKrz_dY) &emsp;`Hell Cell`
>  
>> * 文字教程 : [Sub-Store 教程](https://www.notion.so/Sub-Store-6259586994d34c11a4ced5c406264b46) &emsp;`Peng-YM`
>>
>> * 视频教程 : [Sub-Store 你的个人订阅转换神器](https://www.youtube.com/watch?v=VXlQ4kDgqSE) &emsp;`Hell Cell`
> </details>
&nbsp; 



### 免责声明 Disclaimer  

```ini 
ONLY FOR STUDY, NOT FOR COMMERCIAL USE  
仅供研究学习，不得用于商业用途
```
  
&nbsp;  
&nbsp;
<h3 align="right"> ENJOY ! </h3>