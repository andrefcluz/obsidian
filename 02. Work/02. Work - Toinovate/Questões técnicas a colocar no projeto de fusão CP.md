---
title: Questões técnicas a colocar no projeto de fusão CP/EMEF
updated: 2021-11-10 09:06:47Z
created: 2019-10-09 09:21:12Z
author: André Luz
tags:
  - cp
  - cp-emef
---

- Comparar estrutura organizacional de ambas as empresas
- Verificar e comparar o componentes SAP utilizados por cada empresa
- Verificar e comparar os processos utilizados por cada empresa
- Comparar parametrização de cada empresa
- Comparar repositório de cada empresa (objetos Z) - Técnico
- Verificar dados mestre duplicados
- Analizar interfaces existentes em cada empresa - Técnico

Questões a colocar na reunião técnica:

- **Versões SAP**
- **Versões SO**
- **Versões DB**
- **Versões Neptune**
- **Interfaces**
    - Listagem de interfaces existentes em cada empresa
    - Modo de funcionamento de cada interface - RFC, IDoc, SOAP (Webservice), BAPI, Rest, DBLinks
    - Fluxo
    - Sobre que máquinas opera (por exemplo se for sobre a máquina de HR da EMEF e essa máquina se mantiver isolada, então em principio não tem que se fazer nada em relação aos interfaces)
    - Exemplos de dados usados pelas interfaces (estrutura de exemplo, etc)
- **Base de dados**
    - Campos Z adicionados a tabelas standard
    - Problemas de performance (Indices)
- **Validações/Substituições**
- **Exits/BADI's**
    - Exits e implementações de BADI existentes
    - Ecrãs modificados
- **Enhancements ao standard**
- **BTE's**
- **Objetos Z**
    - Tabelas/estruturas/visões
    - Elementos de dados
    - Dominios
    - Programas
    - Módulos de função/Grupos de função
    - Classes
    - Transações
- **Jobs existentes (Cadeia de batch)**
- **Autorizações**

* * *

Neptune - Ver como puxar desenvolvimentos da EMEF para a CP