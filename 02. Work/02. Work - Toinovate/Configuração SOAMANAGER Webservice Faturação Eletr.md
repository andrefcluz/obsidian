---
title: Configuração SOAMANAGER Webservice Faturação Eletrónica
updated: 2021-11-10 09:03:34Z
created: 2019-07-23 09:15:40Z
author: André Luz
tags:
  - proj_internos-fatura_eletronica_saphety
---

**Segurança do consumidor**

|     |     |
| --- | --- |
| Authentication Method | wsse:Username Token |
| Add Encryption | false |
| Signature Expected | false |
| Encryption Expected | false |
| Use Timestamp | true |
| Sign Message | false |
| Secure Communications | SSL |
| PSE of Key | WSSCRT |

![](db8ae41151b402f304b8e28261f7318b.png)

* * *

**Messaging**

|     |     |
| --- | --- |
| RM Protocol | SAP RM |
| Message ID Protocol | WS-A Message ID 1.0 |
| Data transfer scope | Enhanced Data Transfer |
| Transfer protocol | Transfer via SOAP header |

![](0143e48bc26b5bc7645d7f4e52406c75.png)

* * *

**Transport Settings**

|     |     |
| --- | --- |
| URL Access Path | /TradeHttpQa/CTMessageService.svc/sslnosc |
| Computer Name of Access URL | www-qa.netdocs.com.pt |
| Port Number of Access URL | 443 |
| URL Protocol Information | HTTPS |
| Transport Binding Type | SOAP 1.2 |

![](bf79499ce662d5020b8ada1e9dd31e71.png)

* * *

**Configurações de operação**

|     |     |
| --- | --- |
| ChangeQueuedToProcessed | http://www.softlimits.com/Clarinet.Trade/IMessageService/ChangeQueuedToProcessed |
| GetQueuedMessageIds | http://www.softlimits.com/Clarinet.Trade/IMessageService/GetQueuedMessageIds |
| GetMessageResultData | http://www.softlimits.com/Clarinet.Trade/IMessageService/GetMessageResultData |
| ProcessMessage | http://www.softlimits.com/Clarinet.Trade/IMessageService/ProcessMessage |

![](d24d0f7e7dd46604de568d3a2134478d.png)