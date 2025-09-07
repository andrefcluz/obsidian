---
share_link: https://share.note.sx/hbuxt3zx
share_updated: 2025-04-14T12:18:47+01:00
created: 2025-04-12 09:35
updated: 2025-08-20 15:10
tags:
  - chuln
cliente:
  - chuln
---
O objetivo do relatório é permitir visualizar o stock e valores desagregado por depósito, num determina intervalo de datas. O SAP de forma standard só permite fazer isso para a data atual, ou então para um intervalo de datas, mas não é desagregado por depósito. 

#### Parâmetros e seleção (SELECT-OPTIONS):
- SO_BUDAT - Data de lançamento - Tipo BUDAT - Obrigatório
- SO_MATNR - Material - Tipo MATNR
- SO_WERKS - Centro - Tipo WERKS_D - Obrigatório
- SO_LGORT - Depósito - Tipo LGORT_D

#### Seleções:

 1. Começamos por obter o stock e valor atual do centro. Para isso vamos à tabela MBEW com o material (MATNR = SO_MATNR) e o centro (BWKEY = SO_WERKS). Gravamos os dados numa tabela interna GT_MBEW.
 2. Depois temos que obter o stock atual para cada depósito. Para isso vamos à tabela MARD com o material (MATNR = SO_MATNR) e centro (WERKS = SO_WERKS). Gravamos os dados numa tabela interna GT_MARD. 
	 1. Aqui só queremos ficar com um registo para cada combinação MATNR/WERKS/LGORT, o que tiver o ano (LFGJA) mais recente. Por isso temos que eliminar todos os outros registos. Para isso após selecionar tudo, e de seguida fazemos uma ordenação à tabela interna GT_MARD por MATNR (crescente), WERKS (crescente), LGORT (crescente) e LFGJA (decrescente):
	    
	    `SORT GT_MARD BY MATNR WERKS LGORT LFGJA DESCENDING.`
	    
	    E depois, com os dados ordenados vamos eliminar os duplicados. Isso mantém apenas o primeiro registo de dados duplicados. Como estão ordenados pelo ano de forma decrescente, temos a garantia que o registo que fica é o mais recente:
	    
	    `DELETE ADJACENT DUPLICATES FROM GT_MARD COMPARING MATNR WERKS LGORT.`
	    
3. De seguida precisamos de obter todos os movimentos que foram feitos desde a data de inicio de seleção do relatório, até hoje, ou seja, entre SO_BUDAT-LOW e SY-DATUM. Para isso vamos à MSEG com o data de lançamento (BUDAT_MKPF entre SO_BUDAT-LOW e SY-DATUM), material (MATNR = SO_MATNR) e centro (WERKS = SO_WERKS). Gravamos os dados numa tabela interna GT_MSEG. 

#### Tratamento dos dados

1. a


---

![[CHULN - PP5-BQA-76ME - 215004 Existências 2025-04-14 09.52.10.excalidraw.svg]]
%%[[CHULN - PP5-BQA-76ME - 215004 Existências 2025-04-14 09.52.10.excalidraw.md|🖋 Edit in Excalidraw]]%%


Objetivo: Saber o stock e valor de cada material por deposito numa data especifica

O que temos?
- Stock e valor atual de cada material por centro (MBEW)
- Stock atual de cada material por deposito (MARD)
- Movimentos (quantidade e valor) feitos para cada material por deposito/centro por data (MSEG)

Como é que calculamos o stock de um material para um deposito para uma data especifica?
- Ler o stock atual (MARD)
- Ler os movimentos entre essa data e a data atual (MSEG)
- Subtrair/somar o stock de todos os movimentos ao stock atual

Como é que calculamos o valor de um material para um deposito para uma data especifica?
- Ler valor atual do centro (MBEW)
- Ler todos os movimentos feitos para aquele centro a partir da data (movimentos de todos os depósitos do centro) (MSEG)
- Subtrair/somar o valor de todos os movimentos ao valor atual do centro
- Ficamos com o valor do centro para aquela data (Sabemos que o stock e valor do centro é a soma do stock e valor de todos os depósitos daquele centro)
	- Valor do material por centro para a data
	- Stock do material por centro para a data
	- Stock do material por deposito para a data
	- Valor do material por deposito para a data = ( {Valor do material por centro para a data} * {Stock do material por deposito para a data} ) / {Stock do material por centro para a data}



--- 

##### Teste MB5B

![[Untitled 2-1742537768501.png]]


![[Untitled 2-1742537759206.png]]
