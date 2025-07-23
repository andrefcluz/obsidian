---
title: IPL - Safemed
updated: 2025-07-21 15:58
created: 2024-05-08 09:23:23Z
latitude: 38.7222524
longitude: -9.1393366
altitude: 0
tags:
  - ipl/safemed
---
### Ordens de Transporte

| OT         | Descrição                                          | Transporte QLP | Transporte PRD |
| ---------- | -------------------------------------------------- | -------------- | -------------- |
| DPLK907115 | RH7-SH2-LQRD - Interface Safemed #1 - FR/AL        | 2024.12.04     | 2025.02.03     |
| DPLK907390 | RH7-SH2-LQRD - Interface Safemed #1 - CUST - FR/AL | 2024.12.04     | 2025.02.03     |
| DPLK907411 | RH7-SH2-LQRD - Interface Safemed #2 - FR/AL        | 2024.12.05     | 2025.02.03     |
| DPLK907413 | RH7-SH2-LQRD - Interface Safemed #2 - CUST - FR/AL | 2024.12.05     | 2025.02.03     |
| DPLK907449 | RH7-SH2-LQRD - Interface Safemed #3 - FR/AL        | 2024.12.05     | 2025.02.03     |
| DPLK907455 | RH7-SH2-LQRD - Interface Safemed #4 - FR/AL        | 2024.12.11     | 2025.02.03     |
| DPLK907466 | RH7-SH2-LQRD - Interface Safemed #5 - FR/AL        | 2024.12.13     | 2025.02.03     |
| DPLK907468 | RH7-SH2-LQRD - Interface Safemed #3 - CUST - FR/AL | 2024.12.12     | 2025.02.03     |
| DPLK907470 | RH7-SH2-LQRD - Interface Safemed #4 - CUST - FR/AL | 2024.12.12     | 2025.02.03     |
| DPLK907472 | RH7-SH2-LQRD - Interface Safemed #5 - CUST - FR/AL | 2024.12.12     | 2025.02.03     |
| DPLK907479 | RH7-SH2-LQRD - Interface Safemed #6 - FR/AL        | 2024.12.17     | 2025.02.03     |
| DPLK907483 | RH7-SH2-LQRD - Interface Safemed #6 - CUST - FR/AL | 2024.12.17     | 2025.02.03     |
| DPLK907492 | RH7-SH2-LQRD - Interface Safemed #7 - FR/AL        | 2025.02.03     | 2025.02.03     |
| DPLK907618 | RH7-SH2-LQRD - Interface Safemed #7 - CUST - FR/AL | 2025.02.03     | 2025.02.03     |
| DPLK907638 | RH7-SH2-LQRD - Interface Safemed #8 - AL           | 2025.02.24     | 2025.02.24     |
| DPLK907859 | JP1-639-S35V - Safemed ajustes #1 - AL             | 2025.06.03     | 2025.06.05     |
| DPLK907864 | JP1-639-S35V - Safemed ajustes #2 - AL             | 2025.06.05     | 2025.06.05     |
| DPLK907869 | JP1-639-S35V - Safemed ajustes #3 - AL             | 2025.06.18     | 2025.06.18     |
| DPLK907882 | JP1-639-S35V - Safemed ajustes #4 - AL             | 2025.06.24     | 2025.06.24     |
| DPLK907884 | JP1-639-S35V - Safemed ajustes #5 - AL             | 2025.06.24     | 2025.06.24     |
| DPLK907901 | JP1-639-S35V - Safemed ajustes #6 - AL             | 2025.07.10     | 2025.07.10     |
| DPLK907907 | JP1-639-S35V - Safemed ajustes #7 - AL             | 2025.07.11     | 2025.07.11     |
| DPLK907911 | JP1-639-S35V - Safemed ajustes #8 - AL             | 2025.07.17     | 2025.07.17     |
| DPLK907913 | JP1-639-S35V - Safemed ajustes #9 - AL             | 2025.07.18     | 2025.07.18     |
| DPLK907915 | JP1-639-S35V - Safemed ajustes #10 - AL            | 2025.07.18     | 2025.07.18     |
| DPLK907917 | JP1-639-S35V - Safemed ajustes #11 - AL            | 2025.07.18     | 2025.07.18     |
| DPLK907919 | JP1-639-S35V - Safemed ajustes #12 - AL            | 2025.07.21     | 2025.07.21     |

### Dados Serviço

#### Produção
URL serviço: https://safemed.pt:2087/iplisboa
WSDL: https://safemed.pt:2087/iplisboa/SyncERP.asmx?wsdl

Username: sap
Password: tOqXO73x9HeRg5w

---
#### Testes
URL serviço: https://safemed.pt:2087/ipl_qld
WSDL: https://safemed.pt:2087/ipl_qld/SyncERP.asmx?wsdl

Username: sap
Password: 6Y02DL1Iq85v

---
### Tarefas

1.  Enviar dados para SAFEMED
    1.  Criar tabelas de log
    2.  Criar MF para ler os dados
        1.  Beneficiários
        2.  Ausências
    3.  Criar programas para enviar dados para a SAFEMED
        1.   Beneficiários
        2.  Ausências
    4.  Criar cockpit para ver log dos dados enviados, com a opção de os reenviar
2.  Criar API para os serviços de informática usarem


### Tabelas parametrização SAP

- Dados webservice (user, password, NIF, clientName) - ZSMED_API_DATA
- Dados das empresas (clientName, NIF) - ZSMED_EMPRESAS
- Lista de eventos a considerar - ZSMED_EVENTOS
- Mapeamento estabelecimentos - ZSMED_ESTABELEC
- Mapeamento códigos ausência - ZSMED_COD_AUSENC
