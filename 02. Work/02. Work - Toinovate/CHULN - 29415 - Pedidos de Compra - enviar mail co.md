---
title: CHULN - 29415 - Pedidos de Compra - enviar mail com as quantidades a fornecedor
updated: 2024-10-06 10:51
created: 2022-07-15 09:55:29Z
author: André Luz
tags:
  - chuln
---

Programa: ZMM_EMAIL_FORNECEDORES
Tabela: ZMM_EMAIL_PC
Estrutura: ZMM_ENVIO_EMAIL_PC_ALV

* * *

### Exemplo de envio de email no HFF

Método: zrc_utils->send_mail
Tabela mensagens email: ZRC_POOL_MAIL_B

* * *

### Teste impressão PC CHULN

ME9F

Pedido de compra: 60000607
![image.png](image-25.png)

Programa de impressão: ZSAPFM06P_PO

![image.png](image-26.png)

![image.png](image-24.png)

![image.png](image-23.png)

* * *

|     |     |
| --- | --- |
| Fornecedor | EKKO – LIFNR |
| Nome Fornecedor | LFA1 – NAME1 |
| Pedido Compra | EKPO – EBELN |
| Item | EKPO – EBELP |
| Material | EKPO – MATNR |
| Designação Material | MARA – MAKTG |
| Centro | EKPO - WERKS |
| Depósito | EKPO – LGORT |
| Consignação | EKPO – PSTYP = 2 |
| Quantidade Pedido | EKPO – MENGE |
| Unidade | EKPO – MEINS |
| Quantidade Pendente | MSEG – EBELN EPELP<br>somar MSEG – SHKZG = S<br>somar MSEG – SHKZG = H<br>Quantidade pendente = (EKPO – MENGE) - TOTAL (SHKZG = S – SHKZG = H) |

Nota Encomenda > Item > Fornecedor > Nome Fornecedor > Material > Texto Material > Quantidade > Qtd. Pendente >Un Pedido> Ctg. Item > Centro > Deposito