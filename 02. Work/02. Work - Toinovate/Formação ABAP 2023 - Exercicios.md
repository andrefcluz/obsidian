---
title: Formação ABAP 2023 - Exercicios
updated: 2024-10-06 10:50
created: 2023-09-19 03:21:19Z
author: André Luz
tags:
  - toinovate
---

## Declarar variáveis

Declarar variáveis com referência aos tipos principais, e a elementos de dados e tabelas

ZMOD3_01_VARIAVEIS
Bloco 1

## Imprimir dados da estrutura SYST

Imprimir o nome de utilizador, a data atual e a hora atual

ZMOD3_01_VARIAVEIS
Bloco 2

## Operadores

Declarar variáveis
Fazer somas, subtrações, multiplicações, divisões e o resto da divisão
Imprimir os resultados

ZMOD3_01_OPERADORES

## Condições (IF e CASE)

IF
Comparar dois parameters

- se o A for maior que o B, dá uma mensagem (MESSAGE) do tipo I a dizer que A é maior que o B e diz qual é a diferença
- se o B for maior que o A e o A for positivo, dá uma mensagem (MESSAGE) do tipo I a dizer que o B é maior que o A e diz qual é a diferença
- se não, dá uma mensagem (MESSAGE) do tipo W a dizer "Nenhuma das anteriores"

ZMOD3_01_COND_IF

CASE
Compara A e B e guarda numa variavel CHAR1 lv_maior a variável que é maior
Se lv_maior for

- igual a A, imprime A é maior
- igual a B, imprime B é maior
- qualquer outra coisa, imprime A e B são iguais

ZMOD3_01_COND_CASE

## Ciclos (LOOP, WHILE e DO)

LOOP

Percorrer a tabela GT_LFA1 para a estrutura GS_LFA1 e imprimir o valor dos campos LIFNR e STCEG

ZMOD3_01_CICLOS_LOOP

WHILE
Declarar um variável lv_contador do tipo inteiro I
Atribuir o valor 1 a essa variável

Criar um ciclo WHILE que executa até a variável lv_contador ser maior ou igual a 256

Em cada iteração imprime a variável lv_contador e depois dobra o seu valor

ZMOD3_01_CICLOS_WHILE

DO
Fazer o mesmo do exercício anterior mas usar um ciclo DO

ZMOD3_01_CICLOS_DO

## SELECT e JOIN

ZMOD3_02_SELECT

Selecionar os campos todos da tabela LFA1 onde o LAND1 é igual a 'PT'

Selecionar apenas uma linha da tabela LFA1 onde o LAND1 é igual a 'PT'

Criar tipo estruturado com os seguintes campos da LFA1

- LIFNR
- NAME1
- LAND1

Criar tabela interna e estrutura com esse tipo

Selecionar todos os registos da LFA1 para a tabela interna onde o campo ORT01 é igual a 'Lisboa' e o STRAS não está vazio

Imprimir os registos dessa tabela interna

ZMOD3_02_SELECT_JOIN

Criar tipo estruturado com os seguintes campos da LFB1

- LFB1-LIFNR
- LFB1-BUKRS
- LFB1-ERDAT
- LFB1-ERNAM
- T001-BUTXT
- T001-ORT01
- T001-LAND1

Criar tabela interna e estrutura com esse tipo

Fazer um select inner join à tabela LFB1 com a tabela T001, onde a chave externa é LFB1-BUKRS = T001-BUKRS, onde são selecionados os registos onde o BUKRS é diferente de '1000'

Imprimir os registos dessa tabela interna

## INSERT, UPDATE, MODIFY e DELETE

ZMOD3_02_DB
Bloco INSERT
Bloco UPDATE
Bloco MODIFY
Bloco DELETE

ZPESSOA##
ZPESS_FUNCAO##

Fazer INSERT, UPDATE, MODIFY e DELETE à tabela ZPESSOA##

## Rotinas

ZMOD3_03_ROTINAS

Criar rotina (FORM) SOMAR_VALORES com dois parametros de entrada (USING), as variaveis a somar e devolve o resultado da soma (CHANGING)

Fazer a chamada a essa rotina (PERFORM) e depois imprimir o resultado da soma

## Includes

Fazer exercício em conjunto onde mostro código fora de includes e vemos em que include inserimos cada bloco de código

## Eventos

Só mostrar um programa com os eventos INITIALIZE, START-OF-SELECTION e END-OF-SELECTION

## Ecrãs de seleção

ZMOD3_03_ECRA_SEL

Criar um ecrã com parameters, select-options, radiobuttons e checkbox

Usar o evento AT-SELECTION-SCREEN para esconder os parameters no ecrã quando a checkbox é piscada

## Seleção de dados

Mostrar apenas um programa já com seleções feitas (já fizeram exercícios de seleções antes)

## Tratamentos de dados

ZMOD3_03_TRATAR_DADOS

SORT e DELETE ADJANCENT DUPLICATES
Fazer APPEND de registos a uma tabela auxiliar
Modificar dados de uma tabela em LOOP usando o MODIFY
Fazer o mesmo exercício anterior mas usando FIELD-SYMBOLS

## Exibição de dados em ALV

ZMOD3_03_EXIBIR_ALV

Seleciona dados da tabela ####
Preencher a tabela FIELDCAT
Preencher a estrutura LAYOUT
Mostra os dados em ALV usando o MF 'REUSE_ALV_GRID_DISPLAY'

## Execução de programa em background

Fazer a execução do programa anterior em background e ver o resultado do JOB

## Exercício Final

ZMOD3_EXERC_FINAL

## Exercicios Extra

ZMOD3_EXTRA

ZMOD3_01_VARIAVEIS
ZMOD3_01_OPERADORES
ZMOD3_01_COND_IF
ZMOD3_01_COND_CASE
ZMOD3_01_CICLOS_LOOP
ZMOD3_01_CICLOS_WHILE
ZMOD3_01_CICLOS_DO
ZMOD3_02_SELECT
ZMOD3_02_SELECT_JOIN
ZMOD3_02_DB
ZMOD3_03_ROTINAS
ZMOD3_03_ECRA_SEL
ZMOD3_03_TRATAR_DADOS
ZMOD3_03_EXIBIR_ALV
ZMOD3_EXERC_FINAL

QF05_RANDOM_INTEGER