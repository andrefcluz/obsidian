---
title: Gerfip 3.1 - Validações e substituições
updated: 2024-10-06 10:50
created: 2017-09-15 07:35:26Z
author: André Luz
tags:
  - espap
---

**RGUGBR00**
**
**
**Validações OB28 - ZPFM_1FIUE02**

1.  Por item de lançamento contabilístico, todos os lançamentos têm que ter o campo “Nº conta alternativo na empresa” preenchido (bseg-lokkt)

Z002 – Etapa 031 – msg ZFI286

2.  Os documentos financeiros têm que ter obrigatoriamente saldo 0 para contas sem letras, saldo 0 para as contas 'P' e saldo 0 para as contas 'O' para as contas POCP (bseg-hkont) num mesmo documento. Em Gerfip 31, um documento financeiro pode conter uma ou a totalidade destas combinações.

3.  Os documentos financeiros têm que ter obrigatoriamente saldo 0 para contas sem letras e saldo 0 para as contas 'S' para as contas SNC-AP (bseg-lokkt) num mesmo documento. Em Gerfip 31, um documento financeiro pode conter uma ou a totalidade destas combinações.

Z003 – Etapa 034 – Exit UZ157 – msg ZFI287

4.  As contas de PLC somente poderão ser movimentadas por tipos de documento de PLC. Para a empresa em causa e respetiva data de lançamento aceder à tabela PFM_TPPLC_LANC_N e verificar se a conta (bseg-hkont se encontra na mesma no período correspondente à data de lançamento. Caso a(s) contas se encontrem na tabela aceder à tabela PFM_TPTD e para a mesma empresa verificar se o tipo de documento existe nessa tabela. Caso não exista deve dar erro.

Z003 – Etapa 035 – Exit UZ158 – msg ZFI288

5.  Para documentos que não sejam de BL (excluir desta validação sempre que bkpf-blind esteja preenchido) e para os tipos de documento que não estejam na tabela PFM_TPTD, validar que as contas P* (bseg-hkont) só possuem classificações orçamentais dummy.

Z003 – Etapa 036 – Exit UZ159 – msg ZFI289

6. Nº conta alternativo obrigatorio

Z003 - Etapa 037 - Exit UZ160 - msg ZFI286

**Substituições OBBH - ZPFM_1FIUE01**
**
**

1. Substituição da conta reconciliação de fornecedores em documentos plc, de acordo com as seguintes regras:

               •	A substituição só deve ser executada caso a empresa esteja ativa para o Gerfip 3.1;

               •	A substituição só pode ser executada para os tipos de documento 86 (etapa ENDC) e 99 (etapa                          ENPL). Estes são documentos de PLC.

               •	Caso se verifiquem as condições anteriores deve ser substituída a conta de reconciliação de                                   fornecedor no documento (bseg-hkont) para os items de fornecedor que não possuam compromisso                   pela conta 2684500001. Adicionalmente efetuar igualmente a substituição da conta alternativa                             (bseg-lokkt) pela conta alternativa equivalente da conta 2684500001.

          Z003 - Etapa 016 - Exit UZ134