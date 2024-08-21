---
title: CP - Interface acinGov
updated: 2021-11-10 09:06:54Z
created: 2020-07-24 08:24:16Z
author: André Luz
tags:
  - cp-acingov
---

**Ambiente de teste**

WSDL: https://acingov-testes.acin.pt/acingovalpha/1/webservice/webserver2/webserver.php?wsdl

**Cerificados**

[certificado_digital(12).crt](certificado_digital(12).crt)[João Manuel_2YILzqH151.p12](Jo_o_Manuel_2YILzqH151.p12)

2YILzqH151

https://acingov-testes.acin.pt/acingovalpha/2/

joao.manuel@acin.pt
1234
<s>testecp001</s>

Ambiente de produção

WSDL: https://www.acingov.pt/acingovprod/1/webservice/webserver2/webserver.php?wsdl

https://www.acingov.pt/acingovprod/2/index.php/
CP_WEBSERVICE
gredes@cp.pt
CP_20202020

* * *

**Objetos Criados**
**
**
Tabelas

- ZPS_ACIN_SERV
- ZPS_ACIN_LOG
- ZPS_ACIN_MAP

Programas

- ZPS_ACIN_COCKPIT

Classes

- ZPS_ACIN_CL_WS_INTERFACE

Conversa Manuela - 27/07/2020

- Ativar Trace mais completo na Soamanager para ver se obtemos mais informação
- Enviar email para a CP por causa da firewall
- A Manuela vai tentar transformar o certificado privado em formato PSE e se conseguir envia juntamente com um tutorial da AT de como carregar em SAP

https://us02web.zoom.us/j/85285471107?pwd=cFV3bEtJU3FLbzFMS3ZzT3dYbUF3QT09

Pedir à Manuela para converter certificado privado para formato PSE, depois na STRUST carregar em File (duplo clique) e seleciona o certificado convertido. Após isso clicar na linha de cima, do primeiro campo da tela (Titular), e depois cá em baixo escolher a opção para carregar certficado e desta vez selecionar o publico, e clicar em "Inserir na lista de certificados". Por fim no menu clicar em PSE -> Gravar Como e depois selecionar a opção Mandante SSL

* * *

**Passos a fazer depois em CPP:**

**STRUST**

- Pedir à Manuela para converter certificado privado para formato PSE, depois na STRUST carregar em File (duplo clique) e seleciona o certificado convertido. Após isso clicar na linha de cima, do primeiro campo da tela (Titular), e depois cá em baixo escolher a opção para carregar certficado e desta vez selecionar o publico, e clicar em "Inserir na lista de certificados". Por fim no menu clicar em PSE -> Gravar Como e depois selecionar a opção Mandante SSL
- Ir ao endpoint de produtivo (que deverá ser https://www.acingov.pt/acingovprod/2/index.php/) e fazer download do certificado Sectigo e gravar em formato .CER
- Adicionar o certificado na STRUST no SSL Client Standard

**SOAMANAGER**

- Gravar o WSDL para ficheiro
- Criar um proxy com base no WSDL (não vai ser o final, vai servir apenas para copiar as configurações para o DEFAULT)
- Criar outro proxy (o final) com o nome DEFAULT e escolhe a opção para criar manualmente
- Na parte da autentificação selecionar a opção X.509 SSL Client Certificate e depois escolher o DFAULT
- O resto das configurações copiar do proxy que foi criado com base no WSDL

* * *

Contato Victor Abreu - 967725937

* * *

Conversa Luís Jacinto

CTT:
CL_FDT_JSON
ZCL_ORION_CRM_REST
MF ZPEG_WF_ARCHIV

![image_2020_07_28T11_55_05_575Z.png](image_2020_07_28T11_55_05_575Z.p)

EXTJUS
toin2014

* * *

Campos em falta/duvida

* * *

fundamentacao_abertura_procedimento
fundamentacao_criterio_material

* * *

Objetos a adicionar no manual/especificação

Tabelas
ZPS_ACIN_WS_AUTH
ZPS_ACIN_USER_ID

CP COMBOIOS DE PORTUGAL, EPE

* * *

8VKiWuX5Bh

https://www.acingov.pt/acingovprod/1/webservice/webserver2/webserver.php?wsdl