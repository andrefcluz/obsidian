---
title: CHULN - IDoc fica sempre com o mesma localização (GLN)
updated: 2025-08-20 15:26
created: 2023-01-24 16:50:42Z
author: André Luz
tags:
  - chuln
cliente: chuln
---

![image.png](image-6.png)

- Atualmente lê o campo GLN (ILNNR no segmento E1EDKA1) com base na tabela EANC_GLN_MAPP, que só permite ter um GLN configurado por centro
- A solução é substituir esse campo no exit EXIT_SAPLEINM_002 (chamado na linha 451 do print). Colocar código dentro do IF, no sítio indicado no print abaixo

![image.png](image-5.png)

    - Nesse momento o IDOC já tem o segmento EIEDKA1, é só alterar o valor do campo ILNNR

        1. Criar tabela de parametrização com centro (WERKS), tipo de material (MTART) e localização (ILNNR) (GLN)

        2. Ler segmento E1EDK01 na tabela interna INT_EDIDD, e obter o número da nota de encomenda

        3. Com a nota de encomenda ir à tabela EKPO ler o primeiro registo não eliminado (LOEKZ <> 'L')

        4. Com o material (MATNR) da EKPO ir à tabela MARA ler o tipo de material (MTART)

        5. Ler segmento E1EDKA1, com field-symbols, obter o centro

        6. Ler a tabela criada no ponto 1 com o centro e tipo de material, para obter a localização

        7. Se sy-subrc == 0, no field-symbols substituir o campo ILNNR com o que estiver na tabela