---
title: Modula - Inventário
updated: 2025-08-20 15:26
created: 2024-07-09 14:16:30Z
latitude: 41.1579438
longitude: -8.6291053
altitude: 0
tags:
  - cp/modula
cliente: cp
---
## Tarefas após transporte

- [x] Parametrizar tabela ZMOD_API_DATA em PRD
- [x] Remover parametrização da tabela ZMOD_API_DATA em QLD

### Parametrização 

#### ZMOD_API_DATA

| Ambiente | URL Base                            | Username | Password |
| -------- | ----------------------------------- | -------- | -------- |
| TESTES   | http://192.168.3.122:3001/api/jobs/ | modula   | modula   |
| PRODUCAO | http://192.168.3.122:3001/api/jobs/ | modula   | modula   |

--- 
## Ordens de Transporte

| OT         | Descrição                         | Transporte CPP |
| ---------- | --------------------------------- | -------------- |
| CPQK946452 | 7892 - Interface SAP <> MODULA #1 | 2024.09.25     |
| CPQK948117 | 7892 - Interface SAP <> MODULA #2 | 2024.10.02     |
| CPQK948134 | 7892 - Interface SAP <> MODULA #3 | 2024.10.03     |
| CPQK948241 | 7892 - Interface SAP <> MODULA #4 | 2024.10.28     |
| CPQK948330 | 7892 - Interface SAP <> MODULA #5 | 2024.11.15     |
| CPQK948336 | 7892 - Interface SAP <> MODULA #6 | 2024.11.15     |
| CPQK948346 | 7892 - Interface SAP <> MODULA #7 | 2024.11.18     |

---

## Autorizações 

Transação: SUIM 

Função criada a pedido da própria CP

![[Pasted image 20240926105719.png|715]]

* * *

## Comunicações

Teste comunicações em SAP  
Programa: Z_HTTP_REQ_AL

**Z_AL_TESTE_INT_MOV_MODULA**

## Acessos plataforma MODULA

USER: ADVANCED  
PASS: SYSTEM08

[Modula-soapui-project.xml](Modula-soapui-project.xml)

![6782eab4de451325cb87d800318a0bc5.png](6782eab4de451325cb87d800318a0bc5.png)



* * *

## Desenvolvimentos

#### Tipos Processamento

JOB  
MANUAL  
REPROC

@08@ / @5B@ --> Green Light  
@09@ / @5D@ --> Yellow Light  
@0A@ / @5C@ --> Red Light

#### Tarefas

- [x] Criar tabelas de log
    - [x] Tabela de log - ZMOD_LOG_E_MAT
    - [x] Tabela de detalhe - ZMOD_LOG_D_E_MAT
- [x] Criar estrutura do JSON
    - [x] Envio - ZMOD_ST_JSON_E_MAT
    - [x] Receção
- [x] Criar método para envio dos materiais
- [x] Criar programa que vai correr em job e envia os materiais daquele dia
- [x] Criar cockpit


- [x] CFG-IMP-ARTICOLI
    - [x] ZMOD_ST_JSON_E_MAT
    - [x] Método EXPORTA_MATERIAIS
    - [x] ZMOD_LOG_D_E_MAT
    - [x] Programa ZMOD_EXP_MATERIAIS
- [x]  CFG-IMP-ORDINI
    - [x] ZMOD_ST_JSON_E_ORD
    - [x] Método EXPORTA_ORDENS
    - [x] ZMOD_LOG_E_ORD
    - [x] ZMOD_LOG_E_ORD_I
    - [x] ZMOD_LOG_D_E_ORD
    - [x] Programa ZMOD_EXP_ORDENS
- [x] CFG-IMP-SOTTOCODICI
    - [x] ZMOD_ST_JSON_E_ORD_PM
    - [x] Método EXPORTA_ORDENS_PM
    - [x] ZMOD_LOG_E_OPM
    - [x] ZMOD_LOG_D_E_OPM
    - [x] Programa ZMOD_EXP_ORDENS_PM
- [x] CFG-EXP-MOVIMENTI
    - [x] ZMOD_ST_JSON_I_MOV
    - [x] Método IMPORTA_MOVIMENTOS
    - [x] ZMOD_LOG_I_MOV
    - [x] ZMOD_LOG_D_I_MOV
    - [x] Programa ZMOD_IMP_MOVIMENTOS


#### Resposta

Operazione completata con successo

![081df6124fb9e142e1b3cfce8aed3a62.png](081df6124fb9e142e1b3cfce8aed3a62.png)

#### Ordens PM/CS

![3052c93cb64a34675ae7243d5297d12b.png](3052c93cb64a34675ae7243d5297d12b.png)

![2c590e3eb6ec42dfd9548bab36285944.png](2c590e3eb6ec42dfd9548bab36285944.png)

![7becc3abf40dcc8ccf9adbd0b2ec7afe.png](7becc3abf40dcc8ccf9adbd0b2ec7afe.png)

![ee324cb3dd104bf68447f13b00e80477.png](ee324cb3dd104bf68447f13b00e80477.png)


#### Ordens de Transporte/Movimentos

![d199da3e4824c3c3acedcf02c7a07a0a.png](d199da3e4824c3c3acedcf02c7a07a0a.png)

![29e1ae9741959ff7d4305d67769b5738.png](29e1ae9741959ff7d4305d67769b5738.png)


Pedido fica pendente que o material seja arrumado

![5fe72302ff35ba669752601e52a1d4ff.png](5fe72302ff35ba669752601e52a1d4ff.png)


#### Inventário

LICC

LI11N

LX22

LI04


Deposito 910

Tipo deposito 012 (MODULA 1) ou 013 (MODULA 2)


![2fbe486666a32e32256a235311e1e7eb.png](2fbe486666a32e32256a235311e1e7eb.png)


![6e5f919a1aad6d4bdbfb13ea9205af04.png](6e5f919a1aad6d4bdbfb13ea9205af04.png)


![3c0b77b8a8f411521d4e937e82d2b6c8.png](3c0b77b8a8f411521d4e937e82d2b6c8.png)

![0316cbb707b01647d62671e5f38ddcc4.png](0316cbb707b01647d62671e5f38ddcc4.png)

![cf213c7f45441e49c15f818dc6845d8e.png](cf213c7f45441e49c15f818dc6845d8e.png)


![ccf7b90bd73f3be68c74aca3ab6026d5.png](ccf7b90bd73f3be68c74aca3ab6026d5.png)

![a65b0f93da369df2fa54c59fee8a587c.png](a65b0f93da369df2fa54c59fee8a587c.png)