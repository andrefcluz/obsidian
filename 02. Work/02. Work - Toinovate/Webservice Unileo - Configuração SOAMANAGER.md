---
title: Webservice Unileo - Configuração SOAMANAGER
updated: 2024-10-06 10:50
created: 2018-03-02 10:56:16Z
source: http://uii171-vip.topo.mfap:8000/sap/bc/webdynpro/sap/appl_soap_management?sap-language=PT
author: André Luz
tags:
  - espap
  - espap-gerfip31
---

Webservices
ZWS_BTS_BASIC (pacote que tem WS do joao)

Proxy: **ZPR_WS_G31CO_UNILEO_SERVICES**

Transação: **SOAMANAGER**

Ir a:
Application and Scenario Communication -> Single Service Administration

**Search**
**Consumer Proxy | ZPR_WS_G31CO_UNILEO_SERVICES | Internal Name**

**Details of Proxy Definition **
Configurations -> Create Logical Port

- Logical Port Name: **DEFAULT**
- Logical Port Is Default: **X**
- Description: **Default**
- Configuration Type: **Manual Configuration**

**Configuration for Logical Port "DEFAULT"**

- Consumer Security
    - Não alterar nada
- Additional Information
    - Não alterar nada
- Messaging
    - Message ID Protocol: **Suppress ID Transfer**
- Transport Settings
    - URL Access Path: **UnileoServices?WSDL**
    - URL Protocol Information: **HTTPS**
    - Computer Name of Access URL
        - MFD: **dev-gseb2b.gerall.pt**
        - MFQ: **pp-gseb2b.gerall.pt**
        - MFP: **gseb2b.gerall.pt**
    - Port Number of Access URL: **443**
    - Resto não alterar nada
- Operation Specific
    - Submeter_Ficheiro
        - SOAP Action: **Submeter_Ficheiro**
    - Obter_RelatorioDoFicheiroSubmetido
        - SOAP Action: **Obter_RelatorioDoFicheiroSubmetido**
    - GetUnileoFileReport
        - SOAP Action: **GetUnileoFileReport**
    - SubmitUnileoFile
        - SOAP Action: **SubmitUnileoFile**