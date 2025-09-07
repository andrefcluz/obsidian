---
title: IP - Mapas AOR, AOD, TSC e TSR
updated: 2025-08-20 15:28
created: 2023-03-03 10:39:00Z
author: André Luz
tags:
  - ip
cliente: ip
---

Todos eles serão com base nos mapas que estão no IPL, mas não esquecer que a IP tem as suas particularidades, nomeadamente:

                - Funcional não é direto
                - Fundos comuns não são diretos e tem de se passar pela tabela que faz a repartição para obter o fundo real
                - Eles não têm o processo das transferências e subsídios montado como no IPL em que os utilizadores têm de preencher a finalidade e disposição legal no documento. Terá de ser criada uma tabela de dados para eles introduzirem por uma combinação de fundo, item financeiro e entidade (esta última opcional) as disposições legais e finalidades.

Rever:

- TSC/TSR
    - Etapas
        - TSR
            - SRCC
            - SRCD
        - TSC
            - SRCF
            - RAPF
            - SRCP
    - Já veio uma tabela do IPL com os textos das disposições legais e finalidades (ZFI_TSC_TSR_TEXT)

![image.png](image-80.png)

    - Veio outra tabela para desagregar montantes (ZFI_TSC_TSR_DESA)

![image.png](image-81.png)

    - <s>Os mapas usam o campo com nome FKBER para o fundo (e FAREA para a área funcional)</s>
    - <s>O split do fundo é feito pelo MF ZSPLIT_AMOUNT_BY_KEY e deve ter que se adicionar novos campos à tabela interna para funcionar</s>
    - <s>A determinação da área funcional é feito pela medida, que não é usado pelo mapa</s>

<s>
</s>
<s>
</s>