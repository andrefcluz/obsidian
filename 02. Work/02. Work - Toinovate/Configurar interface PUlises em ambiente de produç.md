---
title: Configurar interface PUlises em ambiente de produção da CP
updated: 2024-10-06 10:51
created: 2019-12-18 09:32:08Z
author: André Luz
tags:
  - cp
---

1. Fazer configurações com base no manual de parametrização e com as configurações já existentes em ambiente de produção da EMEF

2. No ponto 3.4 colocar pastas "dummy" para que na primeira execução os materiais que foram migrados da EMEF para a CP não sejam enviados para o robot

3. Fazer primeira execução manualmente. Executar report RBDMIDOC em background com os parametros CLFMAS e MATMAS

4. Validar que os ficheiros IDOC foram todos criados, e fazer nova execução ao programa para confirmar que não são criados novamente

5. Caso não sejam, quer dizer que está a funcionar bem, então refazer o passo 3.4 do manual mas colocar as pastas corretas, onde o robot irá ler os dados

6. Criar job identico ao GERACAO IDOC ULISES da EMEF em produção

[ManualParametrizacao_v1.1.pdf](ManualParametrizacao_v1.1.pdf)