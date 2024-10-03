---
title: Notas AcinGov
updated: 2021-11-10 09:06:50Z
created: 2020-09-23 15:15:13Z
author: André Luz
tags:
  - cp/acingov
---

https://acingov-testes.acin.pt/acingovalpha/2/

joao.manuel@acin.pt
testecp001

Copia de dados esmaga certificados e soamanager?

Codigos novos - Ficou definido com os key-users que os codigos tem que ser sempre atualizados em SAP antes de serem criados na acinGov. De qualquer forma vai atualizar na PRPS.

Mensagem SOAP:1.023 SRT: Processing error in Internet Communication Framework: ("ICF Error when receiving the response: ICM_HTTP_ - Aumentar para 255

Conversão certificado - Depois de estar tudo a funcionar em CPP, questionar a acinGov se é possivel enviar o certificado privado no formato (PSE???) e se for passar

* * *

Tabelas parametrização

|     |     |
| --- | --- |
| Tipos de Aquisição | ZPS_AQUISICAO |
| Tipos de Procedimento | ZPS_PROCEDIMENTO |
| Mapeamento Utilizadores | ZPS_ACIN_USER_ID |
| Histórico Interface | ZPS_ACIN_SERV |
| Campos Interface | ZPS_ACIN_CAMPOS |
| Mapeamento dados CP<>AcinGov | ZPS_ACIN_MAP |
| Mapeamento campos longos | ZPS_ACIN_MAP_FLD |
| Dados autentificação WS | ZPS_ACIN_WS_AUTH |

* * *

Programas

|     |     |
| --- | --- |
| Cockpit | ZPS_ACIN_COCKPIT |
| Programa Associação Manual | ZPS_ACIN_PEP_MANUAL |
| Programa Associação Manual em Massa | ZPS_ACIN_PEP_MANUAL_MASS |
| Consulta procedimentos na AcinGov | ZPS_ACIN_CONSULTA_PROC |
| Marca procedimentos existentes como enviados | ZPS_ACIN_ENV_ACINGOV |

* * *

Classes

|     |     |
| --- | --- |
| Classe da interface | ZPS_ACIN_CL_WS_INTERFACE |
| Classe de conversão JSON | ZCL_FDT_JSON |

* * *

Webservice
ZPS_ACIN_CO_ACIN_GOVPORT

* * *

Ampliação
ZPS_ACIN_WS_CRIA_PROCEDIMENTO