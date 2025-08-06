---
title: Mapas S3CP
updated: 2024-10-06 10:50
created: 2019-07-24 09:59:57Z
author: André Luz
tags:
  - cp
---

|     |     |     |
| --- | --- | --- |
|     | Programa | Transação |
| Cockpit | ZFI_COCKPIT_EXPORT_XML | ZFI_EXPORT_SEND_XML |

Mapas

|     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
| Mapa | Descrição | Cockpit? | Programa | Transação | Transformação | Programa auxiliar |
| CPLC | Correspondencia Plano de Contas Local/Central | X   | ZFI_MAPA_CPLC | ZFI_MAPA_CPLC | ZCPLC | -   |
| BA  | Balancete Analitico | X   | ZFI_BALANC_ANALITICO | ZFI_BAL_ANALIT | ZBA | ZFI_BALANC_ANALITICO_SALDOS_B |
| DODES | Demonstração Orçamental da despesa | X   | ZEAPS_MAPA_DODES2 | ZEAPS_MAPA_DODES | ZDODES | -   |
| DOREC | Demosntração Orçamental da Receita | X   | ZEAPS_MAPA_DOREC | ZEAPS_MAPA_DOREC | ZDOREC | -   |
| DDORC | Demonstração Desempenho Orçamental | X   | ZFI_MAPA_DDORC | ZFI_MAPA_DDORC | ZDDORC | -   |
| DR/BLC | Demonstração de Resultados / Balanço | X   | ZFI_MAPAS_BALANCO_DR | ZFI_BLC_DR | ZDR/ZBLC | RFBILA00 |
| DTAS | Dívidas a Terceiros por Antiguidade de Saldos | X   | ZFI_MAPAS_DTAS | ZFI_DTAS | ZDTAS | -   |
| DAPL | Demonstração de Alterações no Património Líquido | X   | ZFI_MAPA_DAPL | ZFI_DAPL | ZDAPL | ZMVCP |
| EC  | Encargos Contratuais | X   | ZFI_MAPA_EC | ZFI_EC | ZEC | -   |
| DPPI | Demonstração de Execução do Plano Plurianual de Investimentos | X   | ZFI_MAPA_DPPI | ZFI_MAPA_DPPI | ZDPPI | -   |
| DFC | Demonstração de Fluxos de Caixa | X   | ZFI_MAPA_DFC | -   | ZDFC | -   |
| AI  | Ativos Intangiveis | X   | ZAA_MAPA_AI | ZAA_MAPA_AI | ZA  | -   |
| AFT | Ativos Fixos Tangiveis | X   | ZAA_MAPA_AFT | ZAA_MAPA_AFT | ZAFT | -   |
| PI  | Propriedades de Investimento | X   | ZAA_MAPA_PI | ZAA_MAPA_PI | ZPI | -   |
| OPOP | Orçamento e Plano Orçamental Plurianual |     | ZFI_MAPA_OPOP | ZFI_MAPA_OPOP | -   | -   |
| ATP | Adjudicação por Tipo de Procedimento |     | ZFI_MAPA_ATP | ZFI_MAPA_ATP | -   | -   |
| OT  | Operações de Tesouraria |     | ZFI_MAPA_OT | ZFI_MAPA_OT | -   | -   |
| TSC/TSR | Transf. e Subsídios Concedidos / Transf. e Subsídios Recebidos |     | ZFI_MAPA_TSC_TSR | ZFI_MAPA_TSC_TSR | -   | -   |

Tabelas Parametrização Globais

|     |     |
| --- | --- |
| Tabela | Descrição |
| ZG3_COCK_MAPAS | ID's mapas |
| ZG3_ALV_FIELDS | Campos a exibir nos ALV's dos mapas |
| ZG3_ALV_TITLES | Títulos dos ALV's dos mapas |

Includes Globais

|     |     |
| --- | --- |
| Include | Descrição |
| ZFI_G3_CONSTANTS | Constantes globais |
| ZG3_ROTINAS_ALV | Rotinas de geração de ALV's dos mapas |