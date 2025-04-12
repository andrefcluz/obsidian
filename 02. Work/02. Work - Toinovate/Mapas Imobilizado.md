---
title: Mapas Imobilizado
updated: 2024-10-06 10:50
created: 2018-03-15 09:46:01Z
source: file:///C:\Users\André%20Luz\Google%20Drive\02.Work\ToInovate\Clientes\eSPap\Gerfip%203.1\Mapas\Imobilizado\AI\%5bDSI_CC%5dDEV_R_AA-Quadros_AI_V1.0.docx
author: André Luz
tags:
  - espap
  - espap-gerfip31
---

Domínios

- **ZAA_ID_COL** - ID's de coluna (Aqui estão parametrizados os intervalos de valores possíveis para ID, caso haja alterações têm que ser feitas diretamente aqui no domínio)

Tabelas

- **ZAA_MAPAS_RUBR** - Rubricas Mapas Imobilizado - Mapeamento por Item Financeiro
- **ZAA_SNCAP_COLMOV** - Fora de âmbito, chegou-se à conclusão que era suficiente manter esta parametrização no domínio ZAA_ID_COL)
- **ZAA_SNCAP_TPMOV** - Imobilizado - Associação entre ID's de colunas e tipos de movimento

**Mapa AI**

**Programa**: ZAA_MAPA_AI

**Transação**: ZAA_MAPA_AI

**Transformação**: ZAI

**Ecrã de seleção**

- Quadro 3.1 **1**
- Quadro 3.2 **2**
                - [ ] Quadro 3.2
                - [ ] Quadro 3.2A
                - [ ] Quadro 3.2B

**1** Apenas ALV

**2** XML se não selecionada nenhuma das opções abaixo | ALV se selecionada uma ou mais das opções (agrega)

Ver como fazer, se esconder/mostrar opção consoante escolhida a opção ALV ou XML, ou apenas validar se as opções escolhidas fazem sentido

**Mapeamento campos**

|     |     |     |     |
| --- | --- | --- | --- |
| **3.1** | **3.2** | **3.2A** | **3.2B** |
| Rubricas (1) | Rubricas (1) | Rubricas (1) | Rubricas (1) |
| Quantia Bruta (2) | Quantia escriturada inicial (2) | Internas (2) | Alienação a título oneroso (2) |
| Amortizações acumuladas (3) | Adições (3) | Compra (3) | Transferência ou troca (3) |
| Perdas por imparidade acumuladas (4) | Transferências internas à entidade (4) | Cessão (4) | Fusão, cisão, reestruturação (4) |
| Quantia escriturada (5) = (2) - (3) - (4) | Revalorizações (5) | Transferência ou troca (5) | Outras (5) |
| Quantia bruta (6) | Reversões de perdas por imparidade (6) | Doação, herança, legado ou perdido a favor do Estado (6) | Total (6) |
| Amortizações acumuladas (7) | Perdas por imparidade (7) | Dação em pagamento (7) |     |
| Perdas por imparidade acumuladas (8) | Amortizações do  período (8) | Locação financeira (8) |     |
| Quantia escriturada (9) = (6) - (7) - (8) | Diferenças cambiais (9) | Fusão, cisão, reestruturação (9) |     |
|     | Diminuições (10) | Outras (10) |     |
|     | Quantia escriturada final (11) | Total (11) |     |

[Mapas imobilizado - AI - Tabelas usadas na seleção de dados](https://docs.google.com/spreadsheets/d/15vNIBkasv2fkYJElOM8aAMF443ork7D9jgldkkg75Sc/edit?usp=drive_web)

|     |     |     |
| --- | --- | --- |
|     | **XML** | **SAP** |
|     | AI  |     |
|     | Cabeçalho |     |
| - [X] | Entidade | T001-STCEG |
| - [X] | Data | AAAA-MM-DDThh:mm:ss |
| - [X] | Ano |  GJAHR |
| - [X] | Periodicidade | T (Trimestral) |
| - [X] | Periodo | 01, 02, 03, 04<br>14<br>(1º Trimestre, 2º Trimestre, 3º Trimestre, 4º Trimestre, 4º Trimestre - Após apuramento dos resultados) |
| - [X] | PlanoContasLocal | SNC-AP |
|     | AtivosIntangiveis |     |
|     | Resumo |     |
| - [X] | ID_Resumo |     |
| - [X] | RubricaAgregadora | Coluna 1 do mapa 3.2 – corresponde à rubrica agregadora do mapa (AI) |
| - [X] | TotalQuantiaEscrituradaInicial | Total Coluna 2 do mapa 3.2 (AI) |
| - [X] | TotalAdicoes | Total Coluna 3 do mapa 3.2 (AI) |
| - [X] | TotalTransferenciasInternasEntidade | Total Coluna 4 do mapa 3.2 (AI) |
| - [X] | TotalRevalorizacoes | Total Coluna 5 do mapa 3.2 (AI) |
| - [X] | TotalReversoesPerdasImparidade | Total Coluna 6 do mapa 3.2 (AI) |
| - [X] | TotalPerdasImparidade | Total Coluna 7 do mapa 3.2 (AI) |
| - [X] | TotalAmortizacoesPeriodo | Total Coluna 8 do mapa 3.2 (AI) |
| - [X] | TotalDiferencasCambiais | Total Coluna 9 do mapa 3.2 (AI) |
| - [X] | TotalDiminuicoes | Total Coluna 10 do mapa 3.2 (AI) |
| - [X] | TotalQuantiaEscrituradaFinal | Total Coluna 11 do mapa 3.2 (AI) |
|     | Registos |     |
| - [X] | Registo |     |
| - [X] | ID_Registo |     |
| - [X] | Rubrica | Rubricas do mapa (deve criar um “bloco” por cada Rubrica do mapa) |
| - [X] | RubricaAgregadora | Rubrica agregadora para a rubrica tratada |
| - [X] | QuantiaEscrituradaInicial | Coluna 2 do mapa 3.2 (AI) para a rubrica |
| - [X] | Adicoes | Coluna 3 do mapa 3.2 (AI) para a rubrica |
| - [X] | TransferenciasInternasEntidade | Coluna 4 do mapa 3.2 (AI) para a rubrica |
| - [X] | Revalorizacoes | Coluna 5 do mapa 3.2 (AI) para a rubrica |
| - [X] | ReversoesPerdasImparidade | Coluna 6 do mapa 3.2 (AI) para a rubrica |
| - [X] | PerdasImparidade | Coluna 7 do mapa 3.2 (AI) para a rubrica |
| - [X] | AmortizacoesPeriodo | Coluna 8 do mapa 3.2 (AI) para a rubrica |
| - [X] | DiferencasCambiais | Coluna 9 do mapa 3.2 (AI) para a rubrica |
| - [X] | Diminuicoes | Coluna 10 do mapa 3.2 (AI) para a rubrica |
| - [X] | QuantiaEscrituradaFinal | Coluna 11 do mapa 3.2 (AI) para a rubrica |
|     | AtivosIntangiveisDesagregacaoAdicoes |     |
|     | Resumo |     |
| - [X] | ID_Resumo |     |
| - [X] | RubricaAgregadora | Coluna 1 do mapa 3.2 – corresponde à rubrica agregadora do mapa (AI) |
| - [X] | TotalInternas | Total Coluna 2 do mapa 3.2A (AI-A) |
| - [X] | TotalCompra | Total Coluna 3 do mapa 3.2A (AI-A) |
| - [X] | TotalCessao | Total Coluna 4 do mapa 3.2A (AI-A) |
| - [X] | TotalTransferenciaTroca | Total Coluna 5 do mapa 3.2A (AI-A) |
| - [X] | TotalDoacaoHerancaLegadoOuPerdidoFavorEstado | Total Coluna 6 do mapa 3.2A (AI-A) |
| - [X] | TotalDacaoPagamento | Total Coluna 7 do mapa 3.2A (AI-A) |
| - [X] | TotalLocacaoFinanceira | Total Coluna 8 do mapa 3.2A (AI-A) |
| - [X] | TotalFusaoCisaoReestruturacao | Total Coluna 9 do mapa 3.2A (AI-A) |
| - [X] | TotalOutras | Total Coluna 10 do mapa 3.2A (AI-A) |
| - [X] | TotalGeral | Total Coluna 11 do mapa 3.2A (AI-A) |
|     | Registos |     |
| - [X] | Registo |     |
| - [X] | ID_Registo |     |
| - [X] | Rubrica | Rubrica do mapa (deve criar um “bloco” por cada Rubrica do mapa |
| - [X] | RubricaAgregadora | Rubrica agregadora do mapa para a rubrica tratada |
| - [X] | Internas | Coluna 2 do mapa 3.2A (AI-A) |
| - [X] | Compra | Coluna 3 do mapa 3.2A (AI-A) |
| - [X] | Cessao | Coluna 4 do mapa 3.2A (AI-A) |
| - [X] | TransferenciaTroca | Coluna 5 do mapa 3.2A (AI-A) |
| - [X] | DoacaoHerancaLegadoOuPerdidoFavorEstado | Coluna 6 do mapa 3.2A (AI-A) |
| - [X] | DacaoPagamento | Coluna 7 do mapa 3.2A (AI-A) |
| - [X] | LocacaoFinanceira | Coluna 8 do mapa 3.2A (AI-A) |
| - [X] | FusaoCisaoReestruturacao | Coluna 9 do mapa 3.2A (AI-A) |
| - [X] | Outras | Coluna 10 do mapa 3.2A (AI-A) |
| - [X] | Total | Coluna 11 do mapa 3.2A (AI-A) |
|     | AtivosIntangiveisDesagregacaoDiminuicoes |     |
|     | Resumo |     |
| - [X] | ID_Resumo |     |
| - [X] | RubricaAgregadora | Coluna 1 do mapa 3.2 – corresponde à rubrica agregadora do mapa (AI) |
| - [X] | TotalAlienacaoTituloOneroso | Total Coluna 2 do mapa 3.2B (AI-D) |
| - [X] | TotalTransferenciaTroca | Total Coluna 3 do mapa 3.2B (AI-D) |
| - [X] | TotalFusaoCisaoReestruturacao | Total Coluna 4 do mapa 3.2B (AI-D) |
| - [X] | TotalOutras | Total Coluna 5 do mapa 3.2B (AI-D) |
| - [X] | TotalGeral | Total Coluna 6 do mapa 3.2B (AI-D) |
|     | Registos |     |
| - [X] | Registo |     |
| - [X] | ID_Registo |     |
| - [X] | Rubrica | Rubrica do mapa (deve criar um “bloco” por cada Rubrica do mapa) |
| - [X] | RubricaAgregadora | Rubrica agregadora do mapa para a rubrica tratada |
| - [X] | AlienacaoTituloOneroso | Coluna 2 do mapa 3.2B (AI-D) |
| - [X] | TransferenciaTroca | Coluna 3 do mapa 3.2B (AI-D) |
| - [X] | FusaoCisaoReestruturacao | Coluna 4 do mapa 3.2B (AI-D) |
| - [X] | Outras | Coluna 5 do mapa 3.2B (AI-D) |
| - [X] | Total | Coluna 6 do mapa 3.2B (AI-D) |

* * *

![DDORC_rubricas.jpg](DDORC_rubricas.jpg)