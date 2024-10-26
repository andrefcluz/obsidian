---
title: Toinovate - Acessos
updated: 2024-01-31 14:07:20Z
created: 2023-07-20 08:11:03Z
author: André Luz
tags:
  - _fav
  - toinovate
---

## **VPNs**

|             |                                    |                                                                                                                                              |                                                       |                                                                                                                                                                                                              |
| ----------- | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Cliente** | **VPN**                            | **Configuração**                                                                                                                             | **Login**                                             | **Notas**                                                                                                                                                                                                    |
| IPL         | Windows Built-in                   | Nome: VPN IPL  <br>Servidor: [sap.vpn.net.ipl.pt:60443](http://sap.vpn.net.ipl.pt:60443)  <br>VPN Type: SSTP  <br>![image.png](image-64.png) | Username: telem-toinovate  <br>Password: 46BNDfMu77cf | Ir às definições do Windows e depois ir a:  <br>![image.png](image-65.png)  <br>Depois seguir os seguintes passos e remover o pisco "Use default gateway in remote network":  <br>![image.png](image-68.png) |
| HFF         | Windows Built-in (Toinovate)       | Nome: VPN Toinovate  <br>Servidor: [vpn.toinovate.com](http://vpn.toinovate.com)  <br>VPN Type: Automatic  <br>![image.png](image-63.png)    | Username: andre.luz  <br>Password:                    |                                                                                                                                                                                                              |
| CP          | OpenVPN GUI                        | Ficheiro ".ovpn"                                                                                                                             | NA                                                    |                                                                                                                                                                                                              |
| CHULN       | FortiClient                        | Nome: CHULN  <br>Remote Gateway: [vpn.chln.min-saude.pt](http://vpn.chln.min-saude.pt)  <br>Port: 443  <br>![image.png](image-67.png)        | Username: 96170  <br>Password:                        | **Remote Desktop Connection**  <br><br/>Computer: [vs951sta.chln.min-saude.pt](http://vs951sta.chln.min-saude.pt)  <br>Username: chln\\96170  <br>Password:                                                  |
| SMAS        | FortiClient                        | Nome: SMAS Almada  <br>Remote Gateway: [194.65.136.169](http://194.65.136.169)  <br>Port: 10443  <br>![image.png](image-66.png)              | Username: andre.luz@toinovate.com  <br>Password:      |                                                                                                                                                                                                              |
| IP          | No browser ir a:  <br>vpn.refer.pt | NA                                                                                                                                           | Username: exafluz  <br>Password:                      | **Remote Desktop Connection**  <br><br/>Computer: [RDSHOST-LX41.ip.pt](http://RDSHOST-LX41.ip.pt) ou [RDSHOST-LX42.ip.pt](http://RDSHOST-LX42.ip.pt)  <br>Username: IP\\exafluz  <br>Password:               |

## **Máquinas SAP**

|     |     |     |     |
| --- | --- | --- | --- |
| **Cliente** | **Ambiente** | **Conexão** | **User** |
| TOINOVATE | DEV | S4  <br>172.19.5.34  <br>02  <br>TS4  <br>/H/148.69.116.170/W/T0!202$ | ALUZ |
| IPL | DEV | IPL - 1 - DEV  <br>192.168.1.98  <br>00  <br>DPL | TOINOV2  <br>Benfica_2021 |
| QLD | IPL - 2 - QLD  <br>192.168.1.103  <br>00  <br>QLP | TOINOV2  <br>Benfica_2021 |     |
| PRD | IPL - 3 - PRD  <br>192.168.1.100  <br>00  <br>PRD | TOINOV2  <br>Benfica_2021 |     |
| CP  | DEV/QLD | CP - 1 - DEV/QLD  <br>sapdcp.cp.pt  <br>00  <br>CPQ | ALUZ |
| PRD | CP - 3 - PRD  <br>192.168.3.57  <br>02  <br>CPP | ALUZ |     |
| CHULN | DEV | CHLN - 1 - DEV  <br>vs345sta.chln.min-saude.pt  <br>00  <br>DEV | 96170  <br>Toin23-CHULN1 |
| QLD | CHLN - 2 - QLD  <br>vs344sta.chln.min-saude.pt  <br>00  <br>QAS | 96170  <br>Toin23-CHULN1 |     |
| PRD | CHLN - 3 - PRD (vs503sta)  <br>172.31.10.97  <br>05  <br>PRD | 96170  <br>Toin24-CHULN |     |
| EDIA | DEV | EDIA - 1 - DEV  <br>192.168.2.136  <br>00  <br>D01  <br>/H/saprouter.milestone.pt/S/3299/W/Ml5%2o1I/H/83.240.223.69/S/3299 | TALUZ |
| QLD | EDIA - 2 - QLD  <br>192.168.2.137  <br>00  <br>Q01  <br>/H/saprouter.milestone.pt/S/3299/W/Ml5%2o1I/H/83.240.223.69/S/3299 | TALUZ |     |
| PRD | EDIA - 3 - PRD  <br>10.19.8.12  <br>00  <br>P01  <br>/H/saprouter.milestone.pt/S/3299/W/Ml5%2o1I/H/83.240.223.69/S/3299 | TOINOVATE  <br>Beja_2022  <br>TOINOVATE2  <br>Beja_2022 |     |
| HFF | DEV | HFF - 1 - DEV  <br>172.16.37.25  <br>00  <br>DEV  <br>/H/62.48.168.242/S/3299 | Toinovate  <br>Lisboa_2020 |
| QLD | HFF - 2 - QLD  <br>172.16.4.67  <br>00  <br>QAS  <br>/H/62.48.168.242/S/3299 | Toinovate  <br>Lisboa_2020 |     |
| PRD | HFF - 3 - PRD  <br>172.16.4.68  <br>00  <br>PRD  <br>/H/62.48.168.242/S/3299 | Toinovate  <br>Lisboa_2020 |     |
| SMAS | DEV | ERP - 1 - DEV  <br>172.16.20.68  <br>00  <br>SND | ALUZ |
| QLD | ERP - 2 - QLD  <br>172.16.20.112  <br>00  <br>SNQ | ALUZ |     |
| PRD | ERP - 3 - PRD  <br>172.16.20.24  <br>00  <br>SNP | ALUZ |     |
| UC  | DEV | UC - 1 - DEV  <br>Belenus-dev.uc.pt  <br>00  <br>DV7 |     |

![image.png](image-69.png)