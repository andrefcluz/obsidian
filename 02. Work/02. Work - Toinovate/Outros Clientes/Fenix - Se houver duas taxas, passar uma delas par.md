---
title: Fenix - Se houver duas taxas, passar uma delas para a segunda prestação das propinas
updated: 2025-08-20 15:30
created: 2020-01-28 12:05:50Z
source: https://www.saptutorial.org/change-billing-plan-data-sales-order-contract/
author: André Luz
tags:
  - iscte
cliente:
  - iscte
---

1. Na primeira prestação não considerar o valor da taxa de 200€ (ver como a identificar)

2. Ver se tem que se fazer alguma alteração no calculo do valor da segunda prestação. Diria que não porque a taxa de 200€ cabe lá

3. Alterar a categoria de item da taxa de 200€ de ZTAI para ZTXP (ver se antes ou depois de lançar a ordem de venda)

4. Após lançar a Ordem de Venda, modificar a mesma. No item da taxa de 200€, ir a programa de pagamento, remover o pisco "Prg.fat.cab." (RV60F-KFREL), e depois eliminar todas as prestações, exceto a da taxa dos 200€ e atualizar o montante para o total da taxa

BAPI_SALESORDER_CHANGE

SD_VBKD_READ_WITH_VBELN
BILLING_SCHEDULE_READ
BILLING_SCHEDULE_SAVE

lt_item_out_tx
ty_t_bapiitemex

t_item_out_tx