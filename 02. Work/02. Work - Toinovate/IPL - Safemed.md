---
title: IPL - Safemed
updated: 2024-08-06 17:15:15Z
created: 2024-05-08 09:23:23Z
latitude: 38.7222524
longitude: -9.1393366
altitude: 0
tags:
  - ipl/safemed
---

https://safemed.pt/iplisboa/syncERP.asmx?wsdl


URL ambiente testes: https://safemed.pt:2087/ipl_qld

URL webservice: https://safemed.pt:2087/ipl_qld/SyncERP.asmx?wsdl

User: sap

Pass: 6Y02DL1Iq85v


Passos Safemed


1.  Enviar dados para SAFEMED
    
    1.  Criar tabelas de log
    2.  Criar MF para ler os dados
        1.  Beneficiários
        2.  Ausências
    3.  Criar programas para enviar dados para a SAFEMED
        1.   Beneficiários
        2.  Ausências
    4.  Criar cockpit para ver log dos dados enviados, com a opção de os reenviar
2.  Criar API para os serviços de informática usarem