---
title: Implementação USDMT em clientes
updated: 2023-06-14 10:49:26Z
created: 2022-03-16 09:55:05Z
author: André Luz
tags:
  - usdmt
share_link: https://share.note.sx/fwfmdzqe
share_updated: 2025-03-06T11:56:09+00:00
---
[[Toinovate - USDMT]]

- [ ] **SISTEMA ORIGEM**
	- [ ] Exportar objetos da ferramenta USDMT
		- [ ] *Opção 1*
			- [ ] Fazer download do pacote /USDMT/USDMT utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)
			- [ ] Fazer download do pacote ZUSDMT_EXITS utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)
		- [ ] *Opção 2*
			- [ ] Criar OT de transporte de cópias
			- [ ] Incluir pacote /USDMT/USDMT na OT
			- [ ] Incluir pacote ZUSDMT_EXITS na OT
			- [ ] Incluir layouts da ALV da ferramenta na OT
			- [ ] Liberar OT
			- [ ] Fazer download do ficheiros DATA e COFILES
- [ ] **SISTEMA DESTINO**
	- [ ] **Ambiente de desenvolvimento**
		- [ ] Adicionar namespace /USDMT/ ao sistema de destino (SE03 -> Exibir/Modificar conjuntos de nomes)
		- [ ] Definir o namespace /USDMT/ como modificável (SE03 -> Definir opções de modificação do sistema)
		- [ ] Importar objetos da ferramenta USDMT
			- [ ] *Opção 1*
				- [ ] Fazer upload do pacote /USDMT/USDMT utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)
				- [ ] Fazer upload do pacote ZUSDMT_EXITS utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)
			- [ ] *Opção 2*
				- [ ] Carregar ficheiros DATA e COFILES
				- [ ] Importar OTs (/USDMT/USDMT e ZUSDMT_EXITS)
		- [ ] Alterar camada de transporte do pacote /USDMT/USDMT na SE21
		- [ ] Parametrizar tabelas
			- [ ] Parametrizar tabela /USDMT/ACT_FUNCT
			- [ ] *Parametrizar tabela /USDMT/FUNC_ESP*
			- [ ] *Parametrizar tabela /USDMT/AREA_FUNC*
			- [ ] Parametrizar tabela /USDMT/FM_COLS
			- [ ] Parametrizar tabela /USDMT/FORMULAS
			- [ ] Parametrizar tabela /USDMT/ALV_FIELD para DODES e DOREC
		- [ ] Criar layouts (/DODES, /DOREC, /VAL_DODES e /VAL_DOREC) para o cockpit (Funcional)
		- [ ] Criar PARAMETER ID (TPARA) com o nome /USDMT/ID_MAPA
	- [ ] **Ambiente de testes**
		- [ ] Parametrizar tabelas
			- [ ] Parametrizar tabela /USDMT/ACT_FUNCT
			- [ ] Parametrizar tabela /USDMT/REGR_ZERO (Funcional)
			- [ ] Parametrizar tabela /USDMT/CONTAS_BL (Funcional)
		- [ ] Criar layouts (/DODES, /DOREC, /VAL_DODES e /VAL_DOREC) para o cockpit (Funcional)
		- [ ] *Migrar exceções antigas para tabela nova (programa /USDMT/MIGRAR_EXCECOES)*
		- [ ] *Executar programa /USDMT/CARR_FMIFIIT_FMIOI para carregar as tabelas /USDMT/FMIOI e /USDMT/FMIFIIT e definir execução para cada 15m* 
	- [ ] **Ambiente de produção**
		- [ ] Parametrizar tabelas
			- [ ] Parametrizar tabela /USDMT/ACT_FUNCT
			- [ ] Parametrizar tabela /USDMT/REGR_ZERO (Funcional)
			- [ ] Parametrizar tabela /USDMT/CONTAS_BL (Funcional)
		- [ ] Criar layouts (/DODES, /DOREC, /VAL_DODES e /VAL_DOREC) para o cockpit (Funcional)
		- [ ] *Migrar exceções antigas para tabela nova (programa /USDMT/MIGRAR_EXCECOES)*
		- [ ] *Executar programa /USDMT/CARR_FMIFIIT_FMIOI para carregar as tabelas /USDMT/FMIOI e /USDMT/FMIFIIT e definir execução para cada 15m* 