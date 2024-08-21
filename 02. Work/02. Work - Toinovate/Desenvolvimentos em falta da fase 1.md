---
title: Desenvolvimentos em falta da fase 1
updated: 2021-11-10 09:06:49Z
created: 2020-04-16 08:55:20Z
source: >-
  file:///C:/Users/andre/AppData/Local/Microsoft/Windows/INetCache/Content.MSO/5E27B048.xlsx
author: André Luz
tags:
  - cp-emef
---

**Exit - CMOD    ZMMEXIT1    EXIT_SAPLMEREQ_010    Cliente na requisição de compra**

Controlo de Disponibilidade de Exploração

Está desativado na EMEF, porque valida se a ZACKY tem a entrada  CONTROLE_DISP e em produtivo da EMEF não tem, portanto não é usado

* * *

**Exit - CMOD    ZMMEXIT7    EXIT_SAPLCORF_002    Validação do Campo "Trabalho Real" | UE Validação de datas inseridas**

**PM????**
User-Exit para Gravação IW41 - Confirmação para ordem PM entrar
Validação do Campo "Trabalho Real"
Nº de Horas não pode ser superior a 24 horas.

* * *

**Exit - CMOD    ZMMSDINT    EXIT_SAPLV50G_001    arrivals: determine destination region from delivery address**

Manipula o campo HERKR (Região de origem do material (origem Câm.Ind.e Comércio)) da tabela EIPO (Comércio exterior: export./import.: dados do item)

* * *

**Enhancement    ZME_POST_REQUISITION_EXT    Texto breve do item na requisicao**

Na IW32

Alterar o texto breve do item da requisição com a primeira linha do texto longo através da ordem (classificação F)

* * *

**Enhancement    ZMM_ENHAC_MIGO_01    Enhancement MIGO Valuation Type**

Na MIGO faz uma chamada adicional à BAPI  MB_CREATE_GOODS_MOVEMENT

* * *

**Enhancement    ZMM_PRINT_PURC_DOCS    MM - Print Purchase Documents Enh**

Envia para memória uma flag mas não tem indicação de onde é chamada depois