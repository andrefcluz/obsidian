---
title: Update de segmentos de ciclos de rateio em massa
updated: 2021-07-24 14:20:34Z
created: 2021-06-25 13:21:10Z
author: André Luz
tags:
  - cp
  - cp-emef
---

Programa ja existente - ZCOB2616
Tabela segmentos - T811S

Programa com ecrã de seleção:

- Empresa - Default 1000
- CSKS-KOKRS Default 1000
- Ficheiro
- Radiobutton
    - Segmentos de centro de custo - KSU2
    - Segmentos de centro de lucro - 3KE2

**Segmentos de centro de custo**

Modificar segmento se existir ou anexar se não (adicionar também descrição) - Excel

Codigo bloqueio - Excel

CABEC. SEGMENTO
Classe custo rateio - Excel
Regra emissor - "1"
Quota em % - Excel (se não tiver colocar 100 por defeito)
Radio Origens Valores reais - "X"
Regra Recetor - Excel

- Tp. Quot. Variavel - Excel

Padroniz.bases.ref.negativas - Excel

EMISSOR/RECETOR

Centro custo Emissor - CSKS-KOKRS = Ecrã seleçao + Excel-Emissores - Se encontrar preenche centro de custo com Emissores, se não encontrar preenche grupo

Classe de custo Emissor - Ir T001 apanhar o KTOPL, depois ir à CSKA com o KTOPL e Excel-"Classes  de custo emissoras" - Se existir é uma classe de custo (preenche de), senão é um grupo de classes de custo (preenche grupo)

Centro custo Recetor - Mesma logica do cnetro de custo emissor mas com campo Recetores do excel

VAL.EMISSOR
Nada

BASE REF.RECEPTORA
Tp.quant.variavel  - Excel-Tp. Quot. Variavel
Padroniz... - Excel-"Padroniz.bases.ref.negativas"

Indice Estatistico-De -> Excel-Criterio

* * *

**Segmentos de centro de lucro**

CABEC. SEGMENTO
Igual ao custo

EMISSOR/EMISSOR
Emissor
Versão - "0"
N Conta - Igual custo CSKA (set em vez de grupo)
Centro lucro - Igual ao centro custo acima mas tabela CEPC (Excel - Emissores)

Receptor
Centro lucro - Igual ao centro custo acima mas tabela CEPC (Excel-Receptores)

BASE.REF....
Igual ao do custo
+
N Conta - Ate - "ZZZZZZZZZZ"
Indice Estat - Excel-Indice Estatistico

![image.png](image-96.png)![image.png](image-94.png)

* * *

![image.png](image-95.png)

![image.png](image-93.png)