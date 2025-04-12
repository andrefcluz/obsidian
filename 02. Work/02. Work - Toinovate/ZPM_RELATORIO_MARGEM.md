---
title: ZPM_RELATORIO_MARGEM
updated: 2024-10-06 10:50
created: 2020-05-18 10:38:00Z
author: André Luz
tags:
  - cp/emef
---

1. **GET_DATA_VBRP** - Seleciona os dados dos documentos de faturamento na tabela VBRP, que não estejam estornados e cujo status para a transferência para a contabilidade (RFBSK) seja igual a C (Documento de lançamento criado). Aqui também constroi um range (R_KDAUF) com os documentos de vendas (VBRP-AUBEL) para os documentos que selecionou na VBRP que são do tipo fatura (VBTYP = M).

2. **GET_DADOS_VBFA **- Com os documentos de faturamento que selecionou no passo 1 vai à tabela VBFA, com documento precedente (VBELV)  e Categoria de documento SD subsequente (VBTYP_N) igual a O ou P, para obter os documentos subsequentes (VBELN)

3. **GET_REG_VBRP** - Com os documentos subsequentes que selecionou na VBFA no passo 2 volta a ir à tabela VBRP, e os documentos que apanha acrescenta ao que apanhou na primeira seleção à VBRP (passo 1). Adicionalmente cria um range com os números de condição dos documentos (KNUMV) que apanha nesta seleção especificamente

4. **GET_DADOS_KONV** - Vai à tabela KONV (Condições - dados de operação) com Nº condição do documento (KNUMV) igual ao range que criou no passo 3, e tipo de condição (KSCHL) igual a ZPR0 ou ZR00

5. **SET_DADOS_VENDAS **- Com os documentos que selecionou no passo 1 e 3, vai ver a correspondência nas condições (que selecionou no passo 4), e obtem os valores a exibir no relatório, e adiciona toda essa informação à tabela LTA_ALL

6. **GET_DATA_COBRB** - Com os documentos de vendas que selecionou no passo 1 (que foram incluidos no range R_KDAUF) vai à tabela das regras de repartição de normas de apropriação (COBRB), com o campo N° ordem do cliente (KDAUF) igual aos documentos de vendas e Tipo de apropriação de custos (PERBZ) igual a PER (Apropriação periódica). Assim obtem o N° objeto (OBJNR) das ordens e insere num range (R_REC_OBJNR)

7. **GET_DATA_VBAP** - Por fim, com os N° objeto que selecionou no passo 6, vai à tabela COEP (Objeto CO: partidas CO referentes ao período) selecionar os custos para as ordens, e insere-os na tabela final (GT_DATA), na linha do documento correspondente.