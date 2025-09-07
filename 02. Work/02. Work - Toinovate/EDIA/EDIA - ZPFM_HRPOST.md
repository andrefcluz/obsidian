---
title: EDIA - ZPFM_HRPOST
updated: 2025-08-20 15:27
created: 2021-12-22 10:47:26Z
author: André Luz
tags:
  - edia
cliente: edia
---

Cópia do programa PFM_RPCIPE00 para ZPFM_RPCIPE00

* * *

## Includes substituidos no programa

|     |     |     |
| --- | --- | --- |
| PFM_RPCIPE0R | ZPFM_RPCIPE0R | Copiado como estava no IPL |
| PFM_RPCIPE0F | ZPFM_RPCIPE0F | Copiado como estava no IPL |
| PFM_RPCIPE0R_STD | ZPFM_RPCIPE0R_STD | Não estava no IPL - Foi copiado porque no IPL o standard foi martelado para passar mais um parametro (c0) na chamada à rotina CALL_USER_EXIT_FILL que está declarada no include ZPFM_RPCIPE0R |
| PFM_RPCIPE0X_STD | ZPFM_RPCIPE0X_STD | Não estava no IPL - Foi copiado porque no IPL o standard foi martelado para passar mais um parametro (c0) na chamada à rotina CALL_USER_EXIT_FILL que está declarada no include ZPFM_RPCIPE0R |

* * *

## Outros objetos criados/copiados que são chamados no programa Z

### MF

|     |     |     |
| --- | --- | --- |
| ZPFMX_RPCIPE0_002 | Chamado no include ZPFM_RPCIPE0R | Valida cabimento |
| ZHRPP_TRANSLATE_FICO | Chamado no include ZPFM_RPCIPE0F | "Transferir FI / CO: converter material de lançamento de RH em documentos RWIN" |
| ZHRPP_CREATE_POSTING_DOCUMENTS | Chamado no MF ZHRPP_TRANSLATE_FICO | Faz o mesmo do standard mas no final insere registos na tabela PPDIT |

### Tabelas

|     |     |
| --- | --- |
| ZPFM_HR30 | Atribuição fundos  Centros Financeiros cópia tabela PFM_HR30 |
| ZPFM_HR60 | Chave Orçamental das RNAPs |
| ZHR_CONTABILIZA | Tabela de Parametrização para Contabilização |

* * *

## Codigo hardcoded

![image.png](image-52.png)![image.png](image-51.png)![image.png](image-54.png)![image.png](image-53.png)![image.png](image-50.png)