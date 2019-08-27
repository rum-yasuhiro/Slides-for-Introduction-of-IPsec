# Introduction of IPsec

AQUA camp 2019ss.<br />
rum and cocori

---

# What is IPsec？
<!--
インターネットは、その特性上、途中でデータを盗み読むことも可能であり、こうした個人情報をそのままインターネット上で転送するのは、非常に危険な行為だといえる
こうした情報はSSL（Secure Socket Layer）という方式によって暗号化してから送信することが多い。
しかし、これらはWebブラウザや電子メール・クライアントといった、特定のアプリケーションでのみ暗号化を行うものであり、汎用性がない。
そこで、アプリケーションに関係なく、すべての通信を自動的に暗号化してしまおうと考えられたのが、今回解説するIPSecである。
IPSecでは、暗号化をIP（Internet Protocol）プロトコルのレベルで行い、ホストごとにセキュリティを確保することを目的としている。
IP層レベルで自動的に暗号化された通信を行うので、上位のアプリケーションでは暗号化のことを特別に意識する必要はない。
-->
+++
### What is IPsec？
<!-- 
-->

- Encrypted communication
	- Encryption
	- 「完全性の保証」、「認証」
	- 共通鍵暗号、公開鍵暗号
- VPN

---

# Cryptosystem
<!-- 
-->

+++

### Cryptosystem
<!-- 
ここで、暗号システムには「暗号化」、「完全性の保証」、「認証」が必要であることとその理由を先に説明。
このあとで、それぞれの目的と手法について少し詳しく説明する。

-->
- Encryption |
	- 共通鍵暗号、公開鍵暗号
- 「完全性の保証」、「認証」|
	- HMAC、Digital signature

+++


### Encryption
<!-- 
-->

暗号化とは？目的
暗号化手法

+++

### 「完全性の保証」、「認証」
<!-- 
-->

+++


### 共通鍵暗号、公開鍵暗号
<!-- 
-->

---

# VPN
<!-- 
-->
+++


### VPN
<!-- 
-->


---

### TECHNICAL TERMS

- [通信プロトコル](https://ja.wikipedia.org/wiki/通信プロトコル)

	[ネットワーク](https://ja.wikipedia.org/wiki/コンピュータネットワーク)上での通信に関する規約を定めたもの。
	
- [IP(Internet Protocol)](https://ja.wikipedia.org/wiki/Internet_Protocol)

	最も基本的な通信単位であるパケットを相手に送信するための通信プロトコル

- [IP adress](https://ja.wikipedia.org/wiki/IPアドレス)

	IPにおいてパケットを送受信する機器を判別するための番号のこと。

+++

### TECHNICAL TERMS

- [OSI参照モデル](https://ja.wikipedia.org/wiki/OSI参照モデル)

	コンピュータの持つべき通信機能を階層構造に分割したモデルのこと。

+++

### TECHNICAL TERMS

- [VPN](https://ja.wikipedia.org/wiki/Virtual_Private_Network)

	[インターネット](https://ja.wikipedia.org/wiki/インターネット)に跨って、[プライベートネットワーク](https://ja.wikipedia.org/wiki/プライベートネットワーク)を拡張する技術、およびそのネットワークのこと。

+++

### TECHNICAL TERMS

- [デジタル署名](https://ja.wikipedia.org/wiki/デジタル署名)

	書面上の手書き署名のセキュリティ特性を模倣するために用いられる公開鍵暗号技術の一種
	- [電子署名](https://ja.wikipedia.org/wiki/電子署名)


+++

### TECHNICAL TERMS

- [用語](url)

	定義

+++

### Refrence So Far

- [IPsecをはじめから](https://www.infraexpert.com/study/study10.html)
	- [VPN（ Virtual Private Network ）とは](https://www.infraexpert.com/study/ipsec.html)
	- [VPN - VPNの基礎知識](https://www.infraexpert.com/study/ipsec2.html)
	- [VPN - 暗号システムの概要](https://www.infraexpert.com/study/ipsec3.html)
	- [VPN - 共通鍵暗号と公開鍵暗号](https://www.infraexpert.com/study/ipsec4.html)

- [IT管理者のためのIPSec講座](https://www.atmarkit.co.jp/ait/articles/0011/27/news001_2.html)


---

## What is IPsec？(まとめ)

- アプリケーションに関係なく、全ての通信を自動的に暗号化するためのIP Security Protocol |

- 主にVPN構築の際に利用されるもの |

---




## Title

+++

### トランスポートモード、トンネルモード
(OSI参照モデルについて...時間に余裕があれば)
- (SA)
- IKE
- ESPとAH
- 認証データ(「完全性の保証」、「認証」)MAC
- Hash function, HMAC
- Digital signature

---


### Reference 
IT管理者のためのIPSec講座
IPsecとは？
