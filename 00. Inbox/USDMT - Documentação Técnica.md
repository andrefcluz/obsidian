---
updated: 2025-08-20 14:51
created: 2025-08-07 09:47
share_link: https://share.note.sx/497r9mhl
share_updated: 2025-08-20T14:51:48+01:00
---
```table-of-contents
title: 
style: nestedList # TOC style (nestedList|nestedOrderedList|inlineFirstLevel)
minLevel: 0 # Include headings from the specified level
maxLevel: 0 # Include headings up to the specified level
include: 
exclude: 
includeLinks: true # Make headings clickable
hideWhenEmpty: false # Hide TOC if no headings are found
debugInConsole: false # Print debug info in Obsidian console
```
# 📘 USDMT - Documentação Técnica

  
Este documento descreve tecnicamente os objetos desenvolvidos no âmbito da ferramenta USDMT (UNILEO SAP Data Management Tool).
  

---

# 🗃️ Objetos

## 🖊️ Namespace
  - /USDMT/

## 📦 Pacote
- /USDMT/USDMT

## 📂 Programas

### /USDMT/COCKPIT

  
**Descrição:** Gera um relatório ALV com os documentos de faturação do módulo SD, filtrados por cliente e data.


- **Módulo SAP:** SD – Sales and Distribution

- **Componentes utilizados:**

  - Tabelas: VBRK, VBRP

  - Classe: ZCL_FATURACAO_UTILS

  - ALV: CL_GUI_ALV_GRID

  

**Parâmetros de seleção:**

- Intervalo de clientes

- Data de faturação (DE, ATÉ)

  

**Saída:**

- ALV com totais por cliente

- Exportação para Excel


### /USDMT/DODES_DOREC_INVERT

### /USDMT/DODES_DOREC_INVERT_JOB

### /USDMT/ANALISE_COMP

### /USDMT/CHAVE_DETALHE

### /USDMT/CHAVE_JOB

### /USDMT/CARR_FMIFIIT_FMIOI

### /USDMT/DFC_FI_ORC

### /USDMT/DFC_FI_ORC_OLD

### /USDMT/RUBR_DFC_ITEM_FIN

### /USDMT/OT_FI_ORC



---
Módulos Função
/USDMT/FM_CARREG_DADOS_GLOBAIS
/USDMT/FM_CARREG_FMIOI_FMIFIIT
/USDMT/FM_DFC_SELECOES_DFC
/USDMT/FM_DFC_SELECOES_ORC
/USDMT/FM_DFC_TRATA_MATCH_DIR
/USDMT/FM_DFC_TRATA_MATCH_MAN
/USDMT/FM_D_CABIMENTOS
/USDMT/FM_D_CATIVOS
/USDMT/FM_D_CATIVOS_DESCATIVOS
/USDMT/FM_D_COMPROMISSOS
/USDMT/FM_D_COMPR_ASSUM_FUT_N1
/USDMT/FM_D_COMPR_ASSUM_FUT_N2
/USDMT/FM_D_COMPR_ASSUM_FUT_N3
/USDMT/FM_D_COMPR_ASSUM_FUT_N4
/USDMT/FM_D_COMPR_ASSUM_FUT_SE
/USDMT/FM_D_COMPR_TRANSITAR
/USDMT/FM_D_DESCATIVOS
/USDMT/FM_D_DESPESAS_PAGAR
/USDMT/FM_D_DESP_PAGAS_BRUTAS
/USDMT/FM_D_DESP_PAGAS_LIQ_AA
/USDMT/FM_D_DESP_PAGAS_LIQ_COR
/USDMT/FM_D_DESP_PAGAS_LIQ_TOT
/USDMT/FM_D_DOT_CORRIGIDAS
/USDMT/FM_D_DOT_DISPONIVEIS
/USDMT/FM_D_OBRIGACOES
/USDMT/FM_D_OBRIGACOES_TRANSIT
/USDMT/FM_D_REP_ABAT_PAG_EMIT
/USDMT/FM_D_REP_ABAT_PAG_REC
/USDMT/FM_GET_CONTA_ZERO
/USDMT/FM_LANCA_BL
/USDMT/FM_OBTEM_AREAS_FUNC
/USDMT/FM_RECL_CALL_FMBLCORR
/USDMT/FM_RECL_CALL_FMCB
/USDMT/FM_RECL_CALL_FMCD
/USDMT/FM_RECL_CALL_FMCT
/USDMT/FM_RECL_PROCESS_ALL
/USDMT/FM_RETENCOES
/USDMT/FM_RETENCOES_NAO_PAGAS
/USDMT/FM_R_LIQ_ANULADAS
/USDMT/FM_R_PREV_CORRIGIDAS
/USDMT/FM_R_PREV_POR_LIQUIDAR
/USDMT/FM_R_REC_COBR_ANT
/USDMT/FM_R_REC_COB_BRUTAS
/USDMT/FM_R_REC_COB_FINAL_PER
/USDMT/FM_R_REC_COB_LIQ_ANT
/USDMT/FM_R_REC_COB_LIQ_COR
/USDMT/FM_R_REC_COB_LIQ_TOT
/USDMT/FM_R_REC_LIQUIDADAS
/USDMT/FM_R_REEMB_EMIT
/USDMT/FM_R_REEMB_EMIT_NAO_TRA
/USDMT/FM_R_REEMB_EMIT_TRANSIT
/USDMT/FM_R_REEMB_PAGOS
/USDMT/FM_R_REEMB_PAGOS_AA
/USDMT/FM_TAB_CHECK_LOCK
/USDMT/FM_TAB_LOCK
/USDMT/FM_TAB_UNLOCK
/USDMT/FM_TRANSF_FUNDOS
/USDMT/FM_USDMT_CHECK_LOCK
/USDMT/FM_USDMT_LOCK
/USDMT/FM_USDMT_UNLOCK


 
 
 Tabelas
/USDMT/ACT_FUNCT
/USDMT/ALV_FIELD
/USDMT/AN_COMP_C
/USDMT/AREAF_XML
/USDMT/AREA_FUNC
/USDMT/CH_CRITIC
/USDMT/COLS_EXC
/USDMT/CONF_EXEC
/USDMT/CONTAS_BL
/USDMT/CONT_MAPA
/USDMT/DETALHE
/USDMT/DFC_FI_OR
/USDMT/DFC_MATCH
/USDMT/DFC_ORC
/USDMT/DFC_ORC_V
/USDMT/DIFF_JOB
/USDMT/DOCS_EXC
/USDMT/EXCECOES
/USDMT/EXEC_LOG
/USDMT/FMIFIIT
/USDMT/FMIOI
/USDMT/FM_COLS
/USDMT/FORMULAS
/USDMT/FUNC_ESP
/USDMT/IT_OR_DFC
/USDMT/LANC_BL
/USDMT/MFC_CONF
/USDMT/MFC_DATA
/USDMT/PER_FECHA
/USDMT/RECL_LOG
/USDMT/REGR_ZERO
/USDMT/R_REQ_PED
/USDMT/TAB_LOG
/USDMT/TAB_STUNR
/USDMT/VAL_DODES
/USDMT/VAL_DOREC

Mensagens
/USDMT/MC_USDMT

Transformações
/USDMT/XML_DODES
/USDMT/XML_DOREC

## 📂 Tabelas Técnicas

  

### 🔹 ZCLIENTES

  

**Finalidade:** Tabela de parametrização de clientes prioritários.

  

**Campos principais:**

- `CLIENTE` (KUNNR) – Chave primária

- `PRIORIDADE` (CHAR1) – Nível de prioridade (A, B, C)

  

---


## 📂 Tabelas Funcionais

  

### 🔹 ZCLIENTES

  

**Finalidade:** Tabela de parametrização de clientes prioritários.

  

**Campos principais:**

- `CLIENTE` (KUNNR) – Chave primária

- `PRIORIDADE` (CHAR1) – Nível de prioridade (A, B, C)

  

---

  

## 📂 Funções

  

### 🔹 ZFM_CALCULAR_TOTAL

  

**Descrição:** Calcula o total de valores com base nos documentos passados por parâmetro.

  

**Parâmetros:**

- **Importação:** `IT_DOCUMENTOS` – Tabela interna com documentos

- **Exportação:** `EV_TOTAL` – Valor total calculado

  

**Observações:**

- Utiliza a classe auxiliar `ZCL_CALCULO_TOTAL`

  

---

  

## 📂 Classes

  

### 🔹 ZCL_FATURACAO_UTILS

  

**Descrição:** Classe utilitária para tratamento de dados de faturação.

  

**Métodos principais:**

- `GET_DOCUMENTOS()` – Retorna documentos filtrados

- `CALCULAR_TOTAIS()` – Agrega valores por cliente

  

**Dependências:**

- Tabelas: VBRK, VBRP

  

---


# ⚙️ Instalação e configuração

