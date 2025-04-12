---
title: Ferramenta de reclassificação - Ajustes FMCT
updated: 2024-10-06 10:50
created: 2021-01-18 17:42:31Z
author: André Luz
tags:
  - cp
---

FMIFIIT - Quando tem linhas 57, copiar as linhas e mudar para 54 e meter o pisco em estatistico (STATS)

FMIOI -

110
1000
2020
4020013754
001
1513273

FIKRS Popup

![image.png](image-56.png)

* * *

![image_2021_01_18T17_16_47_787Z.png](image_2021_01_18T17_16_47_787Z.p)![Screenshot 2021-01-18 145727.png](Screenshot_2021-01-18_145727.png)![Screenshot 2021-01-20 095757.png](Screenshot_2021-01-20_095757.png)

Fundo
1513273 -> 1513205

- [X] Cabimento 100€	Compromisso 100€

4020013754	5020007646

- [X]  cabimento 100            compromisso 100           factura 100

4020013760                  5020007650                       2202010586

* * *

- [X]  Cabimento 100€	Compromisso 80€	Factura 70€	Pagamento 60

4020013756	5020007648	2202010584	2202405026

![image.png](image-55.png)

* * *

**Algoritmo**

Cabimentos e compromissos
1. Ver o total do documento
2. Subtrair montante da linha que está a ser lançada 0600
3. Se a diferença for diferente de 0, copiar as linhas 0600 e 0650
    1. Colocar o montante da diferença (positivo na 0600 e negativo na 0650)
    2. Colocar o pisco em estatistico
    3. Mudar  o STUNR

Faturas
1. Copiar as linhas 57
    1. Mudar de 57 para 54
    2. Colocar o pisco em estatistico
    3. Mudar STUNR