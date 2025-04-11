#### Reprodução

MD03 - Gerar ordem 
MD04 - Exibir necessidades

![[Carris 2025.02.27-20250311094457791.png]]


---
#### Leitura dos dados das requisições e pedidos

É aqui que são selecionados os dados das requisições e pedidos e no final do método foi adicionado o enhancement (Z_MRP_QUANT_REQS_Y) onde são limpos os campos KNTTP e KNTTP_DB caso tenham o valor Y (porque nesse caso as quantidades são ignoradas)

![[Carris 2025.02.27-20250227180436920.png]]

![[Carris 2025.02.27-1741714608685.png]]


---
#### Criação das ordens planeadas no MRP

Não é utilizada nenhuma BAPI, é feito um insert direto à tabela PLAF:


![[Carris 2025.02.27-20250311151929173.png]]


---
#### Permitir categoria de classificação contábil Y nas ordens planeadas

Atualmente as ordens planeadas não permitem a categoria de classificação contábil Y. Para isso tem que se mudar a parametrização dessa categoria, colocar E no estoque especial

**OME9**

![[Carris 2025.02.27-20250311154939215.png]]

![[Carris 2025.02.27-20250311162050325.png]]


---

Mensagem: 61 039

![[Pasted image 20250408084115.png]]
