---
title: CHULN - 28683 - Contrato Codificado de Valor (ZWC)
updated: 2024-10-06 10:51
created: 2022-06-23 09:54:51Z
author: André Luz
tags:
  - chuln
---

### Criar campo "Valor Fixado Bruto" no cabeçalho do contrato

Elemento de dados: ZMM_VAL_FIX_BRUTO
Estrutura: CI_EKKODB
Tela: SAPLXM06 0201
Exits: EXIT_SAPMM06E_008, EXIT_SAPMM06E_012 e EXIT_SAPMM06E_013

Criar MF onde, ao entrar no cabeçalho, se passa a EKPO, grava os dados numa tabela global e depois usa esses dados para fazer os calculos. Para fazer os calculos chama outro MF, que é chamado no EXIT EXIT_SAPMM06E_006, PAI da tela 201 e no check do EXIT EXIT_SAPMM06E_012

### Validar chave orçamental dos itens

Exit: ZXM06U43 (EXIT_SAPMM06E_012)

### Criação do cabimento/compromisso

Exit: ZXM06U22 (EXIT_SAPLEBND_002)

### Criação da nota de encomenda

BADI: ZCL_IM_ME_PROCESS_PO_CUST => IF_EX_ME_PROCESS_PO_CUST~CHECK
Exit: ZXM06U22 (EXIT_SAPLEBND_002)

Verificar valor do item do contrato e só deixa modificar na nota de encomenda se for diferente de 0

### Validação da quantidade pedida item vs quantidade item no contrato

BADI: ZCL_IM_ME_PROCESS_PO_CUST => IF_EX_ME_PROCESS_PO_CUST~CHECK

### Alterar layout da PAAD

Adobe Form: ZMM_FORM_NPD_PAAD

ZMMF_IMPRESSAO_PAAD

*
*

* * *

Objetos bloqueados

Dicionario

- CI_EKKODB

Exits

- ZXM06U43 (EXIT_SAPMM06E_012)