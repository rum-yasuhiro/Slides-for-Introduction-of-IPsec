## IPsec for Beginners

AQUA camp 2019ss.<br />
rum and cocori

---

## Note(注意)

This slide is for explanation of classical cryptography<br />
これらは全て古典暗号技術の説明です

---

## What is IPsec?(30min)
## Fun hands on! (30min)

Note:

- インターネットは、その特性上、途中でデータを盗み読むことも可能
- だから、個人情報をそのままインターネット上で転送するのは、非常に危険な行為だといえる
- なので、こうした情報はSSL（Secure Socket Layer）という方式によって暗号化してから送信することが多い。
- しかし、これらはWebブラウザや電子メール・クライアントといった、特定のアプリケーションでのみ暗号化を行うものであり、汎用性がない。
- そこで、アプリケーションに関係なく、すべての通信を自動的に暗号化してしまおうと考えられたのが、今回解説するIPSecである。
- IPSecでは、暗号化をIP（Internet Protocol）プロトコルのレベルで行い、ホストごとにセキュリティを確保することを目的としている。
- ネットワーク層レベルで自動的に暗号化された通信を行うので、上位のアプリケーションでは暗号化のことを特別に意識する必要はない。

---
### Summer vacation

![](./img/okinawa.JPG)

+++

## What is IPsec？(1)<br />(15min)
<!-- IPsecを説明する前に、暗号技術の基本とVPNについて確認する必要があることを伝える。-->

- VPN(3min)
- Encrypted communication(12min)

---


## VPN (3min)
<!--
<メモ>
-->
![](https://www.ipvanish.com/images/a/open-graph-img/why-vpn-min.jpg)

+++

### VPN(Virtual Private Network)

- Internet VPN
- IP VPN

![](./img/ipsec1vpn.jpg)
https://www.webhostingsecretrevealed.net/the-a-to-z-vpn-guide/

Note:

VPNとは仮想的なプライベートネットワーク接続のことで、セキュアな通信が可能となります。
VPNには閉じられた専用回線を用いる、IP VPNとInternetなどのpublic network上で行うInternet VPNが有ります。
Internet VPNはIP VPNと比較して、費用を削減できます。
そして、このInternet VPNを実現するセキュリティプロトコルが今回紹介する、IPsecです。

---


## Cryptosystem (12min)
<!--
ここで、暗号システムには「暗号化」、「完全性の保証」、「認証」が必要であることとその理由を先に説明。
このあとで、それぞれの目的と手法について少し詳しく説明する。
さらにここで、AliceとBobの図を描いて説明
-->
![bg](https://i1.wp.com/www.mobileworldlive.com/wp-content/uploads/2016/02/shutterstock_103378880.jpg?w=500&ssl=1)

+++

### Alphabet shift cipher

![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Caesar_cipher_left_shift_of_3.svg/1024px-Caesar_cipher_left_shift_of_3.svg.png)
https://en.wikipedia.org/wiki/Cryptography

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
- Key Exchange(鍵交換) |

- Encryption(暗号化) |

- Anthentication(認証) |

+++


### Encryption
<!--
順番が逆になるけど、まずは二種類の暗号化方式について話す。
理由は、鍵の管理方法のが
-->
	
- Symmetric-key cryptography(共通鍵暗号) |

- Public-key cryptography(公開鍵暗号) |

- [Enigma](https://en.wikipedia.org/wiki/Enigma_machine) |

- [One-time pad](https://en.wikipedia.org/wiki/One-time_pad) |

- etc... |

+++

### Encryption
<!-- <メモ> -->

![](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/z9ws4Rp8VZHoHpnhlh9I3QhAqiIdQZg6aSOlCCu1e5SAFa.width-800.png)

The requirement is sharing secret key <br />
**in some way in advance**

https://www.twilio.com/blog/what-is-public-key-cryptography

+++

### Key Exchange
<!-- ここでは数学的な説明までは踏み込まないことを説明 -->

- [**Diffie-Hellman key exchange**](https://en.wikipedia.org/wiki/Diffie–Hellman_key_exchange)

![](./img/ipsec1diffiehellman.jpg)

https://blog.trendmicro.com/trendlabs-security-intelligence/how-exploit-kit-operators-are-misusing-diffie-hellman-key-exchange/

<!-- 素数の使い回しなどによって解読可能性が上がるなどの問題有り -->


+++

### Encryption
<!-- <メモ> -->

![](./img/ipsec1publickeycryptograph.png)

https://www.twilio.com/blog/what-is-public-key-cryptography

+++


### Anthentication
	
The act of proving an assertion based on identification information

- data integrity |

+++

### Anthentication
	
- Hash function(ハッシュ関数)

![](./img/ipsec1hashfuncion.png)
https://freecontent.manning.com/cryptographic-hashes-and-bitcoin/

+++

### Anthentication

![](./img/ipsec1hashfuncion.png)
![](./img/ipsec1hashfuncion2.png)

https://freecontent.manning.com/cryptographic-hashes-and-bitcoin/

<!--
これだけではdata integrityは保証できるが、正しい相手とcommunicateできているかはどうかは保証できない
そこで、Authentificationを達成するために、HMACやdigital signatureなどの技術がhash fucntionと組み合わせて用いられる。
-->
+++

### Anthentication

**Data integrity(データの完全性)**

- MAC(メッセージ認証符号)

	Based on the Symmetric-key cryptography<br />
	
	Generate: Data + Symmetric-key<br />
	Check : Data + Symmetric-key

- Digital Signature(デジタル署名)
	
	Based on the Public-key cryptography<br />
	
	Generate: Data + Secret-key<br />
	Check : Data + Public-key

---

### TECHNICAL TERMS

<ul>	
	
<li>Internet VPN</li>

VPN using internet connection
<ul>

<li>IPsec-VPN</li>
Internet VPN using IPsec as the security protocol
	
<li>SSL-VPN</li>
Internet VPN using SSL as a security protocol
</ul>

<li>IP VPN</li>
<ul>
<li>MPLS-VPN</li>
A VPN that uses MPLS to search for route information within the private IP network of a carrier.
</ul>

</ul>

+++

### TECHNICAL TERMS

<ul>
<li>[Information Security](https://en.wikipedia.org/wiki/Information Security)</li>

Maintain the confidentiality, integrity, and availability of information (Information CIA)
	
<li>[HTTPS](https://en.wikipedia.org/wiki/HTTPS)</li>

HTTPS is not a protocol, but HTTP communication over a secure connection provided by the SSL / TLS protocol is called HTTPS
	
<li>[SSL / TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security)</li>

Protocol for performing security-required communications in computer networks such as the Internet

</ul>
+++

### TECHNICAL TERMS

<ul>
<li>[Diffie-Hellman Key Exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange)</li>

Cryptographic protocol that enables sharing of encryption keys using channels that may be wiretapped without prior secret sharing

</ul>
+++

### TECHNICAL TERMS

<ul>
<li>[Common Key Cryptography](https://en.wikipedia.org/wiki/Symmetric-key_algorithm)</li>

Encryption method that uses the same (common) key for encryption and decryption

<li>[Public Key Cryptography](https://en.wikipedia.org/wiki/Public Key Cryptography)</li>

Cryptography that uses separate keys (procedures) for encryption and decryption, and allows the encryption key to be disclosed

</ul>
+++

### TECHNICAL TERMS

<ul>

<li>Falsification</li>

Changing all or part of a document, record, etc. to a format or content that should not be done at the time when it should not be done. <br />
Whether or not malicious.

<li>[Spoofing](https://en.wikipedia.org/wiki/IP_address_spoofing)</li>

In the first place, it is necessary to check whether the data was sent from a legitimate communication partner.

+++

</ul>
### TECHNICAL TERMS

<ul>
<li>[Authentication](https://en.wikipedia.org/wiki/Authentication#Authentication)</li>

Confirming the legitimacy of the object based on the identification information

<li>[Data integrity](https://en.wikipedia.org/wiki/data integrity # information security)</li>

The data is valid without being tampered with

</ul>
+++

### TECHNICAL TERMS

<ul>
<li>[Message Authentication Code (MAC)](https://en.wikipedia.org/wiki/Message_authentication_code)</li>

Fixed-length code (bit string) for detecting whether data has been tampered with

</ul>
+++

### TECHNICAL TERMS

<ul>

<li>[HMAC](https://en.wikipedia.org/wiki/HMAC)</li>

Used with a common key.
MAC which calculates by combining hash function and common key.
	
<li>[Digital Signature](https://en.wikipedia.org/wiki/Digital Signature)</li>
Used with public key.
A type of public-key cryptography used to mimic the security characteristics of handwritten signatures on paper.
Different from [electronic signature](https://en.wikipedia.org/wiki/electronic signature).

</ul>
---

### 用語集

- インターネットVPN

	インターネット回線を利用するVPN
	- IPsec-VPN
	セキュリティプロトコルにIPsecを使用したインターネットVPNのこと
	 
	- SSL-VPN
	セキュリティプロトコルにSSLを使用したインターネットVPNのこと

- IP VPN

	- MPLS-VPN
	通信事業者のプライベートIP網内で経路情報の探索にMPLSを採用したVPNのこと

+++

### 用語集

- [情報セキュリティ](https://ja.wikipedia.org/wiki/情報セキュリティ)

	情報の機密性、完全性、可用性を維持すること(情報のCIA)

- [HTTPS](https://ja.wikipedia.org/wiki/HTTPS)

	HTTPS自体はプロトコルではなく、SSL/TLSプロトコルによって提供されるセキュアな接続の上でHTTP通信を行うことをHTTPSと呼ぶ
	
- [SSL/TLS](https://ja.wikipedia.org/wiki/Transport_Layer_Security)

	インターネットなどのコンピュータネットワークにおいてセキュリティを要求される通信を行うためのプロトコル

+++

### 用語集

- [ディフィー・ヘルマン鍵共有](https://ja.wikipedia.org/wiki/ディフィー・ヘルマン鍵共有)

	事前の秘密の共有無しに、盗聴の可能性のある通信路を使って、暗号鍵の共有を可能にする暗号プロトコル

+++

### 用語集

- [共通鍵暗号](https://ja.wikipedia.org/wiki/共通鍵暗号)

	暗号化と復号に同一の(共通の)鍵を用いる暗号方式

- [公開鍵暗号](https://ja.wikipedia.org/wiki/公開鍵暗号)

	暗号化と復号に別個の鍵(手順)を用い、暗号化の鍵を公開できるようにした暗号方式

+++

### 用語集

- [改竄（かいざん）](https://ja.wikipedia.org/wiki/改竄)

	文書、記録等の全部又は一部が、本来なされるべきでない時期に、本来なされるべきでない形式や内容などに変更されること、すること<br />
	悪意の有無は問わない
	
- [なりすまし](http://capm-network.com/?tag=認証とは#改ざんとなりすましについて)

	そもそもデータが正規の通信相手から送付されたものかどうかも確認する必要がある

+++

### 用語集

- [認証(anthentication)](https://ja.wikipedia.org/wiki/認証#Authentication)

	識別情報に基づいて対象の正当性を確認すること

- [データの完全性(data itegrity)](https://ja.wikipedia.org/wiki/データ完全性#情報セキュリティ)

	データが改ざんされることなく妥当であること

+++

### 用語集

**認証(Authentication)**

- [メッセージ認証符号 (MAC)](https://ja.wikipedia.org/wiki/メッセージ認証符号)

	データ改ざんの有無を検知するための固定長コード（ビット列）

+++

### 用語集

**認証方式**

- [HMAC](https://ja.wikipedia.org/wiki/HMAC)
	
	共通鍵と共に用いられる
	ハッシュ関数と共通鍵を組合せて計算するMACのこと

- [デジタル署名](https://ja.wikipedia.org/wiki/デジタル署名)

	公開鍵と共に用いられる
	書面上の手書き署名のセキュリティ特性を模倣するために用いられる公開鍵暗号技術の一種
	[電子署名](https://ja.wikipedia.org/wiki/電子署名)とは異なる

+++

### 用語集

- [VPN](https://ja.wikipedia.org/wiki/Virtual_Private_Network)

	[インターネット](https://ja.wikipedia.org/wiki/インターネット)に跨って、[プライベートネットワーク](https://ja.wikipedia.org/wiki/プライベートネットワーク)を拡張する技術、およびそのネットワークのこと

---

### Reference So Far

- [IPsecをはじめから](https://www.infraexpert.com/study/study10.html)
	- [VPN（ Virtual Private Network ）とは](https://www.infraexpert.com/study/ipsec.html)
	- [VPN - VPNの基礎知識](https://www.infraexpert.com/study/ipsec2.html)
	- [VPN - 暗号システムの概要](https://www.infraexpert.com/study/ipsec3.html)
	- [VPN - 共通鍵暗号と公開鍵暗号](https://www.infraexpert.com/study/ipsec4.html)

- [IT管理者のためのIPSec講座](https://www.atmarkit.co.jp/ait/articles/0011/27/news001_2.html)

+++

### Reference So Far

- [情報セキュリティ Capn Network](http://capm-network.com/?tag=%E6%83%85%E5%A0%B1%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3)
	
	- [鍵配送問題 Capn Network](http://capm-network.com/?tag=%E9%8D%B5%E9%85%8D%E9%80%81%E5%95%8F%E9%A1%8C)
	- [暗号通信 Capm Network](http://capm-network.com/?tag=%E6%9A%97%E5%8F%B7%E9%80%9A%E4%BF%A1)
	
	- [ハッシュ関数 Capn Network](http://capm-network.com/?tag=%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E9%96%A2%E6%95%B0)
	- [メッセージ認証コード Capn NetWork](http://capm-network.com/?tag=%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E8%AA%8D%E8%A8%BC%E3%82%B3%E3%83%BC%E3%83%89)
	- [デジタル署名とデジタル証明書 Capn Network](http://capm-network.com/?tag=%E3%83%87%E3%82%B8%E3%82%BF%E3%83%AB%E7%BD%B2%E5%90%8D%E3%81%A8%E3%83%87%E3%82%B8%E3%82%BF%E3%83%AB%E8%A8%BC%E6%98%8E%E6%9B%B8)

- [What is Public Key Cryptography? - Twilio](https://www.twilio.com/blog/what-is-public-key-cryptography)

---

## What is IPsec？(2)<br />(10min)

- Encpsulation
- IKE vs IPsec AH/ESP
- Basic idea of a tunnel
- SAs & rekeying

Note: 
IPsec is a generic name for several protocols for realizing encrypted communication.

From here, I will introduce Ipsec mode and some protocols that are the core of IPsec.

+++

## Encapsulation

Note: 
Before that, I want to introduce the key idea of network.

The term encapsulation is often used interchangeably with information hiding. 

and also in object-oriented programming
+++

### Encapsulation

![](./img/ipsec2encapsulation.png)
https://www.atmarkit.co.jp/ait/articles/0802/26/news135.html

Note: 

Abstracting the upper layer data by encapsulation, communication can be realized without the data of the upper layer being known to the lower layer.

+++

### Encapsulation

**IPsec Layer**
<img src="./img/ipsec2osiipseclayer.png" width=1200px />

+++

## Transport Mode
## Tunnel Mode

+++

### Transport Mode <br />Tunnel Mode

<img src="./img/ipsec2tunneltransport.png" height=500px />
https://www.cse.wustl.edu/~jain/cse571-11/ftp/l_19ips.pdf
+++

### SAs(Security Associations)

- To send and receive packets, <br />you need a SA for sending and a SA for receiving

- SA is unique for each IPsec encapsulation protocol

Note: 

Valid values are between 60 sec and 86400 sec (1 day). The default value is 3600 seconds.



+++

### SAs(Security Associations) 

IPsec performs encryption and authentication for each packet

SPI(Security poiner idex)

Note: 

SPIは暗号化通信で各パケット中に挿入され、パケット内の通信内容がどのような暗号化アルゴリズムで暗号化されたのか、どの暗号鍵を使うのかといったことを示すガイドとなる。


SPIを各パケットに挿入するのは、ホストが同時に複数の相手と暗号化通信を行うことがあるからだ。

このとき、それぞれの相手と個別にネゴシエーションを行うため、それぞれの通信で使用する暗号化アルゴリズムや暗号鍵などのSAが異なってしまう。

そのため、パケットを受信するたびに、暗号化アルゴリズムと暗号鍵を照合する必要がある。

そこで、パケット内のSPIを検索キーのように使って、必要な情報を引き出すようにしている。

SPIの値は、この値から暗号化アルゴリズムや暗号鍵が推測できないように、暗号化通信の開始時に任意のものが割り当てられ、値の意味がネゴシエーションを行った当事者者同士以外には分からないように工夫されている。

+++


### IKE(Internet Key Exchange)

<img src="./img/ike.png"  heigt=50px />

- Phase1: Generate and Exchange the key

- Phase2: Negotiate SA(Security Association)

- Start Fun IPsec!!

+++

### IKE(Internet Key Exchange)

<img src="./img/ipsec2sas.png" width=1000px />

+++

### AH and ESP
<!--
AH is used to authenticate – but not encrypt
ESP provides encryption and optional authentication
-->

<img src="./img/ipsec2ahesp.png" width=1000px />
http://jazier.blogspot.com/2015/08/ipsec-vpn-theory.html
+++

### AH and ESP
- AH(Authentication Header)

	- Authenticates whether the packet has been tampered with.
	- Packet encryption is not possible.

- ESP(Encapsulated Security Payload)

	- Authenticates whether the packet has been tampered with.
	- Encrypt the payload part of the packet.

+++

### AH and ESP

<img src="./img/ipsec2ahesp2.png" width=1000px />

+++

### SAs and Rekeying

Note: 

Each SA, whether IKE or Child, can (and should) have a lifetime. 

That lifetime can be specified in either seconds or in bytes that have been
encrypted as they pass through the tunnel. 

Once the lifetime has expired, the two gateways must create a new Child SA with new keys.

This ultimately is the heart of what we're looking for here: what is

that recommended lifetime today, and what should it be in the light of quantum computing?


---
### TECHNICAL TERM

-[Communication protocol](https://en.wikipedia.org/wiki/Communication_protocol)

Rules for communication on [Network](https://en.wikipedia.org/wiki/Computer_Network)


-[IP (Internet Protocol)](https://en.wikipedia.org/wiki/Internet_Protocol)

Communication protocol for sending packets, the most basic communication unit, to the other party

-[IP address](https://en.wikipedia.org/wiki/IP address)

A number used to identify the device that sends and receives packets in IP

+++

### TECHNICAL TERMS

-[OSI reference model](https://en.wikipedia.org/wiki/OSI reference model)

![](./img/ipsec2osimodel.jpg)

https://thetechlogy.com/osi-and-tcp-ip-model/

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

- [OSI参照モデル](https://ja.wikipedia.org/wiki/OSI参照モデル)

![](./img/ipsec2osimodel.jpg)

https://thetechlogy.com/osi-and-tcp-ip-model/
---

### Reference So Far


- [IPsec - SA ( Security Association )](https://www.infraexpert.com/study/ipsec7.html)
- [IPsec - Transport mode / Tunnel mode](https://www.infraexpert.com/study/ipsec6.html)

- [IT管理者のためのIPSec講座](https://www.atmarkit.co.jp/ait/articles/0011/27/news001_2.html)

- [Introduction to IP Security (IPSec) - Cisco](https://www.cisco.com/c/en/us/td/docs/wireless/asr_5000/20/IPSec/b_20_IPSec/b_20_IPSec_chapter_01011.pdf)

- [IPsec VPN Theory Cisco Routing & Switching and Security]( http://jazier.blogspot.com/2015/08/ipsec-vpn-theory.html)

- [データはどうやって伝わるの？](https://www.atmarkit.co.jp/ait/articles/0802/26/news135.html)

---

## Hands-on(30min)

+++

### Hands-on

[This](https://drive.google.com/open?id=15dCljthLrtDskK0bEveo6B9Y4XRDQBoQ) is a simple hands-on.  
Please access here with your keio.jp

+++

### Try VPN!

First, let's use VPN.
If you have already used VPN, you don't need to setup.  
If you don't have any VPN settings, let's make VPN settings.  

+++

### Try VPN!

Open your network preference.
![usevpn1](./img/usevpn1.png)

+++

### Try VPN!

![usevpn2](./img/usevpn2.png)

+++

### Try VPN!

![usevpn3](./img/usevpn3.png)

+++

### Try VPN!

![usevpn4](./img/usevpn4.png)

+++

### Try VPN!

![usevpn5](./img/usevpn5.png)

+++

### Try VPN!

![usevpn6](./img/usevpn6.png)

---

### What is IPsec？(Conclusion)

- IP Security Protocol for automatically encrypting all communications regardless of application |

- Used for VPN construction |

---

### Reference 


- [IPsecをはじめから](https://www.infraexpert.com/study/study10.html)
	- [VPN（ Virtual Private Network ）とは](https://www.infraexpert.com/study/ipsec.html)
	- [VPN - VPNの基礎知識](https://www.infraexpert.com/study/ipsec2.html)
	- [VPN - 暗号システムの概要](https://www.infraexpert.com/study/ipsec3.html)
	- [VPN - 共通鍵暗号と公開鍵暗号](https://www.infraexpert.com/study/ipsec4.html)

- [IT管理者のためのIPSec講座](https://www.atmarkit.co.jp/ait/articles/0011/27/news001_2.html)

+++

### Reference

- [情報セキュリティ Capn Network](http://capm-network.com/?tag=%E6%83%85%E5%A0%B1%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3)
	
	- [鍵配送問題 Capn Network](http://capm-network.com/?tag=%E9%8D%B5%E9%85%8D%E9%80%81%E5%95%8F%E9%A1%8C)
	- [暗号通信 Capm Network](http://capm-network.com/?tag=%E6%9A%97%E5%8F%B7%E9%80%9A%E4%BF%A1)
	
	- [ハッシュ関数 Capn Network](http://capm-network.com/?tag=%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E9%96%A2%E6%95%B0)
	- [メッセージ認証コード Capn NetWork](http://capm-network.com/?tag=%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E8%AA%8D%E8%A8%BC%E3%82%B3%E3%83%BC%E3%83%89)
	- [デジタル署名とデジタル証明書 Capn Network](http://capm-network.com/?tag=%E3%83%87%E3%82%B8%E3%82%BF%E3%83%AB%E7%BD%B2%E5%90%8D%E3%81%A8%E3%83%87%E3%82%B8%E3%82%BF%E3%83%AB%E8%A8%BC%E6%98%8E%E6%9B%B8)

- [What is Public Key Cryptography? - Twilio](https://www.twilio.com/blog/what-is-public-key-cryptography)

+++

### Reference

- [IPsec - SA ( Security Association )](https://www.infraexpert.com/study/ipsec7.html)
- [IPsec - Transport mode / Tunnel mode](https://www.infraexpert.com/study/ipsec6.html)

- [IT管理者のためのIPSec講座](https://www.atmarkit.co.jp/ait/articles/0011/27/news001_2.html)

- [Introduction to IP Security (IPSec) - Cisco](https://www.cisco.com/c/en/us/td/docs/wireless/asr_5000/20/IPSec/b_20_IPSec/b_20_IPSec_chapter_01011.pdf)

- [IPsec VPN Theory Cisco Routing & Switching and Security]( http://jazier.blogspot.com/2015/08/ipsec-vpn-theory.html)

- [データはどうやって伝わるの？](https://www.atmarkit.co.jp/ait/articles/0802/26/news135.html)

