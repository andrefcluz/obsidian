---
tags:
  - ip
  - usdmt
created: 2025-01-16 09:52
updated: 2025-02-10 08:48
---
- Criar estrutura para a ALV do relatório com os seguintes campos (/USDMT/ST_OT_FI_ORC)
	- Empresa
	- Ano
	- Período
	- Item Financeiro
	- Status
	- Valor Orçamental
	- Valor BSIS Receita (esconder)
	- Valor BSIS Despesa (esconder)
	- Valor Diferença
- Adicionar opções OTR e OTD à tabela /USDMT/REGR_ZERO e parametrizar
- Relatório
	- Seleções
		- Selecionar contas na tabela /USDMT/REGR_ZERO para as opções OTD e OTR
		- Selecionar itens financeiros extra-orçamentais (FMCI - FIKRS=REF1, GJAHR=p_gjahr, FIVOR=30, STATS=X, TIPO=03)
		- Chamar MF /USDMT/FM_D_DESP_PAGAS_LIQ_TOT e /USDMT/FM_R_REC_COB_LIQ_TOT para itens selecionados
		- Chamar MF /USDMT/FM_GET_CONTA_ZERO para as contas selecionadas
	- Tratamento dados
		- Preencher tabela da ALV com os itens financeiros selecionados e montantes correspondentes, e depois ler a tabela dos valores das contas
	- Detalhe
		- Mostrar detalhe orçamental ou financeiro ao fazer duplo clique nas colunas correspondentes
	- Análise Comparativa Regras Contas
	- Lançar BL 
		- ALV principal
		- Na visão da análise comparativa (BL individual)


---


Sets Contas OT:

![[Pasted image 20240912123910.png]]


![[IP - USDMT - OT-20250121082949581.png]]


