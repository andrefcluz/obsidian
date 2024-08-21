---
title: CP - MODULA
updated: 2024-05-26 07:41:21Z
created: 2023-11-22 14:50:11Z
latitude: 38.72225240
longitude: -9.13933660
altitude: 0.0000
tags:
  - cp
---

## Tarefas após transporte

- [ ] Parametrizar tabela ZMOD_API_DATA em PRD
- [ ] Remover parametrização da tabela ZMOD_API_DATA em QLD

&nbsp;

* * *

&nbsp;

\*\*Z_AL_TESTE_INT_MOV_MODULA\*\*

&nbsp;

Acessos plataforma MODULA

USER: ADVANCED  
PASS: SYSTEM08

&nbsp;

&nbsp;

[Modula-soapui-project.xml](../_resources/Modula-soapui-project.xml)

![6782eab4de451325cb87d800318a0bc5.png](../_resources/6782eab4de451325cb87d800318a0bc5.png)

Teste comunicações em SAP  
Programa: Z_HTTP_REQ_AL

&nbsp;

* * *

JOB  
MANUAL  
REPROC

@08@ / @5B@ --> Green Light  
@09@ / @5D@ --> Yellow Light  
@0A@ / @5C@ --> Red Light

* * *

## Materiais

- [x] Criar tabelas de log
    - [x] Tabela de log - ZMOD_LOG_E_MAT
    - [x] Tabela de detalhe - ZMOD_LOG_D_E_MAT
- [x] Criar estrutura do JSON
    - [x] Envio - ZMOD_ST_JSON_E_MAT
    - [x] Receção
- [x] Criar método para envio dos materiais
- [x] Criar programa que vai correr em job e envia os materiais daquele dia
- [x] Criar cockpit

&nbsp;

&nbsp;

- [ ] CFG-IMP-ARTICOLI
    - [x] ZMOD_ST_JSON_E_MAT
    - [x] Método EXPORTA_MATERIAIS
    - [x] ZMOD_LOG_D_E_MAT
    - [x] Programa ZMOD_EXP_MATERIAIS
- [ ]  CFG-IMP-ORDINI
    - [x] ZMOD_ST_JSON_E_ORD
    - [x] Método EXPORTA_ORDENS
    - [x] ZMOD_LOG_E_ORD
    - [x] ZMOD_LOG_E_ORD_I
    - [x] ZMOD_LOG_D_E_ORD
    - [ ] Programa ZMOD_EXP_ORDENS
- [ ] CFG-IMP-SOTTOCODICI
    - [x] ZMOD_ST_JSON_E_ORD_PM
    - [x] Método EXPORTA_ORDENS_PM
    - [x] ZMOD_LOG_E_OPM
    - [x] ZMOD_LOG_D_E_OPM
    - [ ] Programa ZMOD_EXP_ORDENS_PM
- [ ] CFG-EXP-MOVIMENTI
    - [x] ZMOD_ST_JSON_I_MOV
    - [ ] Método IMPORTA_MOVIMENTOS
    - [x] ZMOD_LOG_I_MOV
    - [x] ZMOD_LOG_D_I_MOV
    - [ ] Programa ZMOD_IMP_MOVIMENTOS

&nbsp;

Operazione completata con successo

![081df6124fb9e142e1b3cfce8aed3a62.png](../_resources/081df6124fb9e142e1b3cfce8aed3a62.png)

&nbsp;

&nbsp;

* * *

![3052c93cb64a34675ae7243d5297d12b.png](../_resources/3052c93cb64a34675ae7243d5297d12b.png)

![2c590e3eb6ec42dfd9548bab36285944.png](../_resources/2c590e3eb6ec42dfd9548bab36285944.png)

![7becc3abf40dcc8ccf9adbd0b2ec7afe.png](../_resources/7becc3abf40dcc8ccf9adbd0b2ec7afe.png)

![ee324cb3dd104bf68447f13b00e80477.png](../_resources/ee324cb3dd104bf68447f13b00e80477.png)

&nbsp;

&nbsp;

* * *

&nbsp;

&nbsp;![d199da3e4824c3c3acedcf02c7a07a0a.png](../_resources/d199da3e4824c3c3acedcf02c7a07a0a.png)

![29e1ae9741959ff7d4305d67769b5738.png](../_resources/29e1ae9741959ff7d4305d67769b5738.png)

&nbsp;

Pedido fica pendente que o material seja arrumado

![5fe72302ff35ba669752601e52a1d4ff.png](../_resources/5fe72302ff35ba669752601e52a1d4ff.png)