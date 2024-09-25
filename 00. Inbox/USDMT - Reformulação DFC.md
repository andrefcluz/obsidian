---
title: Reformulação DFC
updated: 2024-08-06 15:14:17Z
created: 2024-08-06 14:54:56Z
latitude: 38.72225240
longitude: -9.13933660
altitude: 0.0000
---

1.  Ler dados DFC (diferente para cada cliente)
2.  Ler dados FMIFIIT - Igual para todos os clientes. Mas pode mudar a tabela de exceções (/USDMT/ACT_FUNCT-NOVAS_EXC_ACTIVE), e a fonte de dados, se é a FMIFIIT standard ou a cópia /USDMT/FMIFIIT (/USDMT/ACT_FUNCT-TABS_PROPRIAS_ACTIVE)
3.  Match Dados
    1.  Match Direto - Igual para todos os clientes
    2.  Trata documentos KP - Apenas IP 
        1.  Trata documentos KP - Quando tem vários pagamentos - Apenas IP
    3.  Tratar documentos de IVA Z9 - Apenas IP
    4.  Tratar documentos de compensação - Todos os clientes
        1.  Trata documentos de compensação de forma recursiva - Todos os clientes
    5.  Match direto DFC e Orçamental com diferença de montante - Todos os clientes
    6.  Match por valor / Processo de retenção das garantias - Todos os clientes
        1.  Match por valor com grupos com diferença - Todos os clientes
    7.  Tratar documentos orçamentais que sobram - Todos os clientes
    8.  Tratar documento DFC que sobram - Todos os clientes
    9.  Ajusta semáforos dos documentos DFC e orçamentais sem match - Todos os clientes
    10. Documentos integração vencimentos - Todos os clientes
    11. Adiciona documentos de reconciliação bancária - Todos os clientes
    12. Recalcular grupos - Todos os clientes
    13. Preenche os dados base de execução - Todos os clientes