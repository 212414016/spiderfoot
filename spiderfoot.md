<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
目录

- [spiderfoot是什么](#spiderfoot%E6%98%AF%E4%BB%80%E4%B9%88)
  - [关于SpiderFoot](#%E5%85%B3%E4%BA%8Espiderfoot)
- [安装启动](#%E5%AE%89%E8%A3%85%E5%90%AF%E5%8A%A8)
    - [运行spiderfoot](#%E8%BF%90%E8%A1%8Cspiderfoot)
- [使用](#%E4%BD%BF%E7%94%A8)
  - [New Scan (新建扫描)](#new-scan-%E6%96%B0%E5%BB%BA%E6%89%AB%E6%8F%8F)
    - [扫描模式有三种](#%E6%89%AB%E6%8F%8F%E6%A8%A1%E5%BC%8F%E6%9C%89%E4%B8%89%E7%A7%8D)
      - [按用例By Use Case](#%E6%8C%89%E7%94%A8%E4%BE%8Bby-use-case)
      - [按所需数据](#%E6%8C%89%E6%89%80%E9%9C%80%E6%95%B0%E6%8D%AE)
        - [按数据分类的 翻译](#%E6%8C%89%E6%95%B0%E6%8D%AE%E5%88%86%E7%B1%BB%E7%9A%84-%E7%BF%BB%E8%AF%91)
      - [按模块](#%E6%8C%89%E6%A8%A1%E5%9D%97)
        - [Tool](#tool)
        - [tool 描述翻译](#tool-%E6%8F%8F%E8%BF%B0%E7%BF%BB%E8%AF%91)
        - [Internal](#internal)
        - [Internal	描述翻译](#internal%09%E6%8F%8F%E8%BF%B0%E7%BF%BB%E8%AF%91)
        - [Free API](#free-api)
        - [Free API 描述翻译](#free-api-%E6%8F%8F%E8%BF%B0%E7%BF%BB%E8%AF%91)
        - [Tiered API](#tiered-api)
        - [Tiered API 描述翻译](#tiered-api-%E6%8F%8F%E8%BF%B0%E7%BF%BB%E8%AF%91)
        - [Commercial API](#commercial-api)
        - [Commercial API  描述翻译](#commercial-api--%E6%8F%8F%E8%BF%B0%E7%BF%BB%E8%AF%91)
  - [Scans (扫描列表)](#scans-%E6%89%AB%E6%8F%8F%E5%88%97%E8%A1%A8)
  - [setting（设置）](#setting%E8%AE%BE%E7%BD%AE)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


<a name="DRGiQ"></a>
# spiderfoot是什么
开源版本：[https://github.com/smicallef/spiderfoot](https://github.com/smicallef/spiderfoot)<br />SpiderFoot 是一种侦察工具，可自动查询 100 多个公共数据源 (OSINT)，以收集有关 IP 地址、域名、电子邮件地址、姓名等的情报。您只需指定要调查的目标，选择要启用的模块，然后 SpiderFoot 将收集数据以建立对所有实体及其相互关系的理解.<br />OSINT（开源情报）是公共领域中可用的数据，可能会揭示有关您的目标的有趣信息。这包括 DNS、Whois、网页、被动 DNS、垃圾邮件黑名单、文件元数据、威胁情报列表以及 SHODAN、HaveIBeenPwned? 和更多。<br />SpiderFoot HX 建立在开源版本的模块基础之上，以提供 SpiderFoot 各个方面的增强功能，包括性能、可用性、数据可视化、安全性等。
<a name="CqmCC"></a>
## 关于SpiderFoot
SpiderFoot 是一个开源的、MIT 许可的足迹工具，由[Steve Micallef](https://twitter.com/binarypool)创建。它旨在易于使用、快速和可扩展。<br />如果您有任何错误要报告或需要增强功能，请通过[support@spiderfoot.net](mailto:support@spiderfoot.net)联系支持邮件列表。<br />本次调研版本：**4.0.0**版。<br />访问项目网站[https://www.spiderfoot.net/](https://www.spiderfoot.net/r.php?u=aHR0cHM6Ly93d3cuc3BpZGVyZm9vdC5uZXQv&s=os_int)。<br />[在https://www.spiderfoot.net/documentation/](https://www.spiderfoot.net/documentation/)查看文档。<br />[在https://github.com/smicallef/spiderfoot](https://github.com/smicallef/spiderfoot) 查看 Github 存储库。<br />最新更新 @ Twitter [https://twitter.com/spiderfoot](https://twitter.com/spiderfoot)。<br />[在我们的Discord 服务器](https://discord.gg/vyvztrG)中加入社区。<br />想要具有更多功能的基于云的东西吗？[查看 SpiderFoot HX](https://www.spiderfoot.net/r.php?u=aHR0cHM6Ly93d3cuc3BpZGVyZm9vdC5uZXQvaHgvCg==&s=os_int)。

SpiderFoot 的 200 多个模块在发布者/订阅者模型中相互馈送，以确保最大限度地提取数据以执行以下操作：

- [主机/子域/TLD 枚举/提取](https://asciinema.org/a/295912)
- [电子邮件地址、电话号码和人名提取](https://asciinema.org/a/295947)
- [比特币和以太坊地址提取](https://asciinema.org/a/295957)
- [检查子域劫持的易感性](https://asciinema.org/a/344377)
- DNS 区域传输
- [威胁情报和黑名单查询](https://asciinema.org/a/295949)
- [与SHODAN](https://asciinema.org/a/127601)、[HaveIBeenPwned](https://asciinema.org/a/128731)、[GreyNoise](https://asciinema.org/a/295943)、AlienVault、SecurityTrails 等的 API 集成。
- [社交媒体帐户枚举](https://asciinema.org/a/295923)
- [S3/Azure/Digitalocean 桶枚举/抓取](https://asciinema.org/a/295941)
- IP地理位置
- 网页抓取、网页内容分析
- [图像、文档和二进制文件元数据分析](https://asciinema.org/a/296274)
- 暗网搜索
- [端口扫描和横幅抓取](https://asciinema.org/a/295939)
- [数据泄露搜索](https://asciinema.org/a/296145)
<a name="d3gzZ"></a>
# 安装启动
本次 安装是使用的 docker 安装部署的 服务<br />从 [https://github.com/smicallef/spiderfoot.git](https://github.com/smicallef/spiderfoot.git)  拉取源代码 <br />使用 SpiderFoot 提供的 Dockerfile，我们可以创建将用于运行容器的图像：<br />`docker build -t spiderfoot .`<br />镜像打包完成后运行<br />打包过程中 alpine 工具 或者 pip 包下载缓慢可以更改 Dockerfile 设置,将其下载源设置为国内源。
<a name="rXLav"></a>
### 运行spiderfoot
如果你看一下， Dockerfile 你会看到它将在容器内侦听的端口是 5001。但那是在容器内——我们需要做的是将运行容器的服务器上的一个端口映射到该端口，这样我们可以从容器外部连接到它。这就是 -p 论证的作用。下面你可以看到我们正在将本地服务器上的端口 5009 映射到端口 5001，这是 SpiderFoot 在容器中监听的端口。<br />`docker run -p 5009:5001 -d spiderfoot`

已部署完成的服务地址<br />[http://124.222.8.184:5009/](http://124.222.8.184:5009/)
<a name="MDRKu"></a>
# 使用
开启服务后打开网站 界面如下
<a name="Zi0Wj"></a>
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29274466/1670556223084-3d5e1124-dd58-4228-9dbe-073cb40cdc6c.png#averageHue=%23f9f7f6&clientId=ud05204c4-559d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=914&id=u2c429168&margin=%5Bobject%20Object%5D&name=image.png&originHeight=914&originWidth=973&originalType=binary&ratio=1&rotation=0&showTitle=false&size=153662&status=done&style=none&taskId=u7f50bec3-36d3-4e03-b55b-b378013f582&title=&width=973)
<a name="MsfPe"></a>
## New Scan (新建扫描)

 您的扫描目标可能是以下之一。SpiderFoot 会根据你输入的格式自动检测目标类型：<br />域名：例如example.com<br />IPv4 地址：例如1.2.3.4<br />IPv6 地址：例如2606:4700:4700::1111<br />主机名/子域：例如abc.example.com<br />子网：例如1.2.3.0/24<br />比特币地址：例如1HesYJSP1QqcyPEjnQ9vzBL1wujruNGe7R<br />电子邮件地址：例如bob@example.com<br />电话号码：例如+12345678901（E.164 格式）<br />人名：例如“John Smith”（必须在引号中）<br />用户名：例如“jsmith2000”（必须在引号中）<br />网络ASN : 例如1234

**Scan Name(扫描名称) —— 本次扫描的自定义名称**
<a name="m974N"></a>
### 扫描模式有三种
<a name="o7enb"></a>
#### 按用例[By Use Case](默认的四种扫描模式)

- All   

 **Get anything and everything about the target.(**获取有关目标的所有信息。**)**<br />All SpiderFoot modules will be enabled (slow) but every possible piece of information about the target will be obtained and analysed.(所有 SpiderFoot 模块都将启用（缓慢），但将获取和分析有关目标的所有可能信息。)

- Footprint

**Understand what information this target exposes to the Internet.(**了解此目标向 Internet 公开了哪些信息。**)**<br />Gain an understanding about the target's network perimeter, associated identities and other information that is obtained through a lot of web crawling and search engine use.(了解目标的网络边界、关联身份以及通过大量网络爬虫和搜索引擎使用获得的其他信息。)

- Investigate

**Best for when you suspect the target to be malicious but need more information.(**最适合当您怀疑目标是恶意的但需要更多信息时。**)**<br />Some basic footprinting will be performed in addition to querying of blacklists and other sources that may have information about your target's maliciousness.(除了查询黑名单和其他可能包含有关目标恶意信息的来源之外，还将执行一些基本的足迹追踪。)

- Passive

**When you don't want the target to even suspect they are being investigated.(**当你不想让目标怀疑他们正在接受调查时。**)**<br />As much information will be gathered without touching the target or their affiliates, therefore only modules that do not touch the target will be enabled.(由于将在不接触目标或其附属机构的情况下收集大量信息，因此只会启用不接触目标的模块。)

<a name="p0vaJ"></a>
#### 按所需数据
可选择的查询数据

| Account on External Site | Affiliate - Company Name | Interesting File | Internal SpiderFoot Root event |
| --- | --- | --- | --- |
| Affiliate - Domain Name | Affiliate - Domain Name Unregistered | Internet Name | Internet Name - Unresolved |
| Affiliate - Domain Whois | Affiliate - Email Address | Job Title | Junk File |
| Affiliate - IP Address | Affiliate - IPv6 Address | Leak Site Content | Leak Site URL |
| Affiliate - Internet Name | Affiliate - Internet Name - Unresolved | Legal Entity Identifier | Linked URL - External |
| Affiliate - Internet Name Hijackable | Affiliate - Web Content | Linked URL - Internal | Malicious AS |
| Affiliate Description - Abstract | Affiliate Description - Category | Malicious Affiliate | Malicious Affiliate IP Address |
| App Store Entry | BGP AS Membership | Malicious Bitcoin Address | Malicious Co-Hosted Site |
| BGP AS Ownership | Base64-encoded Data | Malicious E-mail Address | Malicious IP Address |
| Bitcoin Address | Bitcoin Balance | Malicious IP on Owned Netblock | Malicious IP on Same Subnet |
| Blacklisted Affiliate IP Address | Blacklisted Affiliate Internet Name | Malicious Internet Name | Malicious Phone Number |
| Blacklisted Co-Hosted Site | Blacklisted IP Address | Name Server (DNS NS Records) | Netblock IPv6 Membership |
| Blacklisted IP on Owned Netblock | Blacklisted IP on Same Subnet | Netblock IPv6 Ownership | Netblock Membership |
| Blacklisted Internet Name | Cloud Storage Bucket | Netblock Ownership | Netblock Whois |
| Cloud Storage Bucket Open | Co-Hosted Site | Non-Standard HTTP Header | Open TCP Port |
| Co-Hosted Site - Domain Name | Co-Hosted Site - Domain Whois | Open TCP Port Banner | Open UDP Port |
| Company Name | Compromised Password | Open UDP Port Information | Operating System |
| Compromised Password Hash | Cookies | PGP Public Key | Phone Number |
| Country Name | Credit Card Number | Phone Number Compromised | Phone Number Type |
| DNS SPF Record | DNS SRV Record | Physical Address | Physical Coordinates |
| DNS TXT Record | Darknet Mention URL | Physical Location | Proxy Host |
| Darknet Mention Web Content | Date of Birth | Public Code Repository | Raw DNS Records |
| Defaced | Defaced Affiliate | Raw Data from RIRs/APIs | Raw File Meta Data |
| Defaced Affiliate IP Address | Defaced Co-Hosted Site | SSL Certificate - Issued by | SSL Certificate - Issued to |
| Defaced IP Address | Deliverable Email Address | SSL Certificate - Raw Data | SSL Certificate Expired |
| Description - Abstract | Description - Category | SSL Certificate Expiring | SSL Certificate Host Mismatch |
| Device Type | Disposable Email Address | Search Engine Web Content | Similar Account on External Site |
| Domain Name | Domain Name (Parent) | Similar Domain | Similar Domain - Whois |
| Domain Registrar | Domain Whois | Social Media Presence | Software Used |
| Email Address | Email Address - Generic | TOR Exit Node | Telecommunications Provider |
| Email Gateway (DNS MX Records) | Error Message | URL (Accepts Passwords) | URL (Accepts Uploads) |
| Ethereum Address | Ethereum Balance | URL (AdBlocked External) | URL (AdBlocked Internal) |
| Externally Hosted Javascript | HTTP Headers | URL (Form) | URL (Purely Static) |
| HTTP Status Code | Hacked Account on External Site | URL (Uses Flash) | URL (Uses Java Applet) |
| Hacked Email Address | Hacked User Account on External Site | URL (Uses Javascript) | URL (Uses a Web Framework) |
| Hash | Historic Interesting File | Undeliverable Email Address | Username |
| Historic URL (Accepts Passwords) | Historic URL (Accepts Uploads) | VPN Host | Vulnerability - CVE Critical |
| Historic URL (Form) | Historic URL (Purely Static) | Vulnerability - CVE High | Vulnerability - CVE Low |
| Historic URL (Uses Flash) | Historic URL (Uses Java Applet) | Vulnerability - CVE Medium | Vulnerability - General |
| Historic URL (Uses Javascript) | Historic URL (Uses a Web Framework) | Vulnerability - Third Party Disclosure | Web Analytics |
| Hosting Provider | Human Name | Web Content | Web Content Type |
| IBAN Number | IP Address | Web Server | Web Technology |
| IP Address - Internal Network | IPv6 Address | WiFi Access Point Nearby | Wikipedia Page Edit |

<a name="oYb5Q"></a>
##### 按数据分类的 翻译
| 外部网站帐户 | 附属公司 - 公司名称 | 有趣的文件 | 内部 SpiderFoot Root 事件 |
| --- | --- | --- | --- |
| 关联 - 域名 | 关联 - 域名未注册 | 互联网名称 | Internet 名称 - 未解析 |
| 关联 - 域 Whois | 关联 - 电子邮件地址 | 职称 | 垃圾文件 |
| 关联 - IP 地址 | 关联 - IPv6 地址 | 泄漏网站内容 | 泄漏站点 URL |
| 关联 - 互联网名称 | 附属公司 - 互联网名称 - 未解决 | 法律实体标识符 | 链接的 URL - 外部 |
| 关联 - 互联网名称可劫持 | 关联 - 网页内容 | 链接的 URL - 内部 | 恶意AS |
| 关联描述 - 摘要 | 关联描述 - 类别 | 恶意关联 | 恶意关联 IP 地址 |
| 应用商店入口 | BGP 自治系统成员 | 恶意比特币地址 | 恶意共同托管站点 |
| BGP 自治系统所有权 | Base64 编码数据 | 恶意电子邮件地址 | 恶意 IP 地址 |
| 比特币地址 | 比特币余额 | 拥有的 Netblock 上的恶意 IP | 同一子网上的恶意 IP |
| 列入黑名单的附属 IP 地址 | 列入黑名单的附属互联网名称 | 恶意互联网名称 | 恶意电话号码 |
| 列入黑名单的联合托管网站 | 列入黑名单的 IP 地址 | 名称服务器（DNS NS 记录） | Netblock IPv6 关联资格 |
| 拥有的 Netblock 上的黑名单 IP | 同一子网上的黑名单 IP | Netblock IPv6 所有权 | Netblock 关联资格 |
| 列入黑名单的互联网名称 | 云存储桶 | Netblock 所有权 | 网络封锁域名 |
| 云存储桶打开 | 共同主办的网站 | 非标准 HTTP 标头 | 打开 TCP 端口 |
| 共同托管网站 - 域名 | 共同托管站点 - 域 Whois | 打开 TCP 端口横幅 | 打开UDP端口 |
| 公司名 | 密码泄露 | 打开UDP端口信息 | 操作系统 |
| 泄露的密码哈希 | Cookies | PGP 公钥 | 电话号码 |
| 国家的名字 | 信用卡号码 | 电话号码泄露 | 电话号码类型 |
| DNS SPF 记录 | DNS SRV 记录 | 实际地址 | 物理坐标 |
| DNS TXT 记录 | 暗网提及 URL | 物理位置 | 代理主机 |
| 暗网提及网页内容 | 出生日期 | 公共代码库 | 原始 DNS 记录 |
| 污损 | 污损的关联 | 来自 RIR/API 的原始数据 | 原始文件元数据 |
| 损坏的关联 IP 地址 | 损坏的共同托管网站 | SSL 证书 - 颁发者 | SSL 证书 - 颁发给 |
| 损坏的 IP 地址 | 可交付的电子邮件地址 | SSL 证书 - 原始数据 | SSL证书过期 |
| 描述 - 摘要 | 描述 - 类别 | SSL 证书即将到期 | SSL 证书主机不匹配 |
| 设备类型 | 一次性电子邮件地址 | 搜索引擎网页内容 | 外部网站上的类似帐户 |
| 域名 | 域名（父） | 相似域名 | 相似域 - Whois |
| 域名注册商 | 域域名 | 社交媒体存在 | 使用的软件 |
| 电子邮件地址 | 电子邮件地址 - 通用 | TOR 出口节点 | 电信供应商 |
| 电子邮件网关（DNS MX 记录） | 错误信息 | URL（接受密码） | URL（接受上传） |
| 以太坊地址 | 以太币余额 | 网址（广告拦截外部） | 网址（内部广告拦截） |
| 外部托管的 Javascript | HTTP 标头 | 网址（表格） | 网址（纯静态） |
| HTTP 状态码 | 外部网站上的被黑帐户 | 网址（使用 Flash） | URL（使用 Java Applet） |
| 被黑的电子邮件地址 | 外部站点上的被黑用户帐户 | 网址（使用 Javascript） | URL（使用 Web 框架） |
| 散列 | 具有历史意义的文件 | 无法送达的电子邮件地址 | 用户名 |
| 历史 URL（接受密码） | 历史 URL（接受上传） | 虚拟主机 | 漏洞 - CVE 严重 |
| 历史网址（表格） | 历史 URL（纯静态） | 漏洞 - CVE 高 | 漏洞 - CVE 低 |
| 历史 URL（使用 Flash） | 历史 URL（使用 Java Applet） | 漏洞 - CVE Medium | 漏洞 - 一般 |
| 历史 URL（使用 Javascript） | 历史 URL（使用 Web 框架） | 漏洞 - 第三方披露 | 网站分析 |
| 托管服务提供商 | 人名 | 网页内容 | 网页内容类型 |
| IBAN号码 | IP地址 | 网络服务器 | 网络技术 |
| IP 地址 - 内部网络 | IPv6地址 | 附近的 WiFi 接入点 | 维基百科页面编辑 |

<a name="n3UQn"></a>
#### 按模块
模块类型分为	Tool  Internal	Free API	Tiered API	Commercial API 五大类
<a name="s4HcG"></a>
##### Tool
| **Name** | **Description** | **Type** |
| --- | --- | --- |
| Tool - CMSeeK | Identify what Content Management System (CMS) might be used. | Tool |
| Tool - DNSTwist | Identify bit-squatting, typo and other similar domains to the target using a local DNSTwist installation. | Tool |
| Tool - nbtscan | Scans for open NETBIOS nameservers on your target's network. | Tool |
| Tool - Nmap | Identify what Operating System might be used. | Tool |
| Tool - Nuclei | Fast and customisable vulnerability scanner. | Tool |
| Tool - onesixtyone | Fast scanner to find publicly exposed SNMP services. | Tool |
| Tool - Retire.js | Scanner detecting the use of JavaScript libraries with known vulnerabilities | Tool |
| Tool - snallygaster | Finds file leaks and other security problems on HTTP servers. | Tool |
| Tool - testssl.sh | Identify various TLS/SSL weaknesses, including Heartbleed, CRIME and ROBOT. | Tool |
| Tool - TruffleHog | Searches through git repositories for high entropy strings and secrets, digging deep into commit history. | Tool |
| Tool - WAFW00F | Identify what web application firewall (WAF) is in use on the specified website. | Tool |
| Tool - Wappalyzer | Wappalyzer indentifies technologies on websites. | Tool |
| Tool - WhatWeb | Identify what software is in use on the specified website. | Tool |

<a name="KiN2Q"></a>
##### tool 描述翻译
| 名称 | 描述 | 类型 |
| --- | --- | --- |
| Tool - CMSeeK | 确定可能使用的内容管理系统 (CMS)。 | 工具 |
| Tool - DNSTwist | 使用本地 DNSTwist 安装识别目标的位抢注、拼写错误和其他类似域。 | 工具 |
| Tool - nbtscan | 扫描目标网络上的开放 NETBIOS 名称服务器。 | 工具 |
| Tool - Nmap | 确定可能使用的操作系统。 | 工具 |
| Tool - Nuclei | 快速且可定制的漏洞扫描器。 | 工具 |
| Tool - onesixtyone | 用于查找公开暴露的 SNMP 服务的快速扫描器。 | 工具 |
| Tool - Retire.js | 检测使用具有已知漏洞的 JavaScript 库的扫描程序 | 工具 |
| Tool - snallygaster | 查找 HTTP 服务器上的文件泄漏和其他安全问题。 | 工具 |
| Tool - testssl.sh | 识别各种 TLS/SSL 弱点，包括 Heartbleed、CRIME 和 ROBOT。 | 工具 |
| Tool - TruffleHog | 在 git 存储库中搜索高熵字符串和秘密，深入挖掘提交历史。 | 工具 |
| Tool - WAFW00F | 识别指定网站上正在使用的 Web 应用程序防火墙 (WAF)。 | 工具 |
| Tool - Wappalyzer | Wappalyzer 识别网站上的技术。 | 工具 |
| Tool - WhatWeb | 识别指定网站上正在使用的软件。 | 工具 |

<a name="GX5cc"></a>
#####  Internal	
| **Name** | **Description** | **Type** |
| --- | --- | --- |
| Account Finder | Look for possible associated accounts on over 500 social and other websites such as Instagram, Reddit, etc. | Internal |
| Base64 Decoder | Identify Base64-encoded strings in URLs, often revealing interesting hidden information. | Internal |
| Binary String Extractor | Attempt to identify strings in binary content. | Internal |
| Bitcoin Finder | Identify bitcoin addresses in scraped webpages. | Internal |
| Company Name Extractor | Identify company names in any obtained data. | Internal |
| Cookie Extractor | Extract Cookies from HTTP headers. | Internal |
| Country Name Extractor | Identify country names in any obtained data. | Internal |
| Credit Card Number Extractor | Identify Credit Card Numbers in any data | Internal |
| Cross-Referencer | Identify whether other domains are associated ('Affiliates') of the target by looking for links back to the target site(s). | Internal |
| Custom Threat Feed | Check if a host/domain, netblock, ASN or IP is malicious according to your custom feed. | Internal |
| DNS Brute-forcer | Attempts to identify hostnames through brute-forcing common names and iterations. | Internal |
| DNS Common SRV | Attempts to identify hostnames through brute-forcing common DNS SRV records. | Internal |
| DNS Look-aside | Attempt to reverse-resolve the IP addresses next to your target to see if they are related. | Internal |
| DNS Raw Records | Retrieves raw DNS records such as MX, TXT and others. | Internal |
| DNS Resolver | Resolves hosts and IP addresses identified, also extracted from raw content. | Internal |
| DNS Zone Transfer | Attempts to perform a full DNS zone transfer. | Internal |
| E-Mail Address Extractor | Identify e-mail addresses in any obtained data. | Internal |
| Error String Extractor | Identify common error messages in content like SQL errors, etc. | Internal |
| Ethereum Address Extractor | Identify ethereum addresses in scraped webpages. | Internal |
| File Metadata Extractor | Extracts meta data from documents and images. | Internal |
| Hash Extractor | Identify MD5 and SHA hashes in web content, files and more. | Internal |
| Hosting Provider Identifier | Find out if any IP addresses identified fall within known 3rd party hosting ranges, e.g. Amazon, Azure, etc. | Internal |
| Human Name Extractor | Attempt to identify human names in fetched content. | Internal |
| IBAN Number Extractor | Identify International Bank Account Numbers (IBANs) in any data. | Internal |
| Interesting File Finder | Identifies potential files of interest, e.g. office documents, zip files. | Internal |
| Junk File Finder | Looks for old/temporary and other similar files. | Internal |
| Page Information | Obtain information about web pages (do they take passwords, do they contain forms, etc.) | Internal |
| PGP Key Servers | Look up domains and e-mail addresses in PGP public key servers. | Internal |
| Phone Number Extractor | Identify phone numbers in scraped webpages. | Internal |
| Port Scanner - TCP | Scans for commonly open TCP ports on Internet-facing systems. | Internal |
| Similar Domain Finder | Search various sources to identify similar looking domain names, for instance squatted domains. | Internal |
| Social Network Identifier | Identify presence on social media networks such as LinkedIn, Twitter and others. | Internal |
| SSL Certificate Analyzer | Gather information about SSL certificates used by the target's HTTPS sites. | Internal |
| Strange Header Identifier | Obtain non-standard HTTP headers returned by web servers. | Internal |
| Subdomain Takeover Checker | Check if affiliated subdomains are vulnerable to takeover. | Internal |
| TLD Searcher | Search all Internet TLDs for domains with the same name as the target (this can be very slow.) | Internal |
| Web Analytics Extractor | Identify web analytics IDs in scraped webpages and DNS TXT records. | Internal |
| Web Framework Identifier | Identify the usage of popular web frameworks like jQuery, YUI and others. | Internal |
| Web Server Identifier | Obtain web server banners to identify versions of web servers being used. | Internal |
| Web Spider | Spidering of web-pages to extract content for searching. | Internal |
| Whois | Perform a WHOIS look-up on domain names and owned netblocks. | Internal |

<a name="jzTlp"></a>
##### Internal	描述翻译
| 名称 | 描述 | 类型 |
| --- | --- | --- |
| Account Finder | 在 500 多个社交网站和其他网站（例如 Instagram、Reddit 等）上寻找可能的关联帐户。 | 内部的 |
| Base64 Decoder | 识别 URL 中的 Base64 编码字符串，通常会揭示有趣的隐藏信息。 | 内部的 |
| Binary String Extractor | 尝试识别二进制内容中的字符串。 | 内部的 |
| Bitcoin Finder | 在抓取的网页中识别比特币地址。 | 内部的 |
| Company Name Extractor | 在任何获得的数据中识别公司名称。 | 内部的 |
| Cookie Extractor | 从 HTTP 标头中提取 Cookie。 | 内部的 |
| Country Name Extractor | 在任何获得的数据中识别国家名称。 | 内部的 |
| Credit Card Number Extractor | 识别任何数据中的信用卡号 | 内部的 |
| Cross-Referencer | 通过查找指向目标站点的链接来确定其他域是否与目标相关联（“关联”）。 | 内部的 |
| Custom Threat Feed | 根据您的自定义提要检查主机/域、netblock、ASN 或 IP 是否是恶意的。 | 内部的 |
| DNS Brute-forcer | 尝试通过强制通用名称和迭代来识别主机名。 | 内部的 |
| DNS Common SRV | 尝试通过暴力破解常见的 DNS SRV 记录来识别主机名。 | 内部的 |
| DNS Look-aside | 尝试反向解析目标旁边的 IP 地址，看看它们是否相关。 | 内部的 |
| DNS Raw Records | 检索原始 DNS 记录，例如 MX、TXT 等。 | 内部的 |
| DNS Resolver | 解析识别的主机和 IP 地址，也从原始内容中提取。 | 内部的 |
| DNS Zone Transfer | 尝试执行完整的 DNS 区域传输。 | 内部的 |
| E-Mail Address Extractor | 在任何获得的数据中识别电子邮件地址。 | 内部的 |
| Error String Extractor | 识别内容中的常见错误消息，如 SQL 错误等。 | 内部的 |
| Ethereum Address Extractor | 识别抓取网页中的以太坊地址。 | 内部的 |
| File Metadata Extractor | 从文档和图像中提取元数据。 | 内部的 |
| Hash Extractor | 识别 Web 内容、文件等中的 MD5 和 SHA 哈希值。 | 内部的 |
| Hosting Provider Identifier | 查明识别出的任何 IP 地址是否属于已知的第 3 方托管范围，例如 Amazon、Azure 等。 | 内部的 |
| Human Name Extractor | 尝试在获取的内容中识别人名。 | 内部的 |
| IBAN Number Extractor | 识别任何数据中的国际银行帐号 (IBAN)。 | 内部的 |
| Interesting File Finder | 识别可能感兴趣的文件，例如办公文档、zip 文件。 | 内部的 |
| Junk File Finder | 查找旧的/临时的和其他类似的文件。 | 内部的 |
| Page Information | 获取有关网页的信息（是否需要密码，是否包含表格等） | 内部的 |
| PGP Key Servers | 在 PGP 公钥服务器中查找域和电子邮件地址。 | 内部的 |
| Phone Number Extractor | 识别抓取网页中的电话号码。 | 内部的 |
| Port Scanner - TCP | 在面向 Internet 的系统上扫描通常打开的 TCP 端口。 | 内部的 |
| Similar Domain Finder | 搜索各种来源以识别外观相似的域名，例如被抢注的域名。 | 内部的 |
| Social Network Identifier | 确定在社交媒体网络（例如 LinkedIn、Twitter 等）上的存在。 | 内部的 |
| SSL Certificate Analyzer | 收集有关目标的 HTTPS 站点使用的 SSL 证书的信息。 | 内部的 |
| Strange Header Identifier | 获取 Web 服务器返回的非标准 HTTP 标头。 | 内部的 |
| Subdomain Takeover Checker | 检查附属子域是否容易被接管。 | 内部的 |
| TLD Searcher | 在所有 Internet TLD 中搜索与目标同名的域（这可能非常慢。） | 内部的 |
| Web Analytics Extractor | 在抓取的网页和 DNS TXT 记录中识别网络分析 ID。 | 内部的 |
| Web Framework Identifier | 识别流行的 Web 框架（如 jQuery、YUI 等）的用法。 | 内部的 |
| Web Server Identifier | 获取 Web 服务器横幅以识别正在使用的 Web 服务器的版本。 | 内部的 |
| Web Spider | 抓取网页以提取内容进行搜索。 | 内部的 |
| Whois | 对域名和拥有的网络块执行 WHOIS 查询。 | 内部的 |

<a name="fYneU"></a>
##### Free API	
| **Name** | **Description** | **Type** |
| --- | --- | --- |
| [abuse.ch](https://www.abuse.ch/) | Check if a host/domain, IP address or netblock is malicious according to Abuse.ch. | Free API |
| [AdGuard DNS](https://adguard.com/) | Check if a host would be blocked by AdGuard DNS. | Free API |
| [Ahmia](https://ahmia.fi/) | Search Tor 'Ahmia' search engine for mentions of the target. | Free API |
| [AlienVault IP Reputation](https://cybersecurity.att.com/) | Check if an IP or netblock is malicious according to the AlienVault IP Reputation database. | Free API |
| [Amazon S3 Bucket Finder](https://aws.amazon.com/s3/) | Search for potential Amazon S3 buckets associated with the target and attempt to list their contents. | Free API |
| [Apple iTunes](https://itunes.apple.com/) | Search Apple iTunes for mobile apps. | Free API |
| [Archive.org](https://archive.org/) | Identifies historic versions of interesting files/pages from the Wayback Machine. | Free API |
| [ARIN](https://www.arin.net/) | Queries ARIN registry for contact information. | Free API |
| [Azure Blob Finder](https://azure.microsoft.com/en-in/services/storage/blobs/) | Search for potential Azure blobs associated with the target and attempt to list their contents. | Free API |
| [BGPView](https://bgpview.io/) | Obtain network information from BGPView API. | Free API |
| [BitcoinAbuse](https://www.bitcoinabuse.com/) | Check Bitcoin addresses against the bitcoinabuse.com database of suspect/malicious addresses. | Free API |
| [Blockchain](https://www.blockchain.com/) | Queries blockchain.info to find the balance of identified bitcoin wallet addresses. | Free API |
| [blocklist.de](http://www.blocklist.de/en/index.html) | Check if a netblock or IP is malicious according to blocklist.de. | Free API |
| [botvrij.eu](https://botvrij.eu/) | Check if a domain is malicious according to botvrij.eu. | Free API |
| [CallerName](http://callername.com/) | Lookup US phone number location and reputation information. | Free API |
| [Certificate Transparency](https://crt.sh/) | Gather hostnames from historical certificates in crt.sh. | Free API |
| [CINS Army List](https://cinsscore.com/) | Check if a netblock or IP address is malicious according to Collective Intelligence Network Security (CINS) Army list. | Free API |
| [CIRCL.LU](https://www.circl.lu/) | Obtain information from CIRCL.LU's Passive DNS and Passive SSL databases. | Free API |
| [CleanBrowsing.org](https://cleanbrowsing.org/) | Check if a host would be blocked by CleanBrowsing.org DNS content filters. | Free API |
| [CleanTalk Spam List](https://cleantalk.org/) | Check if a netblock or IP address is on CleanTalk.org's spam IP list. | Free API |
| [CloudFlare DNS](https://www.cloudflare.com/) | Check if a host would be blocked by CloudFlare DNS. | Free API |
| [CoinBlocker Lists](https://zerodot1.gitlab.io/CoinBlockerListsWeb/) | Check if a domain appears on CoinBlocker lists. | Free API |
| [CommonCrawl](http://commoncrawl.org/) | Searches for URLs found through CommonCrawl.org. | Free API |
| [Crobat API](https://sonar.omnisint.io/) | Search Crobat API for subdomains. | Free API |
| [CRXcavator](https://crxcavator.io/) | Search CRXcavator for Chrome extensions. | Free API |
| [CyberCrime-Tracker.net](https://cybercrime-tracker.net/) | Check if a host/domain or IP address is malicious according to CyberCrime-Tracker.net. | Free API |
| [Debounce](https://debounce.io/) | Check whether an email is disposable | Free API |
| [Digital Ocean Space Finder](https://www.digitalocean.com/products/spaces/) | Search for potential Digital Ocean Spaces associated with the target and attempt to list their contents. | Free API |
| [DNS for Family](https://dnsforfamily.com/) | Check if a host would be blocked by DNS for Family. | Free API |
| [DNSDumpster](https://dnsdumpster.com/) | Passive subdomain enumeration using HackerTarget's DNSDumpster | Free API |
| [DNSGrep](https://opendata.rapid7.com/) | Obtain Passive DNS information from Rapid7 Sonar Project using DNSGrep API. | Free API |
| [DroneBL](https://dronebl.org/) | Query the DroneBL database for open relays, open proxies, vulnerable servers, etc. | Free API |
| [DuckDuckGo](https://duckduckgo.com/) | Query DuckDuckGo's API for descriptive information about your target. | Free API |
| [EmailFormat](https://www.email-format.com/) | Look up e-mail addresses on email-format.com. | Free API |
| [Emerging Threats](https://rules.emergingthreats.net/) | Check if a netblock or IP address is malicious according to EmergingThreats.net. | Free API |
| [Etherscan](https://etherscan.io/) | Queries etherscan.io to find the balance of identified ethereum wallet addresses. | Free API |
| [Flickr](https://www.flickr.com/) | Search Flickr for domains, URLs and emails related to the specified domain. | Free API |
| [FortiGuard Antispam](https://www.fortiguard.com/) | Check if an IP address is malicious according to FortiGuard Antispam. | Free API |
| [Github](https://github.com/) | Identify associated public code repositories on Github. | Free API |
| [Google Object Storage Finder](https://cloud.google.com/storage) | Search for potential Google Object Storage buckets associated with the target and attempt to list their contents. | Free API |
| [Google SafeBrowsing](https://developers.google.com/safe-browsing/v4/lookup-api) | Check if the URL is included on any of the Safe Browsing lists. | Free API |
| [Gravatar](https://secure.gravatar.com/) | Retrieve user information from Gravatar API. | Free API |
| [Greensnow](https://greensnow.co/) | Check if a netblock or IP address is malicious according to greensnow.co. | Free API |
| [grep.app](https://grep.app/) | Search grep.app API for links and emails related to the specified domain. | Free API |
| [HackerOne (Unofficial)](http://www.nobbd.de/) | Check external vulnerability scanning/reporting service h1.nobbd.de to see if the target is listed. | Free API |
| [HackerTarget](https://hackertarget.com/) | Search HackerTarget.com for hosts sharing the same IP. | Free API |
| [Hybrid Analysis](https://www.hybrid-analysis.com/) | Search Hybrid Analysis for domains and URLs related to the target. | Free API |
| [Instagram](https://www.instagram.com/) | Gather information from Instagram profiles. | Free API |
| [Internet Storm Center](https://isc.sans.edu/) | Check if an IP address is malicious according to SANS ISC. | Free API |
| [Keybase](https://keybase.io/) | Obtain additional information about domain names and identified usernames. | Free API |
| [LeakIX](https://leakix.net/) | Search LeakIX for host data leaks, open ports, software and geoip. | Free API |
| [Leak-Lookup](https://leak-lookup.com/) | Searches Leak-Lookup.com's database of breaches. | Free API |
| [Maltiverse](https://maltiverse.com/) | Obtain information about any malicious activities involving IP addresses | Free API |
| [Mnemonic PassiveDNS](https://www.mnemonic.no/) | Obtain Passive DNS information from PassiveDNS.mnemonic.no. | Free API |
| [multiproxy.org Open Proxies](https://multiproxy.org/) | Check if an IP address is an open proxy according to multiproxy.org open proxy list. | Free API |
| [MySpace](https://myspace.com/) | Gather username and location from MySpace.com profiles. | Free API |
| [Onion.link](https://onion.link/) | Search Tor 'Onion City' search engine for mentions of the target domain using Google Custom Search. | Free API |
| [Onionsearchengine.com](https://as.onionsearchengine.com/) | Search Tor onionsearchengine.com for mentions of the target domain. | Free API |
| [Open Bug Bounty](https://www.openbugbounty.org/) | Check external vulnerability scanning/reporting service openbugbounty.org to see if the target is listed. | Free API |
| [OpenDNS](https://www.opendns.com/) | Check if a host would be blocked by OpenDNS. | Free API |
| [OpenNIC DNS](https://www.opennic.org/) | Resolves host names in the OpenNIC alternative DNS system. | Free API |
| [OpenPhish](https://openphish.com/) | Check if a host/domain is malicious according to OpenPhish.com. | Free API |
| [OpenStreetMap](https://www.openstreetmap.org/) | Retrieves latitude/longitude coordinates for physical addresses from OpenStreetMap API. | Free API |
| [PhishStats](https://phishstats.info/) | Check if a netblock or IP address is malicious according to PhishStats. | Free API |
| [PhishTank](https://phishtank.com/) | Check if a host/domain is malicious according to PhishTank. | Free API |
| [Project Honey Pot](https://www.projecthoneypot.org/) | Query the Project Honey Pot database for IP addresses. | Free API |
| [Psbdmp](https://psbdmp.cc/) | Check psbdmp.cc (PasteBin Dump) for potentially hacked e-mails and domains. | Free API |
| [PunkSpider](https://punkspider.io/) | Check the QOMPLX punkspider.io service to see if the target is listed as vulnerable. | Free API |
| [Quad9](https://quad9.net/) | Check if a host would be blocked by Quad9 DNS. | Free API |
| [ReverseWhois](https://www.reversewhois.io/) | Reverse Whois lookups using reversewhois.io. | Free API |
| [RIPE](https://www.ripe.net/) | Queries the RIPE registry (includes ARIN data) to identify netblocks and other info. | Free API |
| [Robtex](https://www.robtex.com/) | Search Robtex.com for hosts sharing the same IP. | Free API |
| [searchcode](https://searchcode.com/) | Search searchcode for code repositories mentioning the target domain. | Free API |
| [Skymem](http://www.skymem.info/) | Look up e-mail addresses on Skymem. | Free API |
| [SlideShare](https://www.slideshare.net/) | Gather name and location from SlideShare profiles. | Free API |
| [SORBS](http://www.sorbs.net/) | Query the SORBS database for open relays, open proxies, vulnerable servers, etc. | Free API |
| [SpamCop](https://www.spamcop.net/) | Check if a netblock or IP address is in the SpamCop database. | Free API |
| [Spamhaus Zen](https://www.spamhaus.org/) | Check if a netblock or IP address is in the Spamhaus Zen database. | Free API |
| [Steven Black Hosts](https://github.com/StevenBlack/hosts) | Check if a domain is malicious (malware or adware) according to Steven Black Hosts list. | Free API |
| [Sublist3r PassiveDNS](https://api.sublist3r.com/) | Passive subdomain enumeration using Sublist3r's API | Free API |
| [SURBL](http://www.surbl.org/) | Check if a netblock, IP address or domain is in the SURBL blacklist. | Free API |
| [Talos Intelligence](https://talosintelligence.com/) | Check if a netblock or IP address is malicious according to TalosIntelligence. | Free API |
| [ThreatCrowd](https://www.threatcrowd.org/) | Obtain information from ThreatCrowd about identified IP addresses, domains and e-mail addresses. | Free API |
| [ThreatFox](https://threatfox.abuse.ch/) | Check if an IP address is malicious according to ThreatFox. | Free API |
| [ThreatMiner](https://www.threatminer.org/) | Obtain information from ThreatMiner's database for passive DNS and threat intelligence. | Free API |
| [TOR Exit Nodes](https://metrics.torproject.org/) | Check if an IP adddress or netblock appears on the Tor Metrics exit node list. | Free API |
| [TORCH](https://torchsearch.wordpress.com/) | Search Tor 'TORCH' search engine for mentions of the target domain. | Free API |
| [Trumail](https://trumail.io/) | Check whether an email is disposable | Free API |
| [Twitter](https://twitter.com/) | Gather name and location from Twitter profiles. | Free API |
| [UCEPROTECT](http://www.uceprotect.net/) | Check if a netblock or IP address is in the UCEPROTECT database. | Free API |
| [URLScan.io](https://urlscan.io/) | Search URLScan.io cache for domain information. | Free API |
| [Venmo](https://venmo.com/) | Gather user information from Venmo API. | Free API |
| [VoIP Blacklist (VoIPBL)](https://voipbl.org/) | Check if an IP address or netblock is malicious according to VoIP Blacklist (VoIPBL). | Free API |
| [VXVault.net](http://vxvault.net/) | Check if a domain or IP address is malicious according to VXVault.net. | Free API |
| [WiGLE](https://wigle.net/) | Query WiGLE to identify nearby WiFi access points. | Free API |
| [Wikileaks](https://wikileaks.org/) | Search Wikileaks for mentions of domain names and e-mail addresses. | Free API |
| [Wikipedia Edits](https://www.wikipedia.org/) | Identify edits to Wikipedia articles made from a given IP address or username. | Free API |
| [Yandex DNS](https://yandex.com/) | Check if a host would be blocked by Yandex DNS. | Free API |
| [Zone-H Defacement Check](https://zone-h.org/) | Check if a hostname/domain appears on the zone-h.org 'special defacements' RSS feed. | Free API |

<a name="i4eH8"></a>
##### Free API 描述翻译
| 名称 | 描述 | 类型 |
| --- | --- | --- |
| [abuse.ch](https://www.abuse.ch/) | 根据 Abuse.ch 检查主机/域、IP 地址或网络块是否是恶意的。 | 免费API |
| [AdGuard DNS](https://adguard.com/) | 检查主机是否会被 AdGuard DNS 阻止。 | 免费API |
| [Ahmia](https://ahmia.fi/) | 在 Tor“Ahmia”搜索引擎中搜索目标的提及。 | 免费API |
| [AlienVault IP Reputation](https://cybersecurity.att.com/) | 根据 AlienVault IP 信誉数据库检查 IP 或网络块是否是恶意的。 | 免费API |
| [Amazon S3 Bucket Finder](https://aws.amazon.com/s3/) | 搜索与目标关联的潜在 Amazon S3 存储桶并尝试列出其内容。 | 免费API |
| [Apple iTunes](https://itunes.apple.com/) | 在 Apple iTunes 中搜索移动应用程序。 | 免费API |
| [Archive.org](https://archive.org/) | 从 Wayback Machine 识别有趣文件/页面的历史版本。 | 免费API |
| [ARIN](https://www.arin.net/) | 查询 ARIN 注册表以获取联系信息。 | 免费API |
| [Azure Blob Finder](https://azure.microsoft.com/en-in/services/storage/blobs/) | 搜索与目标关联的潜在 Azure blob 并尝试列出其内容。 | 免费API |
| [BGPView](https://bgpview.io/) | 从 BGPView API 获取网络信息。 | 免费API |
| [BitcoinAbuse](https://www.bitcoinabuse.com/) | 根据可疑/恶意地址的 bitcoinabuse.com 数据库检查比特币地址。 | 免费API |
| [Blockchain](https://www.blockchain.com/) | 查询 blockchain.info 以查找已识别的比特币钱包地址的余额。 | 免费API |
| [blocklist.de](http://www.blocklist.de/en/index.html) | 根据 blocklist.de 检查 netblock 或 IP 是否是恶意的。 | 免费API |
| [botvrij.eu](https://botvrij.eu/) | 根据 botvrij.eu 检查域名是否恶意。 | 免费API |
| [CallerName](http://callername.com/) | 查找美国电话号码位置和声誉信息。 | 免费API |
| [Certificate Transparency](https://crt.sh/) | 从 crt.sh 中的历史证书收集主机名。 | 免费API |
| [CINS Army List](https://cinsscore.com/) | 根据 Collective Intelligence Network Security (CINS) Army 列表检查 netblock 或 IP 地址是否是恶意的。 | 免费API |
| [CIRCL.LU](https://www.circl.lu/) | 从 CIRCL.LU 的被动 DNS 和被动 SSL 数据库获取信息。 | 免费API |
| [CleanBrowsing.org](https://cleanbrowsing.org/) | 检查主机是否会被 CleanBrowsing.org DNS 内容过滤器阻止。 | 免费API |
| [CleanTalk Spam List](https://cleantalk.org/) | 检查网络屏蔽或 IP 地址是否在 CleanTalk.org 的垃圾邮件 IP 列表中。 | 免费API |
| [CloudFlare DNS](https://www.cloudflare.com/) | 检查主机是否会被 CloudFlare DNS 阻止。 | 免费API |
| [CoinBlocker Lists](https://zerodot1.gitlab.io/CoinBlockerListsWeb/) | 检查域是否出现在 CoinBlocker 列表中。 | 免费API |
| [CommonCrawl](http://commoncrawl.org/) | 搜索通过 CommonCrawl.org 找到的 URL。 | 免费API |
| [Crobat API](https://sonar.omnisint.io/) | 在 Crobat API 中搜索子域。 | 免费API |
| [CRXcavator](https://crxcavator.io/) | 在 CRXcavator 中搜索 Chrome 扩展。 | 免费API |
| [CyberCrime-Tracker.net](https://cybercrime-tracker.net/) | 根据 CyberCrime-Tracker.net 检查主机/域或 IP 地址是否是恶意的。 | 免费API |
| [Debounce](https://debounce.io/) | 检查电子邮件是否是一次性的 | 免费API |
| [Digital Ocean Space Finder](https://www.digitalocean.com/products/spaces/) | 搜索与目标关联的潜在数字海洋空间并尝试列出其内容。 | 免费API |
| [DNS for Family](https://dnsforfamily.com/) | 检查主机是否会被 DNS for Family 阻止。 | 免费API |
| [DNSDumpster](https://dnsdumpster.com/) | 使用 HackerTarget 的 DNSDumpster 进行被动子域枚举 | 免费API |
| [DNSGrep](https://opendata.rapid7.com/) | 使用 DNSGrep API 从 Rapid7 Sonar Project 获取被动 DNS 信息。 | 免费API |
| [DroneBL](https://dronebl.org/) | 在 DroneBL 数据库中查询开放中继、开放代理、易受攻击的服务器等。 | 免费API |
| [DuckDuckGo](https://duckduckgo.com/) | 查询 DuckDuckGo 的 API 以获取有关目标的描述信息。 | 免费API |
| [EmailFormat](https://www.email-format.com/) | 在 email-format.com 上查找电子邮件地址。 | 免费API |
| [Emerging Threats](https://rules.emergingthreats.net/) | 根据 EmergingThreats.net 检查网络块或 IP 地址是否是恶意的。 | 免费API |
| [Etherscan](https://etherscan.io/) | 查询 etherscan.io 以查找已识别的以太坊钱包地址的余额。 | 免费API |
| [Flickr](https://www.flickr.com/) | 在 Flickr 中搜索与指定域相关的域、URL 和电子邮件。 | 免费API |
| [FortiGuard Antispam](https://www.fortiguard.com/) | 根据 FortiGuard Antispam 检查 IP 地址是否是恶意的。 | 免费API |
| [Github](https://github.com/) | 在 Github 上识别相关的公共代码存储库。 | 免费API |
| [Google Object Storage Finder](https://cloud.google.com/storage) | 搜索与目标关联的潜在 Google 对象存储桶并尝试列出其内容。 | 免费API |
| [Google SafeBrowsing](https://developers.google.com/safe-browsing/v4/lookup-api) | 检查该 URL 是否包含在任何安全浏览列表中。 | 免费API |
| [Gravatar](https://secure.gravatar.com/) | 从 Gravatar API 检索用户信息。 | 免费API |
| [Greensnow](https://greensnow.co/) | 根据 greensnow.co 检查网络块或 IP 地址是否是恶意的。 | 免费API |
| [grep.app](https://grep.app/) | 在 grep.app API 中搜索与指定域相关的链接和电子邮件。 | 免费API |
| [HackerOne (Unofficial)](http://www.nobbd.de/) | 检查外部漏洞扫描/报告服务 h1.nobbd.de 以查看是否列出了目标。 | 免费API |
| [HackerTarget](https://hackertarget.com/) | 在 HackerTarget.com 上搜索共享相同 IP 的主机。 | 免费API |
| [Hybrid Analysis](https://www.hybrid-analysis.com/) | 搜索与目标相关的域和 URL 的混合分析。 | 免费API |
| [Internet Storm Center](https://isc.sans.edu/) | 根据 SANS ISC 检查 IP 地址是否是恶意的。 | 免费API |
| [Keybase](https://keybase.io/) | 获取有关域名和已识别用户名的其他信息。 | 免费API |
| [LeakIX](https://leakix.net/) | 在 LeakIX 中搜索主机数据泄漏、开放端口、软件和 geoip。 | 免费API |
| [Leak-Lookup](https://leak-lookup.com/) | 搜索 Leak-Lookup.com 的违规数据库。 | 免费API |
| [Maltiverse](https://maltiverse.com/) | 获取有关涉及 IP 地址的任何恶意活动的信息 | 免费API |
| [Mnemonic PassiveDNS](https://www.mnemonic.no/) | 从 PassiveDNS.mnemonic.no 获取被动 DNS 信息。 | 免费API |
| [multiproxy.org Open Proxies](https://multiproxy.org/) | 根据 multiproxy.org 开放代理列表检查 IP 地址是否为开放代理。 | 免费API |
| [MySpace](https://myspace.com/) | 从 MySpace.com 个人资料中收集用户名和位置。 | 免费API |
| [Onion.link](https://onion.link/) | 使用 Google 自定义搜索在 Tor“洋葱城”搜索引擎中搜索提及目标域的内容。 | 免费API |
| [Onionsearchengine.com](https://as.onionsearchengine.com/) | 在 Tor onionsearchengine.com 中搜索目标域的提及。 | 免费API |
| [Open Bug Bounty](https://www.openbugbounty.org/) | 检查外部漏洞扫描/报告服务 openbugbounty.org 以查看是否列出了目标。 | 免费API |
| [OpenDNS](https://www.opendns.com/) | 检查主机是否会被 OpenDNS 阻止。 | 免费API |
| [OpenNIC DNS](https://www.opennic.org/) | 在 OpenNIC 备用 DNS 系统中解析主机名。 | 免费API |
| [OpenPhish](https://openphish.com/) | 根据 OpenPhish.com 检查主机/域是否是恶意的。 | 免费API |
| [OpenStreetMap](https://www.openstreetmap.org/) | 从 OpenStreetMap API 检索物理地址的纬度/经度坐标。 | 免费API |
| [PhishStats](https://phishstats.info/) | 根据 PhishStats 检查网络块或 IP 地址是否是恶意的。 | 免费API |
| [PhishTank](https://phishtank.com/) | 根据 PhishTank 检查主机/域是否是恶意的。 | 免费API |
| [Project Honey Pot](https://www.projecthoneypot.org/) | 在 Project Honey Pot 数据库中查询 IP 地址。 | 免费API |
| [Psbdmp](https://psbdmp.cc/) | 检查 psbdmp.cc（PasteBin 转储）是否存在可能被黑客入侵的电子邮件和域。 | 免费API |
| [PunkSpider](https://punkspider.io/) | 检查 QOMPLX punkspider.io 服务以查看目标是否被列为易受攻击的目标。 | 免费API |
| [Quad9](https://quad9.net/) | 检查主机是否会被 Quad9 DNS 阻止。 | 免费API |
| [ReverseWhois](https://www.reversewhois.io/) | 使用 reversewhois.io 反向 Whois 查询。 | 免费API |
| [RIPE](https://www.ripe.net/) | 查询 RIPE 注册表（包括 ARIN 数据）以识别网络块和其他信息。 | 免费API |
| [Robtex](https://www.robtex.com/) | 在 Robtex.com 中搜索共享相同 IP 的主机。 | 免费API |
| [searchcode](https://searchcode.com/) | 在 searchcode 中搜索提及目标域的代码存储库。 | 免费API |
| [Skymem](http://www.skymem.info/) | 在 Skymem 上查找电子邮件地址。 | 免费API |
| [SlideShare](https://www.slideshare.net/) | 从 SlideShare 个人资料中收集姓名和位置。 | 免费API |
| [SORBS](http://www.sorbs.net/) | 在 SORBS 数据库中查询开放中继、开放代理、易受攻击的服务器等。 | 免费API |
| [SpamCop](https://www.spamcop.net/) | 检查 SpamCop 数据库中是否存在网络块或 IP 地址。 | 免费API |
| [Spamhaus Zen](https://www.spamhaus.org/) | 检查网络块或 IP 地址是否在 Spamhaus Zen 数据库中。 | 免费API |
| [Steven Black Hosts](https://github.com/StevenBlack/hosts) | 根据 Steven Black Hosts 列表检查域是否是恶意的（恶意软件或广告软件）。 | 免费API |
| [Sublist3r PassiveDNS](https://api.sublist3r.com/) | 使用 Sublist3r 的 API 进行被动子域枚举 | 免费API |
| [SURBL](http://www.surbl.org/) | 检查网络块、IP 地址或域是否在 SURBL 黑名单中。 | 免费API |
| [Talos Intelligence](https://talosintelligence.com/) | 根据 TalosIntelligence 检查网络块或 IP 地址是否是恶意的。 | 免费API |
| [ThreatCrowd](https://www.threatcrowd.org/) | 从 ThreatCrowd 获取有关已识别的 IP 地址、域和电子邮件地址的信息。 | 免费API |
| [ThreatFox](https://threatfox.abuse.ch/) | 根据 ThreatFox 检查 IP 地址是否是恶意的。 | 免费API |
| [ThreatMiner](https://www.threatminer.org/) | 从 ThreatMiner 的数据库获取被动 DNS 和威胁情报的信息。 | 免费API |
| [TOR Exit Nodes](https://metrics.torproject.org/) | 检查 IP 地址或网络块是否出现在 Tor Metrics 出口节点列表中。 | 免费API |
| [TORCH](https://torchsearch.wordpress.com/) | 在 Tor“TORCH”搜索引擎中搜索目标域的提及。 | 免费API |
| [Trumail](https://trumail.io/) | 检查电子邮件是否是一次性的 | 免费API |
| [Twitter](https://twitter.com/) | 从 Twitter 个人资料中收集姓名和位置。 | 免费API |
| [UCEPROTECT](http://www.uceprotect.net/) | 检查网络块或 IP 地址是否在 UCEPROTECT 数据库中。 | 免费API |
| [URLScan.io](https://urlscan.io/) | 在 URLScan.io 缓存中搜索域信息。 | 免费API |
| [Venmo](https://venmo.com/) | 从 Venmo API 收集用户信息。 | 免费API |
| [VoIP Blacklist (VoIPBL)](https://voipbl.org/) | 根据 VoIP 黑名单 (VoIPBL) 检查 IP 地址或 netblock 是否是恶意的。 | 免费API |
| [VXVault.net](http://vxvault.net/) | 根据 VXVault.net 检查域或 IP 地址是否是恶意的。 | 免费API |
| [WiGLE](https://wigle.net/) | 查询 WiGLE 以识别附近的 WiFi 接入点。 | 免费API |
| [Wikileaks](https://wikileaks.org/) | 在 Wikileaks 中搜索域名和电子邮件地址。 | 免费API |
| [Wikipedia Edits](https://www.wikipedia.org/) | 识别使用给定 IP 地址或用户名对维基百科文章所做的编辑。 | 免费API |
| [Yandex DNS](https://yandex.com/) | 检查主机是否会被 Yandex DNS 阻止。 | 免费API |
| [Zone-H Defacement Check](https://zone-h.org/) | 检查主机名/域是否出现在 zone-h.org 的“特殊污损”RSS 提要中。 | 免费API |

<a name="zTAC1"></a>
##### Tiered API
| **Name** | **Description** | **Type** |
| --- | --- | --- |
| [AbstractAPI](https://app.abstractapi.com/) | Look up domain, phone and IP address information from AbstractAPI. | Tiered API |
| [AbuseIPDB](https://www.abuseipdb.com/) | Check if an IP address is malicious according to AbuseIPDB.com blacklist. | Tiered API |
| [Abusix Mail Intelligence](https://abusix.org/) | Check if a netblock or IP address is in the Abusix Mail Intelligence blacklist. | Tiered API |
| [AdBlock Check](https://adblockplus.org/) | Check if linked pages would be blocked by AdBlock Plus. | Tiered API |
| [AlienVault OTX](https://otx.alienvault.com/) | Obtain information from AlienVault Open Threat Exchange (OTX) | Tiered API |
| [BinaryEdge](https://www.binaryedge.io/) | Obtain information from BinaryEdge.io Internet scanning systems, including breaches, vulnerabilities, torrents and passive DNS. | Tiered API |
| [Bing (Shared IPs)](https://www.bing.com/) | Search Bing for hosts sharing the same IP. | Tiered API |
| [Bing](https://www.bing.com/) | Obtain information from bing to identify sub-domains and links. | Tiered API |
| [Bitcoin Who's Who](https://bitcoinwhoswho.com/) | Check for Bitcoin addresses against the Bitcoin Who's Who database of suspect/malicious addresses. | Tiered API |
| [BotScout](https://botscout.com/) | Searches BotScout.com's database of spam-bot IP addresses and e-mail addresses. | Tiered API |
| [BuiltWith](https://builtwith.com/) | Query BuiltWith.com's Domain API for information about your target's web technology stack, e-mail addresses and more. | Tiered API |
| [Censys](https://censys.io/) | Obtain host information from Censys.io. | Tiered API |
| [CertSpotter](https://sslmate.com/certspotter/) | Gather information about SSL certificates from SSLMate CertSpotter API. | Tiered API |
| [Clearbit](https://clearbit.com/) | Check for names, addresses, domains and more based on lookups of e-mail addresses on clearbit.com. | Tiered API |
| [Comodo Secure DNS](https://www.comodo.com/secure-dns/) | Check if a host would be blocked by Comodo Secure DNS. | Tiered API |
| [DNSDB](https://www.farsightsecurity.com/) | Query FarSight's DNSDB for historical and passive DNS data. | Tiered API |
| [EmailCrawlr](https://emailcrawlr.com/) | Search EmailCrawlr for email addresses and phone numbers associated with a domain. | Tiered API |
| [EmailRep](https://emailrep.io/) | Search EmailRep.io for email address reputation. | Tiered API |
| [Focsec](https://focsec.com/) | Look up IP address information from Focsec. | Tiered API |
| [Fraudguard](https://fraudguard.io/) | Obtain threat information from Fraudguard.io | Tiered API |
| [FullContact](https://www.fullcontact.com/) | Gather domain and e-mail information from FullContact.com API. | Tiered API |
| [FullHunt](https://fullhunt.io/) | Identify domain attack surface using FullHunt API. | Tiered API |
| [GLEIF](https://search.gleif.org/) | Look up company information from Global Legal Entity Identifier Foundation (GLEIF). | Tiered API |
| [Google Maps](https://cloud.google.com/maps-platform/) | Identifies potential physical addresses and latitude/longitude coordinates. | Tiered API |
| [Google](https://developers.google.com/custom-search) | Obtain information from the Google Custom Search API to identify sub-domains and links. | Tiered API |
| [Grayhat Warfare](https://buckets.grayhatwarfare.com/) | Find bucket names matching the keyword extracted from a domain from Grayhat API. | Tiered API |
| [GreyNoise Community](https://greynoise.io/) | Obtain IP enrichment data from GreyNoise Community API | Tiered API |
| [GreyNoise](https://greynoise.io/) | Obtain IP enrichment data from GreyNoise | Tiered API |
| [Host.io](https://host.io/) | Obtain information about domain names from host.io. | Tiered API |
| [Hunter.io](https://hunter.io/) | Check for e-mail addresses and names on hunter.io. | Tiered API |
| [Iknowwhatyoudownload.com](https://iknowwhatyoudownload.com/en/peer/) | Check iknowwhatyoudownload.com for IP addresses that have been using torrents. | Tiered API |
| [IntelligenceX](https://intelx.io/) | Obtain information from IntelligenceX about identified IP addresses, domains, e-mail addresses and phone numbers. | Tiered API |
| [ipapi.co](https://ipapi.co/) | Queries ipapi.co to identify geolocation of IP Addresses using ipapi.co API | Tiered API |
| [ipapi.com](https://ipapi.com/) | Queries ipapi.com to identify geolocation of IP Addresses using ipapi.com API | Tiered API |
| [IPInfo.io](https://ipinfo.io/) | Identifies the physical location of IP addresses identified using ipinfo.io. | Tiered API |
| [IPQualityScore](https://www.ipqualityscore.com/) | Determine if target is malicious using IPQualityScore API | Tiered API |
| [ipregistry](https://ipregistry.co/) | Query the ipregistry.co database for reputation and geo-location. | Tiered API |
| [ipstack](https://ipstack.com/) | Identifies the physical location of IP addresses identified using ipstack.com. | Tiered API |
| [JsonWHOIS.com](https://jsonwhois.com/) | Search JsonWHOIS.com for WHOIS records associated with a domain. | Tiered API |
| [Koodous](https://koodous.com/apks/) | Search Koodous for mobile apps. | Tiered API |
| [MalwarePatrol](https://www.malwarepatrol.net/) | Searches malwarepatrol.net's database of malicious URLs/IPs. | Tiered API |
| [MetaDefender](https://metadefender.opswat.com/) | Search MetaDefender API for IP address and domain IP reputation. | Tiered API |
| [NameAPI](https://www.nameapi.org/) | Check whether an email is disposable | Tiered API |
| [NetworksDB](https://networksdb.io/) | Search NetworksDB.io API for IP address and domain information. | Tiered API |
| [NeutrinoAPI](https://www.neutrinoapi.com/) | Search NeutrinoAPI for phone location information, IP address information, and host reputation. | Tiered API |
| [numverify](http://numverify.com/) | Lookup phone number location and carrier information from numverify.com. | Tiered API |
| [Onyphe](https://www.onyphe.io/) | Check Onyphe data (threat list, geo-location, pastries, vulnerabilities) about a given IP. | Tiered API |
| [OpenCorporates](https://opencorporates.com/) | Look up company information from OpenCorporates. | Tiered API |
| [PasteBin](https://pastebin.com/) | PasteBin search (via Google Search API) to identify related content. | Tiered API |
| [Pulsedive](https://pulsedive.com/) | Obtain information from Pulsedive's API. | Tiered API |
| [RiskIQ](https://community.riskiq.com/) | Obtain information from RiskIQ's (formerly PassiveTotal) Passive DNS and Passive SSL databases. | Tiered API |
| [SecurityTrails](https://securitytrails.com/) | Obtain Passive DNS and other information from SecurityTrails | Tiered API |
| [SHODAN](https://www.shodan.io/) | Obtain information from SHODAN about identified IP addresses. | Tiered API |
| [Snov](https://snov.io/) | Gather available email IDs from identified domains | Tiered API |
| [Social Media Profile Finder](https://developers.google.com/custom-search) | Tries to discover the social media profiles for human names identified. | Tiered API |
| [SpyOnWeb](http://spyonweb.com/) | Search SpyOnWeb for hosts sharing the same IP address, Google Analytics code, or Google Adsense code. | Tiered API |
| [StackOverflow](https://www.stackexchange.com/) | Search StackOverflow for any mentions of a target domain. Returns potentially related information. | Tiered API |
| [TextMagic](https://www.textmagic.com/) | Obtain phone number type from TextMagic API | Tiered API |
| [Threat Jammer](https://threatjammer.com/) | Check if an IP address is malicious according to ThreatJammer.com | Tiered API |
| [Trashpanda](https://got-hacked.wtf/) | Queries Trashpanda to gather intelligence about mentions of target in pastesites | Tiered API |
| [Twilio](https://www.twilio.com/) | Obtain information from Twilio about phone numbers. Ensure you have the Caller Name add-on installed in Twilio. | Tiered API |
| [ViewDNS.info](https://viewdns.info/) | Identify co-hosted websites and perform reverse Whois lookups using ViewDNS.info. | Tiered API |
| [VirusTotal](https://www.virustotal.com/) | Obtain information from VirusTotal about identified IP addresses. | Tiered API |
| [WhatCMS](https://whatcms.org/) | Check web technology using WhatCMS.org API. | Tiered API |
| [XForce Exchange](https://exchange.xforce.ibmcloud.com/) | Obtain IP reputation and passive DNS information from IBM X-Force Exchange. | Tiered API |
| [Zetalytics](https://zetalytics.com/) | Query the Zetalytics database for hosts on your target domain(s). | Tiered API |
| [ZoneFile.io](https://zonefiles.io/) | Search ZoneFiles.io Domain query API for domain information. | Tiered API |

<a name="sRDnE"></a>
##### Tiered API 描述翻译
| 名称 | 描述 | 类型 |
| --- | --- | --- |
| [AbstractAPI](https://app.abstractapi.com/) | 从 AbstractAPI 中查找域、电话和 IP 地址信息。 | 分层API |
| [AbuseIPDB](https://www.abuseipdb.com/) | 根据 AbuseIPDB.com 黑名单检查 IP 地址是否为恶意 IP 地址。 | 分层API |
| [Abusix Mail Intelligence](https://abusix.org/) | 检查 netblock 或 IP 地址是否在 Abusix Mail Intelligence 黑名单中。 | 分层API |
| [AdBlock Check](https://adblockplus.org/) | 检查链接页面是否会被 AdBlock Plus 拦截。 | 分层API |
| [AlienVault OTX](https://otx.alienvault.com/) | 从 AlienVault Open Threat Exchange (OTX) 获取信息 | 分层API |
| [BinaryEdge](https://www.binaryedge.io/) | 从 BinaryEdge.io 互联网扫描系统获取信息，包括漏洞、漏洞、种子和被动 DNS。 | 分层API |
| [Bing (Shared IPs)](https://www.bing.com/) | 在 Bing 中搜索共享相同 IP 的主机。 | 分层API |
| [Bing](https://www.bing.com/) | 从 bing 获取信息以识别子域和链接。 | 分层API |
| [Bitcoin Who's Who](https://bitcoinwhoswho.com/) | 根据可疑/恶意地址的比特币名人录数据库检查比特币地址。 | 分层API |
| [BotScout](https://botscout.com/) | 搜索 BotScout.com 的垃圾邮件机器人 IP 地址和电子邮件地址数据库。 | 分层API |
| [BuiltWith](https://builtwith.com/) | 查询 BuiltWith.com 的域 API，了解有关目标网络技术栈、电子邮件地址等的信息。 | 分层API |
| [Censys](https://censys.io/) | 从 Censys.io 获取主机信息。 | 分层API |
| [CertSpotter](https://sslmate.com/certspotter/) | 从 SSLMate CertSpotter API 收集有关 SSL 证书的信息。 | 分层API |
| [Clearbit](https://clearbit.com/) | 根据在 clearbit.com 上查找电子邮件地址来检查名称、地址、域等。 | 分层API |
| [Comodo Secure DNS](https://www.comodo.com/secure-dns/) | 检查主机是否会被 Comodo Secure DNS 阻止。 | 分层API |
| [DNSDB](https://www.farsightsecurity.com/) | 查询 FarSight 的 DNSDB 以获取历史和被动 DNS 数据。 | 分层API |
| [EmailCrawlr](https://emailcrawlr.com/) | 在 EmailCrawlr 中搜索与域关联的电子邮件地址和电话号码。 | 分层API |
| [EmailRep](https://emailrep.io/) | 在 EmailRep.io 中搜索电子邮件地址信誉。 | 分层API |
| [Focsec](https://focsec.com/) | 从 Focsec 查找 IP 地址信息。 | 分层API |
| [Fraudguard](https://fraudguard.io/) | 从 Fraudguard.io 获取威胁信息 | 分层API |
| [FullContact](https://www.fullcontact.com/) | 从 FullContact.com API 收集域和电子邮件信息。 | 分层API |
| [FullHunt](https://fullhunt.io/) | 使用 FullHunt API 识别域攻击面。 | 分层API |
| [GLEIF](https://search.gleif.org/) | 从 Global Legal Entity Identifier Foundation (GLEIF) 查找公司信息。 | 分层API |
| [Google Maps](https://cloud.google.com/maps-platform/) | 标识潜在的物理地址和纬度/经度坐标。 | 分层API |
| [Google](https://developers.google.com/custom-search) | 从 Google Custom Search API 获取信息以识别子域和链接。 | 分层API |
| [Grayhat Warfare](https://buckets.grayhatwarfare.com/) | 查找与从 Grayhat API 的域中提取的关键字相匹配的存储桶名称。 | 分层API |
| [GreyNoise Community](https://greynoise.io/) | 从 GreyNoise Community API 获取 IP 浓缩数据 | 分层API |
| [GreyNoise](https://greynoise.io/) | 从 GreyNoise 获取 IP 浓缩数据 | 分层API |
| [Host.io](https://host.io/) | 从 host.io 获取域名信息。 | 分层API |
| [Hunter.io](https://hunter.io/) | 在 hunter.io 上检查电子邮件地址和姓名。 | 分层API |
| [Iknowwhatyoudownload.com](https://iknowwhatyoudownload.com/en/peer/) | 检查 iknowwhatyoudownload.com 以获取一直在使用种子的 IP 地址。 | 分层API |
| [IntelligenceX](https://intelx.io/) | 从 IntelligenceX 获取有关已识别的 IP 地址、域、电子邮件地址和电话号码的信息。 | 分层API |
| [ipapi.co](https://ipapi.co/) | 使用 ipapi.co API 查询 ipapi.co 以识别 IP 地址的地理位置 | 分层API |
| [ipapi.com](https://ipapi.com/) | 使用 ipapi.com API 查询 ipapi.com 以识别 IP 地址的地理位置 | 分层API |
| [IPInfo.io](https://ipinfo.io/) | 标识使用 ipinfo.io 标识的 IP 地址的物理位置。 | 分层API |
| [IPQualityScore](https://www.ipqualityscore.com/) | 使用 IPQualityScore API 确定目标是否是恶意的 | 分层API |
| [ipregistry](https://ipregistry.co/) | 查询 ipregistry.co 数据库的信誉和地理位置。 | 分层API |
| [ipstack](https://ipstack.com/) | 标识使用 ipstack.com 标识的 IP 地址的物理位置。 | 分层API |
| [JsonWHOIS.com](https://jsonwhois.com/) | 在 JsonWHOIS.com 中搜索与域关联的 WHOIS 记录。 | 分层API |
| [Koodous](https://koodous.com/apks/) | 在 Koodous 中搜索移动应用程序。 | 分层API |
| [MalwarePatrol](https://www.malwarepatrol.net/) | 搜索 malwarepatrol.net 的恶意 URL/IP 数据库。 | 分层API |
| [MetaDefender](https://metadefender.opswat.com/) | 在 MetaDefender API 中搜索 IP 地址和域 IP 信誉。 | 分层API |
| [NameAPI](https://www.nameapi.org/) | 检查电子邮件是否是一次性的 | 分层API |
| [NetworksDB](https://networksdb.io/) | 搜索 NetworksDB.io API 以获取 IP 地址和域信息。 | 分层API |
| [NeutrinoAPI](https://www.neutrinoapi.com/) | 在 NeutrinoAPI 中搜索电话位置信息、IP 地址信息和主机信誉。 | 分层API |
| [numverify](http://numverify.com/) | 从 numverify.com 查找电话号码位置和运营商信息。 | 分层API |
| [Onyphe](https://www.onyphe.io/) | 检查有关给定 IP 的 Onyphe 数据（威胁列表、地理位置、糕点、漏洞）。 | 分层API |
| [OpenCorporates](https://opencorporates.com/) | 从 OpenCorporates 查找公司信息。 | 分层API |
| [PasteBin](https://pastebin.com/) | PasteBin 搜索（通过 Google Search API）识别相关内容。 | 分层API |
| [Pulsedive](https://pulsedive.com/) | 从 Pulsedive 的 API 获取信息。 | 分层API |
| [RiskIQ](https://community.riskiq.com/) | 从 RiskIQ（以前称为 PassiveTotal）的被动 DNS 和被动 SSL 数据库获取信息。 | 分层API |
| [SecurityTrails](https://securitytrails.com/) | 从 SecurityTrails 获取 Passive DNS 和其他信息 | 分层API |
| [SHODAN](https://www.shodan.io/) | 从 SHODAN 获取有关已识别 IP 地址的信息。 | 分层API |
| [Snov](https://snov.io/) | 从已识别的域中收集可用的电子邮件 ID | 分层API |
| [Social Media Profile Finder](https://developers.google.com/custom-search) | 尝试发现已识别的人名的社交媒体资料。 | 分层API |
| [SpyOnWeb](http://spyonweb.com/) | 在 SpyOnWeb 中搜索共享相同 IP 地址、Google Analytics 代码或 Google Adsense 代码的主机。 | 分层API |
| [StackOverflow](https://www.stackexchange.com/) | 在 StackOverflow 中搜索任何提及目标域的内容。返回可能相关的信息。 | 分层API |
| [TextMagic](https://www.textmagic.com/) | 从 TextMagic API 获取电话号码类型 | 分层API |
| [Threat Jammer](https://threatjammer.com/) | 根据 ThreatJammer.com 检查 IP 地址是否是恶意的 | 分层API |
| [Trashpanda](https://got-hacked.wtf/) | 查询 Trashpanda 以收集有关在粘贴点中提及目标的情报 | 分层API |
| [Twilio](https://www.twilio.com/) | 从 Twilio 获取有关电话号码的信息。确保您在 Twilio 中安装了 Caller Name 插件。 | 分层API |
| [ViewDNS.info](https://viewdns.info/) | 识别共同托管的网站并使用 ViewDNS.info 执行反向 Whois 查询。 | 分层API |
| [VirusTotal](https://www.virustotal.com/) | 从 VirusTotal 获取有关已识别 IP 地址的信息。 | 分层API |
| [WhatCMS](https://whatcms.org/) | 使用 WhatCMS.org API 检查网络技术。 | 分层API |
| [XForce Exchange](https://exchange.xforce.ibmcloud.com/) | 从 IBM X-Force Exchange 获取 IP 信誉和被动 DNS 信息。 | 分层API |
| [Zetalytics](https://zetalytics.com/) | 在 Zetalytics 数据库中查询目标域上的主机。 | 分层API |
| [ZoneFile.io](https://zonefiles.io/) | 在 ZoneFiles.io 域查询 API 中搜索域信息。 | 分层API |

<a name="qedu8"></a>
##### Commercial API 
| **Name** | **Description** | **Type** |
| --- | --- | --- |
| [C99](https://api.c99.nl/) | Queries the C99 API which offers various data (geo location, proxy detection, phone lookup, etc). | Commercial API |
| [Dehashed](https://www.dehashed.com/) | Gather breach data from Dehashed API. | Commercial API |
| [F-Secure Riddler.io](https://riddler.io/) | Obtain network information from F-Secure Riddler.io API. | Commercial API |
| [HaveIBeenPwned](https://haveibeenpwned.com/) | Check HaveIBeenPwned.com for hacked e-mail addresses identified in breaches. | Commercial API |
| [ProjectDiscovery Chaos](https://chaos.projectdiscovery.io/) | Search for hosts/subdomains using chaos.projectdiscovery.io | Commercial API |
| [Seon](https://seon.io/) | Queries seon.io to gather intelligence about IP Addresses, email addresses, and phone numbers | Commercial API |
| [Social Links](https://sociallinks.io/) | Queries SocialLinks.io to gather intelligence from social media platforms and dark web. | Commercial API |
| [spur.us](https://spur.us/) | Obtain information about any malicious activities involving IP addresses found | Commercial API |
| [Whoisology](https://whoisology.com/) | Reverse Whois lookups using Whoisology.com. | Commercial API |
| [Whoxy](https://www.whoxy.com/) | Reverse Whois lookups using Whoxy.com. | Commercial API |

<a name="L1cuY"></a>
##### Commercial API  描述翻译
| 名称 | 描述 | 类型 |
| --- | --- | --- |
| [C99](https://api.c99.nl/) | 查询提供各种数据（地理位置、代理检测、电话查询等）的 C99 API。 | 商业API |
| [Dehashed](https://www.dehashed.com/) | 从 Dehashed API 收集违规数据。 | 商业API |
| [F-Secure Riddler.io](https://riddler.io/) | 从 F-Secure Riddler.io API 获取网络信息。 | 商业API |
| [HaveIBeenPwned](https://haveibeenpwned.com/) | 检查 HaveIBeenPwned.com 是否存在违规行为中发现的被黑电子邮件地址。 | 商业API |
| [ProjectDiscovery Chaos](https://chaos.projectdiscovery.io/) | 使用 chaos.projectdiscovery.io 搜索主机/子域 | 商业API |
| [Seon](https://seon.io/) | 查询 seon.io 以收集有关 IP 地址、电子邮件地址和电话号码的情报 | 商业API |
| [Social Links](https://sociallinks.io/) | 查询 SocialLinks.io 以从社交媒体平台和暗网收集情报。 | 商业API |
| [spur.us](https://spur.us/) | 获取有关涉及发现的 IP 地址的任何恶意活动的信息 | 商业API |
| [Whoisology](https://whoisology.com/) | 使用 Whoisology.com 反向 Whois 查询。 | 商业API |
| [Whoxy](https://www.whoxy.com/) | 使用 Whoxy.com 反向 Whois 查询。 | 商业API |

<a name="qw1MR"></a>
## Scans (扫描列表)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29274466/1672121476186-b93512de-9e16-45f1-8c4f-d5f29a494fea.png#averageHue=%23fcfbfb&clientId=u70a9920a-b716-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=407&id=u377915a5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=407&originWidth=1389&originalType=binary&ratio=1&rotation=0&showTitle=false&size=54496&status=done&style=none&taskId=ubc47bc17-607e-4b2c-aab2-32f0ab30744&title=&width=1389)
记录着扫描的资产状态 从name点击可以查看扫描资产的详情（总览  相关  列表浏览 关系图 本次扫描设置 日志）<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/29274466/1672121600810-cb2948b5-781c-4942-9dc1-89571c069373.png#averageHue=%23fbfaf9&clientId=u70a9920a-b716-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=425&id=ue9901d0e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=717&originWidth=1236&originalType=binary&ratio=1&rotation=0&showTitle=false&size=80732&status=done&style=none&taskId=u24fe4b74-ab39-4ca1-8111-8ac900c2560&title=&width=733)![image.png](https://cdn.nlark.com/yuque/0/2022/png/29274466/1672121620341-6db3d603-abaa-4273-a4e9-bd156f5a118f.png#averageHue=%23fcfcfc&clientId=u70a9920a-b716-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=423&id=uddc6fdda&margin=%5Bobject%20Object%5D&name=image.png&originHeight=703&originWidth=1184&originalType=binary&ratio=1&rotation=0&showTitle=false&size=82967&status=done&style=none&taskId=u5e8dd081-7208-4871-a77b-536e32fcb64&title=&width=712)<br />针对与扫描结果的 列表(Browse)  关系图(Graph)  日志(log)  可以进行数据 导出，导出的格式包含CSV 和 Excel
<a name="RnkPI"></a>
## setting（设置）
包含总体的扫描设置，以及模块设置。<br />有非常的多的模块需要自己注册 填写相关个 key 才能使用<br />可以对当前设置好的模块 key 进行导出和导入
