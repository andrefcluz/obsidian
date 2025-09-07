---
title: Processo de Faturação Eletrónica
updated: 2025-08-20 15:32
created: 2019-07-23 08:58:14Z
author: André Luz
tags:
  - proj_internos-fatura_eletronica_saphety
cliente: toinovate_proj_interno
---

**Webservice**

Informação    http://doc.saphety.com/site/Help/webservices/index.html

Nome    CTMessageService - SAPHETY

Link CT Message Service (Desenvolvimento – TST)    https://www-t.netdocs.com.pt/TradeHttpDev/CTMessageService.svc

Link WSDL (Desenvolvimento – TST)    [https://www-t.netdocs.com.pt/TradeHttpDev/CTMessageService.svc?wsdl](https://www-t.netdocs.com.pt/TradeHttpDev/CTMessageService.svc%3Fwsdl)

Link WSDL Single (Desenvolvimento – TST)    [https://www-t.netdocs.com.pt/tradehttpDev/CTMessageService.svc?singleWsdl](https://www-t.netdocs.com.pt/tradehttpDev/CTMessageService.svc%3FsingleWsdl)

End-Point (Desenvolvimento – TST)    https://www-t.netdocs.com.pt/TradeHttpDev/CTMessageService.svc/ssl

Link CT Message Service (Qualidade – QA)    https://www-qa.netdocs.com.pt/tradehttpQA/CTMessageService.svc

Link WSDL (Qualidade – QA)    [https://www-qa.netdocs.com.pt/TradeHttpQa/CTMessageService.svc?wsdl](https://www-qa.netdocs.com.pt/TradeHttpQa/CTMessageService.svc%3Fwsdl)

Link WSDL Single (Qualidade – QA)    [https://www-qa.netdocs.com.pt/tradehttpQA/CTMessageService.svc?singleWsdl](https://www-qa.netdocs.com.pt/tradehttpQA/CTMessageService.svc%3FsingleWsdl)

End-Point (Qualidade – QA)    https://www-qa.netdocs.com.pt/TradeHttpQa/CTMessageService.svc/ssl

Link CT Message Service (Produção – PRD)    https://www.netdocs.com.pt/tradehttp/CTMessageService.svc

Link WSDL (Produção – PRD)    [https://ws.netdocs.com.pt/TradeHttp/CTMessageService.svc?wsdl](https://ws.netdocs.com.pt/TradeHttp/CTMessageService.svc%3Fwsdl)

Link WSDL Single (Produção – PRD)    [https://www.netdocs.com.pt/tradehttp/CTMessageService.svc?singleWsdl](https://www.netdocs.com.pt/tradehttp/CTMessageService.svc%3FsingleWsdl)

End-Point (Produção – PRD)    https://ws.netdocs.com.pt/TradeHttp/CTMessageService.svc/ssl

* * *

- Enviar Documentos

    1. ProcessMessage

- Receber Documentos

    1. GetQueuesMessageIds - Consulta o sistema para ver se existem mensagens recebidas

    2. GetMessageResultData - Descarrega todas as mensagens

    3. ChangeQueuedToProcessed - Marca as mensagem descarregadas como processadas

**Desenvolvimentos**

**Webservice/Proxy/Classe**

- ZWS_FACTELCO_IMESSAGE_SERVICE

**Métodos**

|     |     |
| --- | --- |
| Método | Função |
| PROCESS_MESSAGE | ProcessMessage |
| GET_QUEUED_MESSAGE_IDS | GetQueueMessageIds |
| GET_MESSAGE_RESULT_DATA | GetMessageResultData |
| CHANGE_QUEUED_TO_PROCESSED | ChangeQueuedToProcessed |

Cópia programa ZINVOICE_READ_SAVE da CP para a máquina da Toinovate

Tabelas Z que são lidas

- ZINVOICE_FORNCECE
- ZPM_MP5_2
- ZFILE_REJ_REASON