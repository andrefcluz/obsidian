---
title: Interface da Receita Academica
updated: 2021-11-10 09:06:51Z
created: 2018-09-10 10:17:30Z
source: https://webmail.smartcloud.pt/owa/
tags:
  - ipl
---

Dúvidas

- Header-CompanyAddress -> Em SAP só é um campo com esse nome e no XML é uma estrutura
- MasterFiles-Customer-IBAN -> Falta este campo em SAP, a seguir ao SelfBillingIndicator
- SourceDocuments-WorkingDocuments-WorkDocument-PayorCustomerID -> Falta este campo em SAP, a seguir ao CustomerID
- SourceDocuments-WorkingDocuments-WorkDocument-DocumentStatus-Reason -> Falta este campo em SAP (apenas para notas de crédito)
- SourceDocuments-Payments-Payment-PaymentMethod-AdvancePaymentID -> Está na posição errada
- SourceDocuments-Payments-Payment-PaymentMethod -> Deveria ser tabela em vez de estrutura?

Em falta

- Lançar as notas de crédito, reembolsos, recebimentos e devoluções (ZFI_INTERFACE_RUN_JOB)
- Reprocessar manualmente o lançamento dos documentos que deram erro a lançar no job (ZFI_COCKPIT_CONTAB_CLS - LANCAR_DADOS)
- Criar programa que faz o lançamento dos documento que deram entrada nesse dia através do WS

* * *

User: WS_INTERFACE
Pass: interface

Webservice: zfi_web_Service_contab

**DEV 10.3.130.98 saperpdev.ipl.pt:8000**

http://saperpdev.ipl.pt:8000/sap/bc/srt/wsdl/flv_10002A111AD1/srvc_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/100/zfi_interface_contab/zfi_interface_contab?sap-client=100

Com autentificação

[http://10.3.130.98:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/100/zfi_interface_contab_auth/zfi_interface_contab_auth?sap-client=100](https://webmail.smartcloud.pt/owa/redir.aspx?C=VDsS0ID9Fpp6wn-293G52Hp0jwLQZoXHdy9TUA51yLzh4cxS53bWCA..&URL=http%3a%2f%2f10.3.130.98%3a8000%2fsap%2fbc%2fsrt%2fwsdl%2fflv_10002A111AD1%2fbndg_url%2fsap%2fbc%2fsrt%2frfc%2fsap%2fzfi_web_service_contab%2f100%2fzfi_interface_contab_auth%2fzfi_interface_contab_auth%3fsap-client%3d100)

* * *

**QAS 10.3.130.103**

http://saperpqas.ipl.pt:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/100/zfi_interface_contab/zfi_interface_contab?sap-client=100

Com autentificação

http://saperpqas.ipl.pt:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/100/zfi_interface_contab_auth/zfi_interface_contab_auth?sap-client=100

* * *

**PRD 192.168.1.100**  (10.3.130.100)

[http://SAPERPPRD:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/100/zfi_interface_contab/zfi_interface_contab?sap-client=100](http://saperpprd:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/100/zfi_interface_contab/zfi_interface_contab?sap-client=100)

[http://SAPERPPRD:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/200/zfi_interface_contab/zfi_interface_contab?sap-client=200](http://saperpprd:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/200/zfi_interface_contab/zfi_interface_contab?sap-client=200)

[http://SAPERPPRD:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/200/zfi_web_service_contab/zfi_web_service_contab?sap-client=200](http://saperpprd:8000/sap/bc/srt/wsdl/flv_10002A111AD1/bndg_url/sap/bc/srt/rfc/sap/zfi_web_service_contab/200/zfi_web_service_contab/zfi_web_service_contab?sap-client=200)

* * *

MF para fazer os lançamentos
ZFI_INTERFACE_RUN_JOB

Tipos de documento externos
FC - Fatura
DC - Nota Crédito
RC - Reembolso
RGNL - Recebimento
RGRN - Devolução

Tabelas
ZFI_ESCOLA_PAYOR - Alunos
ZFI_INTERF_CONT - Dados processamento

ZFI_COD_PROD
ZFI_COD_LANC

![img_20180910_111708.528.png](img_20180910_111708.528.png)