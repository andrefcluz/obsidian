---
title: Cockpit para geração e envio do XML dos mapas
updated: 2025-08-20 15:32
created: 2023-01-21 15:31:13Z
author: André Luz
tags:
  - toinovate_proj_internos
cliente: toinovate_proj_interno
---

- Tabelas
    - Tabela com ID dos mapas, descrições, intervalo de anos em que estão ativos, e periodicidade, sequencia de execução
    - Tabela de log de geração do XML dos mapas e submissão
    - Tabelas de configuração
        - Dados de API/Webservice e pisco para indicar se a funcionalidade está ativa - sem SM30, atualizável através do cockpit (apenas permite uma entrada, colocar apenas o MANDT como primary key)
        - Dados de utilizador da UNILEO - com password encriptada e sem SM30, tem que ser atualizada diretamente a partir do cockpit, através de um botão que pede a password atual e depois permite substituir (apenas permite uma entrada, colocar apenas o MANDT como primary key)
- Cockpit com empresa, ano, tipo de periodo e período como parâmetros
    - Ao executar cockpit, ler tabela geral dos mapas para obter os que estão ativos naquele momento para aquela periodicidade, e com o ID dos mapas apanhados, depois fazer seleção à tabela de log com esses IDs e empresa, ano, período inseridos nos parâmetros do cockpit
    - ALV principal com a lista dos mapas, com os campos:
        - Empresa
        - Ano
        - Tipo periodo
        - Periodo
        - ID do mapa
        - Descrição do mapa
        - Ícone de XML gerado
            - Ao clicar mostra o XML enviado
        - <s>Ícone para exibir dados em ALV</s>
            - <s>Ao clicar, converte o XML enviado mais recente em tabelas, caso exista já um XML de retorno ALV editável, e permite depois substituir o XML com os dados editados</s>
        - Status mais recente (este campo pode estar escondido, dependendo se o cliente usa a opção para enviar os XML via webservice ou manualmente)
            - Ao clicar neste botão exibe o XML do status mais recente
            - Caso o status seja de erro, com o XML, exibe um botão para mostrar os dados de origem, em ALV, com as linhas em erro marcadas (com um ícone diferente, ou pintadas a vermelho), para serem mais fáceis de identificar
            - A ALV seria editável, e seria possível depois gravar os dados, o que iria gerar um novo XML e enviar o mesmo
        - Data de status mais recente
        - Hora de status mais recente
        - Ícone mais recente
    - ALV lateral de log (ao clicar numa das linhas da ALV principal abre o log completo)
        - ID do Mapa
        - Status
        - Data log
        - Hora log
        - Utilizador log
        - Ícone
    - Botão para gerar XML dos mapas
        - Mostra popup
            - Parâmetros empresa, ano e período (preenchidos por defeito com os mesmos dados dos parâmetros do cockpit)
            - Checkboxes de todos os mapas (para se poder selecionar quais se quer gerar naquele momento, com botões para selecionar ou desselecionar todos)
            - Checkbox para indicar se o XML deve ser logo enviado após ser gerado (com pisco por defeito se o cliente usar webservices; se fizer o envio manualmente esta checkbox ficaria sem o pisco e desativada)
            - Opção para agendar para uma determinada data/hora - ?????
        - Executa (no momento ou agenda) o programa de cada um dos mapas selecionados em background, onde extrai os dados, gera os XML, grava-os no servidor
            - No servidor cria uma pasta com EMPRESA+ANO+TIPO_PERIODO+PERIODO, e uma subpasta com a data e hora de execução YYYYMMDD_HHMMSS
        - Faz o envio para a UNILEO caso tenha o pisco em enviar
    - Botão para guardar ficheiros XML dos mapas selecionados na ALV no computar (mostra o caminho onde quer guardar, e guarda todos os mapas nessa pasta, com os seus nomes originais)
    - Botão para obter status dos mapas
    - Botão (com dropdown) com acesso direto a todas as tabelas de parametrização
        - Uma das opções seria a opção para alterar o utilizador e/ou password

STATUS

- A gerar XML
- Erro na geração do XML
- XML gerado com sucesso - Quando o XML é gerado diretamente pelo mapa
- XML atualizado manualmente com sucesso - Quando os dados são modificados manualmente e é gerado um novo XML
- Erro no envio do XML
- XML enviado com sucesso
- XML integrado com erros
- XML integrado com sucesso (FINAL)