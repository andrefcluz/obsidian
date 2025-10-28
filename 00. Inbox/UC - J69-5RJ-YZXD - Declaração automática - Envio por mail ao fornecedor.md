---
created: 2025-10-22T14:36
updated: 2025-10-22T15:41
cliente:
  - uc
tags:
  - uc
share_link: https://share.note.sx/7h6fgbky
share_updated: 2025-10-22T15:41:54+01:00
---
## Objetivo
Emitir automaticamente uma declaração por fornecedor e enviar por email.

O relatório S_P00_07000134 (RFIDYYWT) gera uma única declaração para todos os fornecedores, que depois tem que ser impressa e enviada por CTT.

Solução: Desenvolver programa para chamar o relatório S_P00_07000134 individualmente para cada fornecedor e depois enviar logo para o email correspondente.

## Estimativa/Passos

1. Análise/Estimativa - **8h**
2. Criar programa Z com ecrã de seleção com os parâmetros necessários do relatório standard (S_P00_07000134) - **8h**
3. Selecionar todos os fornecedores ativos para uma tabela interna - **2h**
4. Para cada um dos fornecedores da tabela interna, chamar o programa standard RFIDYYWT (S_P00_07000134), com os parâmetros necessários para gerar o PDF e depois obter o ficheiro em memória no programa desenvolvido. Ao executar o programa standard impedir que sejam exibidos popups - **24h** 
5. Opção 1 - **32h**
	1. Guardar cada PDF numa pasta no servidor - 4h
	2. Exibir uma ALV com todos os fornecedores para os quais foi gerado um PDF e adicionar uma opção para enviar os PDF por email para cada um dos fornecedores - 8h
	3. Enviar PDF para os fornecedores por email e posteriormente eliminar ficheiros da pasta do servidor - 20h
6. Opção 2 - **24h**
	1. Enviar PDF para o fornecedor por email e guardar log numa tabela interna - 16h
	2. No final da execução mostrar uma ALV com a lista de fornecedores para os quais foram enviados os ficheiros - 8h

### Desenvolvimento
Se o programa for executado em background não mostra popups e guarda o PDF numa ordem de spool. Talvez dê para fazer o submit em background e depois ler diretamente a ordem de spool e enviar o documento para o fornecedor.

Ter como base a variante MOD. 10 2025:
![[UC - J69-5RJ-YZXD - Variante base.png]]

Parâmetro fornecedor. O submit tem que ser feito uma vez para cada fornecedor com este parâmetro preenchido:
![[UC - J69-5RJ-YZXD - Campo fornecedor.png]]

Executar com estes parâmetros a vazio para impedir que sejam criadas listas no output, e sair apenas o PDF:
![[UC - J69-5RJ-YZXD - Nao exibir listas.png]]

Parâmetros a preencher para sair o PDF:
![[UC - J69-5RJ-YZXD - Opcoes de impressao.png]]


## Tratar popups
Em principio se se fizer o submit em background não será preciso lidar com estes popups.

### Seleção adicional para Espanha/Portugal
![[UC - J69-5RJ-YZXD - Popup sel adicional espanha portugal.png]]

Saltar este bloco:
![[UC - J69-5RJ-YZXD - Popup sel adicional espanha portugal - Codigo.png]]

### Popup impressão

![[UC - J69-5RJ-YZXD - Popup impressao.png]]

Impedir que entre neste IF (talvez tentar limpar o l_dialog antes de chegar a esta parte):
![[UC - J69-5RJ-YZXD - Popup impressao - Codigo.png]]


## Dados adicionais

https://chatgpt.com/c/68f8e66d-d9a8-832b-afe6-2e99dc214d21