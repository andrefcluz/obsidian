---
updated: 2025-08-08 21:36
created: 2025-08-07 09:47
---
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

  

---

  

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

