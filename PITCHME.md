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


- Encrypted communication
	- Encryption
	- 「完全性の保証」、「認証」
	- 共通鍵暗号、公開鍵暗号
- VPN

+++


# Cryptosystem
+++

### Cryptosystem
- Encryption
- 「完全性の保証」、「認証」
- 共通鍵暗号、公開鍵暗号

+++


### Encryption

+++


### 「完全性の保証」、「認証」

+++


### 共通鍵暗号、公開鍵暗号

+++

# VPN
<!-- 
-->
+++


### VPN



---

### TECHNICAL TERMS

- 

- [IP(Internet Protocol)](https://ja.wikipedia.org/wiki/Internet_Protocol)

	最も基本的な通信単位であるパケットを相手に送信するための通信プロトコル

- [IP adress](https://ja.wikipedia.org/wiki/IPアドレス)

	IPにおいてパケットを送受信する機器を判別するための番号のこと。

+++

### TECHNICAL TERMS

- [OSI参照モデル](https://ja.wikipedia.org/wiki/OSI参照モデル)

	コンピュータの持つべき通信機能を階層構造に分割したモデルのこと。

- [IP adress](https://ja.wikipedia.org/wiki/IPアドレス)

	IPにおいてパケットを送受信する機器を判別するための番号のこと。

- [OSI参照モデル](https://ja.wikipedia.org/wiki/OSI参照モデル)

	コンピュータの持つべき通信機能を階層構造に分割したモデルのこと。

+++

### Refrence So Far

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
