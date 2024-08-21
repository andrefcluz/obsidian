---
title: PS - Estimativa interface acinGOV
updated: 2021-11-10 09:06:49Z
created: 2020-03-20 14:58:53Z
author: André Luz
tags:
  - cp
---

**Configurar ligações à plataforma acinGOV | 1 hora - ??? horas**

- Criar serviço em SAP com base no WSDL | **1 hora**
    - Isto vai gerar automaticamente uma classe SAP, que basicamente é o interface de comunicação entre SAP e a plataforma do acinGOV.  Nessa classe são gerados automaticamente um método para cada uma das operações do WebService (CriaProcedimento, ConsultaProcedimento, ConsultaAdjudicacao)
- Configurar as ligações na SOAMANAGER - Esta parte será a administração de sistemas a fazer | **???**

* * *

**Criar estruturas e transformações SAP | 24 horas - ??? horas**

- Criar estruturas com os campos utilizados pelas operações e respetivos elementos de dados e dominios | **12 horas**
- Criar transformações para XML em SAP para todas as operações (saida e entrada), caso os Webservices suportem XML. Se for por JSON ainda tem que se ver como fazer | **12 horas - ??? horas**

* * *

**Criar tabelas de log | 3 horas**

- Tabela com o procedimento SAP, ID acinGOV e status atual | **1 hora**

|     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| PEP | ID acinGOV | Status Atual | Data Criação | Hora Criação | User Criação | Data Ult. Modif. | Hora Ult. Modif. | User Ult. Modif. |

- Tabela com log dos procedimentos (mensagens de erro, etc) | **1 hora**

|     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- |
| PEP | Status | Data Status | Hora Status | User Status | Mensagem Status |

- Tabela de procedimentos a processar (procedimentos que foram modificados na plataforma e ainda não foram atualizados em SAP) | **0.5 hora**

|     |     |     |
| --- | --- | --- |
| PEP | Data Modif. acinGOV | Hora Modif. acinGOV |

- Tabela com data da ultima consulta de modificações à plataforma acinGOV | **0.5 hora**

|     |
| --- |
| Data Ult. Consulta |

* * *

**Criar procedimento | 4 horas**

- Chamar o WS ao gravar o procedimento, apenas na criação (talvez através da BADI WORKBREAKDOWN_UPDATE) e atualizar tabelas de status e log | **4 horas**

* * *

**Consultar procedimento | 8 horas**

- [Este ponto é apenas uma ideia, ainda tem que se ver com o acinGOV se é possível fazer] Criar programa que tem como parametros um intervalo de datas, e vai à plataforma do acinGOV ver que procedimentos tiveram alterações nesse intervalo de datas, e grava-os na tabela de procedimentos a processar em SAP. Grava também a data superior na tabela da data da última consulta | **4 horas**
- Criar programa que passando como parametro o PEP vai consultar o procedimento na plataforma da acinGOV, e caso haja alterações atualiza o mesmo em SAP | **4 horas**
    - Se o primeiro ponto for para a frente, então este programa em vez de ter como parametro de entrada o procedimento, pode ir à tabela de procedimentos a processar e é executado para todos os que estiverem lá. Também se pode ter as duas opções caso justifique.
    - Este programa depois será chamado no cockpit, mediante a seleção de um ou vários PEP's. E também poderá ser chamado via job, por exemplo diariamente. Mais uma vez, se o primeiro ponto for para a frente, poderá ser esse chamado no cockpit em via job, e este ser chama pelo outro ou isoladamente.

* * *

**Consultar adjudicação | 4 horas**

- Há-de ser semelhante ao "Consultar Procedimento", portanto é rápido de fazer. Depois tem que se ver se se terá que criar tabelas adicionais para este ponto

* * *

**Cockpit | 24 horas**

- Criação de Cockpit para gestão dos procedimentos já existentes | **24 horas**
    - Listar procedimentos por ID, intervalo de datas e status
    - Visualizar log completo de cada procedimento
    - Reprocessar procedimentos em erro
    - Obter lista de procedimentos com modificações na plataforma acinGOV e que têm que ser atualizados em SAP
    - Atualizar procedimentos que têm modificações na plataforma acinGOV e ainda não foram refletidas em SAP

* * *

**TOTAL: 68 horas - ??? horas**