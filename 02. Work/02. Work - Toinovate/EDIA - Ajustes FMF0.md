---
title: EDIA - Ajustes FMF0
updated: 2024-10-06 10:51
created: 2022-05-26 14:48:46Z
author: André Luz
tags:
  - edia
---

|     |     |
| --- | --- |
| Fatura | 2200000020 |
| Pagamento | 9400000021 |
| Estorno Pagamento | 9400000022 |

1. BSE_CLR com BUKRS, BELNR e GJAHR com os dados da fatura

2. Se apanhar alguma coisa, pega nos dados do pagamento (BUKRS_CLR, BELNR_CLR e GJAHR_CLR) e vai à BSEG ver se está estornado

3. BUKRS, BELNR e GAJHR igual aos dados do pagamento e KOART igual a K
4. Se AUGBL e AUGDT estiverem preenchidos, usar o AUGDT na FMF0

![image.png](image-40.png)

Faz no fim da rotina se a transação for FMF0 e o parametro I_GET_ALL estiver vazio

Faz um READ TABLE à tabela G_T_PSTDAT para um field symbol, preenche a data com o AUGDT da BSEG e determina o ano e periodo como o standard faz