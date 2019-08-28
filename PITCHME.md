## IPsec for Beginners

AQUA camp 2019ss.<br />
rum and cocori

---

## Note(注意)

This slide is for explanation of classical cryptography<br />
これらは全て古典暗号技術の説明です

---

# What is IPsec？<br />(30min)
<!--
インターネットは、その特性上、途中でデータを盗み読むことも可能
だから、個人情報をそのままインターネット上で転送するのは、非常に危険な行為だといえる
なので、こうした情報はSSL（Secure Socket Layer）という方式によって暗号化してから送信することが多い。
しかし、これらはWebブラウザや電子メール・クライアントといった、特定のアプリケーションでのみ暗号化を行うものであり、汎用性がない。
そこで、アプリケーションに関係なく、すべての通信を自動的に暗号化してしまおうと考えられたのが、今回解説するIPSecである。
IPSecでは、暗号化をIP（Internet Protocol）プロトコルのレベルで行い、ホストごとにセキュリティを確保することを目的としている。
IP層レベルで自動的に暗号化された通信を行うので、上位のアプリケーションでは暗号化のことを特別に意識する必要はない。
-->

+++
### What is IPsec？(1)<br />(15min)
<!-- IPsecを説明する前に、暗号技術の基本とVPNについて確認する必要があることを伝える。-->

- Encrypted communication
	- Encryption
	- 「完全性の保証」、「認証」
- VPN

---

## Cryptosystem <br />(10min)
<!--
ここで、暗号システムには「暗号化」、「完全性の保証」、「認証」が必要であることとその理由を先に説明。
このあとで、それぞれの目的と手法について少し詳しく説明する。
さらにここで、AliceとBobの図を描いて説明
-->
![bg](https://i1.wp.com/www.mobileworldlive.com/wp-content/uploads/2016/02/shutterstock_103378880.jpg?w=500&ssl=1)

+++

### Cryptosystem

<!--
In this procedure, there are three key question.
The first question is ...
1. How to share the key?
And, second question is ...
2. How to encript and decript message?
And third one is ...
3. How to Check whether the message has been altered along the way
and whether you are communicating with the correct partner?
-->
- Key Exchange |

- Encryption |

- 「完全性の保証」、「認証」|

+++


### Encryption
<!--
順番が逆になるけど、まずは二種類の暗号化方式について話す。
理由は、鍵の管理方法のが
-->
	
- Symmetric-key cryptography

- Public-key cryptography

+++

### Encryption
<!--
<メモ>
-->

![](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/z9ws4Rp8VZHoHpnhlh9I3QhAqiIdQZg6aSOlCCu1e5SAFa.width-800.png)

The requirement is sharing secret key |
**in some way in advance** |

https://www.twilio.com/blog/what-is-public-key-cryptography

+++

### Encryption
<!--
<メモ>
-->

![](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/19DfiKodi3T25Xz7g9EDTyvF9di2SzvJo6JebRJaCN-1P_.width-808.png)

https://www.twilio.com/blog/what-is-public-key-cryptography

+++

## Public-key cryptography

**Usage**
- SSH
- TLS (HTTPS)
- Bitcoin
- PGP and GPG
- Authentication

[What is Public Key Cryptography? - Twilio](https://www.twilio.com/blog/what-is-public-key-cryptography)

+++

### Key Exchange
<!-- ここでは数学的な説明までは踏み込まないことを説明 -->

**Diffie-Hellman key exchange**



<!-- 素数の使い回しなどによって解読可能性が上がるなどの問題有り -->

+++


### 「完全性の保証」、「認証」
	
- 認証データ, MAC
- Hash function, HMAC

---

## VPN <br />(5min)
<!--
<メモ>
-->

+++


### VPN
<!--
<メモ>
-->

---

### TECHNICAL TERMS

- [HTTPS](https://ja.wikipedia.org/wiki/HTTPS)

	HTTPS自体はプロトコルではなく、SSL/TLSプロトコルによって提供されるセキュアな接続の上でHTTP通信を行うことをHTTPSと呼ぶ
	
- [SSL/TLS](https://ja.wikipedia.org/wiki/Transport_Layer_Security)

	インターネットなどのコンピュータネットワークにおいてセキュリティを要求される通信を行うためのプロトコル

+++

### TECHNICAL TERMS

- [ディフィー・ヘルマン鍵共有](https://ja.wikipedia.org/wiki/ディフィー・ヘルマン鍵共有)

	事前の秘密の共有無しに、盗聴の可能性のある通信路を使って、暗号鍵の共有を可能にする暗号プロトコル

---


### TECHNICAL TERMS

- [共通鍵暗号](https://ja.wikipedia.org/wiki/共通鍵暗号)

	暗号化と復号に同一の（共通の）鍵を用いる暗号方式

- [公開鍵暗号](https://ja.wikipedia.org/wiki/公開鍵暗号)

	暗号化と復号に別個の鍵（手順）を用い、暗号化の鍵を公開できるようにした暗号方式

+++


### TECHNICAL TERMS

- [改竄（かいざん）](https://ja.wikipedia.org/wiki/改竄)

	文書、記録等の全部又は一部が、本来なされるべきでない時期に、本来なされるべきでない形式や内容などに変更されること、すること<br />
	悪意の有無は問わない

- [デジタル署名](https://ja.wikipedia.org/wiki/デジタル署名)

	書面上の手書き署名のセキュリティ特性を模倣するために用いられる公開鍵暗号技術の一種
	[電子署名](https://ja.wikipedia.org/wiki/電子署名)とは異なる

+++

### TECHNICAL TERMS

- [VPN](https://ja.wikipedia.org/wiki/Virtual_Private_Network)

	[インターネット](https://ja.wikipedia.org/wiki/インターネット)に跨って、[プライベートネットワーク](https://ja.wikipedia.org/wiki/プライベートネットワーク)を拡張する技術、およびそのネットワークのこと


+++

### TECHNICAL TERMS

- [用語](url)

	説明

---

### Refrence So Far

- [IPsecをはじめから](https://www.infraexpert.com/study/study10.html)
	- [VPN（ Virtual Private Network ）とは](https://www.infraexpert.com/study/ipsec.html)
	- [VPN - VPNの基礎知識](https://www.infraexpert.com/study/ipsec2.html)
	- [VPN - 暗号システムの概要](https://www.infraexpert.com/study/ipsec3.html)
	- [VPN - 共通鍵暗号と公開鍵暗号](https://www.infraexpert.com/study/ipsec4.html)

- [IT管理者のためのIPSec講座](https://www.atmarkit.co.jp/ait/articles/0011/27/news001_2.html)

- [What is Public Key Cryptography? - Twilio](https://www.twilio.com/blog/what-is-public-key-cryptography)

---

## What is IPsec？(Again)
<!--
IPsecは暗号化通信を実現するための複数のプロトコルの総称
ここではモードと中核をなすいくつかのプロトコルについて紹介する
-->

- アプリケーションに関係なく、全ての通信を自動的に暗号化するためのIP Security Protocol

- VPN構築の際に利用されるもの

+++


### IPsec　<br />(15min)
<!--
<メモ>
-->

- トランスポートモード、トンネルモード
- SA
- IKE
- ESPとAH
+++

### 

---
### TECHNICAL TERM

- [通信プロトコル](https://ja.wikipedia.org/wiki/通信プロトコル)

	[ネットワーク](https://ja.wikipedia.org/wiki/コンピュータネットワーク)上での通信に関する規約を定めたもの
	
- [IP (Internet Protocol)](https://ja.wikipedia.org/wiki/Internet_Protocol)

	最も基本的な通信単位であるパケットを相手に送信するための通信プロトコル

- [IP adress](https://ja.wikipedia.org/wiki/IPアドレス)

	IPにおいてパケットを送受信する機器を判別するための番号のこと

+++

### TECHNICAL TERMS

- [IP層]()



- [OSI参照モデル](https://ja.wikipedia.org/wiki/OSI参照モデル)

	コンピュータの持つべき通信機能を階層構造に分割したモデルのこと

---

### Refrence So Far



---

### What is IPsec？(Conclusion)

- アプリケーションに関係なく、全ての通信を自動的に暗号化するためのIP Security Protocol |

- VPN構築の際に利用されるもの |

---

### Reference 
