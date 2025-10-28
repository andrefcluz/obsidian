---
updated: 2025-10-23T15:15
created: 2025-08-07 09:47
share_link: https://share.note.sx/497r9mhl
share_updated: 2025-10-16T11:21:26+01:00
---
Este documento descreve tecnicamente os objetos desenvolvidos no âmbito da ferramenta USDMT (UNILEO SAP Data Management Tool).

---
# 🗃️ Objetos
### 🖊️ Namespace
  - /USDMT/

## 📦 Pacotes
- /USDMT/USDMT
- ZUSDMT_EXITS

## 📁 Programas Principais

### Cockpit USDMT
Cockpit utilizado para analisar os dados e fazer correções.

- Programa: /USDMT/COCKPIT 
- Transação: /USDMT/COCKPIT

### Carregamento Invertido
Programa utilizado para carregador os dados para o cockpit, para cliente que não têm mapas orçamentais desenvolvidos.

- Programa: /USDMT/DODES_DOREC_INVERT_JOB
- Transação: /USDMT/CARR_INVERT

### Carregar tabelas auxiliares FMIFIIT e FMIOI
Carrega as tabelas /USDMT/FMIFIIT e /USDMT/FMIOI, para clientes que não utilizam as tabelas standard (FMIFIIT e FMIOI).

- Programa: /USDMT/CARR_FMIFIIT_FMIOI
- Transação: /USDMT/CARR_TABELAS

---
# 🛠️ Configurações Globais
## 📈 Tabelas de Parametrização

### /USDMT/ACT_FUNCT
Tabela utilizada para ativar/desativar funcionalidades especificas.

| Campo                                | Nome Técnico         | Função                                                                                                                                                             |
| ------------------------------------ | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Empresa                              | BUKRS                | Indicar a empresa relevante                                                                                                                                        |
| DODES Ativo?                         | DODES_ACTIVE         | Relatório DODES fica ativo no cockpit                                                                                                                              |
| DOREC Ativo?                         | DOREC_ACTIVE         | Relatório DOREC fica ativo no cockpit                                                                                                                              |
| DFC Ativo?                           | DFC_ACTIVE           | Relatório DFC fica ativo no cockpit                                                                                                                                |
| DFC Rubricas Ativo?                  | DFC_RUBR_ACTIVE      | Relatório DFC por item financeiro fica ativo no cockpit                                                                                                            |
| Analise Comparativa Ativa?           | ANALI_COMP_ACTIVE    | Funcionalidade de análise comparativa fica ativa (para os relatórios DODES, DOREC e OT)                                                                            |
| Reclassificação Ativa?               | RECLAS_ACTIVE        | Funcionalidade de reclassificação fica ativa (para os relatórios DODES e DOREC)                                                                                    |
| Novas Exceções Ativa?                | NOVAS_EXC_ACTIVE     | Funcionalidade de novas exceções fica ativa (para os relatórios DODES, DOREC e OT). Se estiver desativada, utiliza as exceções antigas                             |
| Tabelas Próprias FMIFIIT/FMIOI Ativa | TABS_PROPRIAS_ACTIVE | Funcionalidade de leitura de dados nas tabela /USDMT/FMIFIIT e /USDMT/FMIOI fica ativa. Quando está desativada, faz a leitura nas tabelas standard FMIFIIT e FMIOI |
| DFC Antigo Ativo?                    | DFC_ANTIGO_ACTIVE    | Relatório DFC Antigo fica ativo no cockpit                                                                                                                         |
| OT Ativo?                            | OT_ACTIVE            | Relatório OT fica ativo no cockpit                                                                                                                                 |

### /USDMT/FUNC_ESP
Tabela utilizada para ativar/desativar funcionalidades especiais.

| Campo                    | Nome Técnico | Função                                                                                                                                                           |
| ------------------------ | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Empresa                  | BUKRS        | Indicar a empresa relevante                                                                                                                                      |
| Ano de                   | GJAHR_FROM   | Ano a partir do qual a funcionalidade está ativa                                                                                                                 |
| Ano até                  | GJAHR_TO     | Ano até quando a funcionalidade está ativa                                                                                                                       |
| Area Funcional Única     | FUNC1        | Indica se o cliente/empresa, usa uma área funcional especifica (se estiver ativo, a área funcional a utilizar deve ser parametrizada na tabela /USDMT/AREA_FUNC) |
| Obtém Sociedade Parceira | FUNC2        | Indica se ao obter o detalhe nos relatório DODES e DOREC, deve ser obtidos os dados relativos à Sociedade Parceira (piora a performance)                         |
| -                        | FUNC3        | Por atribuir                                                                                                                                                     |
| -                        | FUNC4        | Por atribuir                                                                                                                                                     |
| -                        | FUNC5        | Por atribuir                                                                                                                                                     |
| -                        | FUNC6        | Por atribuir                                                                                                                                                     |
| -                        | FUNC7        | Por atribuir                                                                                                                                                     |
| -                        | FUNC8        | Por atribuir                                                                                                                                                     |
| -                        | FUNC9        | Por atribuir                                                                                                                                                     |

### /USDMT/AREA_FUNC
Tabela onde é parametrizada a área funcional relevante, quando a funcionalidade especial "Area Funcional Única" está ativa na tabela /USDMT/FUNC_ESP.

| Campo          | Nome Técnico   | Função                                         |
| -------------- | -------------- | ---------------------------------------------- |
| Empresa        | BUKRS          | Indicar a empresa relevante                    |
| Ano de         | GJAHR_FROM     | Ano a partir do qual a área funcional é válida |
| Ano até        | GJAHR_TO       | Ano até quando a área funcional é válida       |
| Área Funcional | AREA_FUNCIONAL | Indicar a área funcional a ser utilizada       |

## 📊Tabelas de Dados

### /USDMT/FMIFIIT
Tabela onde são gravados apenas os dados relevantes da tabela FMIFIIT, para serem utilizados nos relatórios da ferramenta USDMT (a funcionalidade "Tabelas Próprias FMIFIIT/FMIOI Ativa" tem que estar ativa na tabela /USDMT/ACT_FUNCT, e tem que ser criado um job para executar o programa /USDMT/CARR_FMIFIIT_FMIOI, que atualiza a tabela).

### /USDMT/FMIOI
Tabela onde são gravados apenas os dados relevantes da tabela FMIOI, para serem utilizados nos relatórios da ferramenta USDMT (a funcionalidade "Tabelas Próprias FMIFIIT/FMIOI Ativa' tem que estar ativa na tabela /USDMT/ACT_FUNCT, e tem que ser criado um job para executar o programa /USDMT/CARR_FMIFIIT_FMIOI, que atualiza a tabela).

### /USDMT/TAB_STUNR
Tabela onde fica registado o STUNR (ID único e sequencial) do último carregamento FMIFIIT/FMIOI, para que ao fazer o próximo carregamento, apenas carregar os novos (a funcionalidade "Tabelas Próprias FMIFIIT/FMIOI Ativa' tem que estar ativa na tabela /USDMT/ACT_FUNCT).

---
# 📊 Relatórios

## DODES/DOREC
**Nota:** Estes relatórios não têm um programa próprio, estão integrados no /USDMT/COCKPIT
### Funcionalidades Principais
#### Detalhe Orçamental
Ao fazer duplo clique numa das colunas azuis ou verdes (colunas onde o cálculo é feito por fórmula).
#### Detalhe Financeiro
Ao fazer duplo clique nas colunas amarelas.
#### Análise de diferenças de regras de conta (diferenças entre orçamental e financeira)
Ao selecionar uma chave (linha) e selecionar a opção "Análise diferenças regras de contas".
#### Análise de diferenças de regras de mapa
Ao selecionar uma chave (linha) e selecionar a opção "Análise diferenças regras de mapas".
#### Criação de exceções
Selecionando o botão "Exceções" no ecrã principal, ou nas funcionalidades "Detalhe Orçamental" e "Detalhe Financeiro", selecionar um documento e depois selecionar o botão "Excecionar documento".
#### Lançamento de documentos de BL de correção
Ao selecionar uma ou várias chaves (linhas) e selecionar a opção "Lançar documento BL", ou dentro da funcionalidade "Análise de diferenças de regras de conta", selecionando uma linha de um grupo com diferenças, e depois selecionar o botão "Lançar BL Correção".
#### Geração de XML UNILEO
Selecionando o botão "Gerar XML".

### Tabelas Configuração
#### /USDMT/FM_COLS
Tabela onde são parametrizadas as colunas dos relatórios DODES e DOREC.

| Campo                           | Nome Técnico    | Função                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------------------- | --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID Mapa                         | ID_MAPA         | Identificar o mapa: DODES ou DOREC                                                                                                                                                                                                                                                                                                                                                                                                              |
| Regra Mapa                      | RC              | Código regra UNILEO. Exemplo: RC11                                                                                                                                                                                                                                                                                                                                                                                                              |
| Coluna                          | COLUNA          | ID Coluna                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Módulo de função                | FM              | Módulo de função (detalhe orçamental)  para obter dados da coluna. Exemplo: /USDMT/FM_D_CABIMENTOS                                                                                                                                                                                                                                                                                                                                              |
| Sinal                           | SINAL           | OBSOLETO - substituido pela coluna "Inverte Sinal?", que é mais explicito.<br>Utilizado para indicar se a coluna deve ser somada (SOMAR) ou subtrair (SUBTRAIR), os dados obtidos no módulo de função indicado na coluna FM (na prática servia para indicar se o sinal dos valores obtidos devia ser invertido ou não)                                                                                                                          |
| Seleção pelo FI?                | SELECAO_FI      | Indica se para essa coluna os dados devem ser obtidos na financeira em vez da orçamental. Quando não está ativo, obtém os dados pela orçamental, através do MF indicado na coluna FM. Quando está ativo, obtém os dados através da financeira, através do MF /USDMT/FM_GET_CONTA_ZERO, com a regra indicada no campo RC                                                                                                                         |
| Inverte Sinal?                  | INVERTE_SINAL   | Indica se, quando é feita a leitura dos dados, o sinal destes deve ser invertido ("X") ou não (" ")                                                                                                                                                                                                                                                                                                                                             |
| Tipo de Seleção                 | TIPO_SELECAO    | Indica se a seleção é: <br>" " - Direta<br>"F" - Fórmula<br>"M" - Misto <br><br>Quando o tipo de seleção é Fórmula (F), a coluna é exibida a verde no cockpit, e a fórmula utilizada para obter os dados deve ser parametrizada na tabela /USDMT/FORMULAS                                                                                                                                                                                       |
| Obter Transferências de Fundos? | TRANSF_FUNDOS   | Indica se deve ler as transferências de fundos para essa coluna:<br>" " - Não lê<br>"X" - Sim, lê todas, do ano corrente e anos anteriores (sets ZPFM_TF_AA + ZPFM_TF_CORR)<br>"A" - Sim, mas apenas de anos anteriores (set ZPFM_TF_AA)<br>"C" - Sim, mas apenas do ano corrente (set ZPFM_TF_CORR)<br><br>Nota: Para que esta funcionalidade funcione corretamente, os sets ZPFM_TF_AA e ZPFM_TF_CORR têm que ser criados (ver com funcional) |
| Lê detahe na linha ZTOTAL       | DET_ZTOTAL      | Indica se para essa coluna é possível ler o detalhe para todas as chaves orçamentais em simultâneo (fazendo duplo clique na linha ZTOTAL no cockpit)                                                                                                                                                                                                                                                                                            |
| Permite Reclassificar           | RECLASSIFICACAO | Indica se é possível reclassificar essa coluna (a funcionalidade "Reclassificação Ativa?" tem que estar ativa na tabela /USDMT/ACT_FUNCT)                                                                                                                                                                                                                                                                                                       |
| Descrição Coluna                | DESCRICAO       | Descrição da coluna, que vai ser exibida na popup do detalhe no cockpit                                                                                                                                                                                                                                                                                                                                                                         |
Exemplo de parametrização da tabela "Tabela FM_COLS.xlsx"

#### /USDMT/FORMULAS
Para as colunas cujo o cálculo é feito através de fórmula, é necessário parametrizar a fórmula recorrendo a esta tabela.
**Nota:** Atualmente só é utilizado na criação de exceções, para replicar exceções para colunas cuja coluna para o qual se está a lançar a exceção faz parte da fórmula. Devia ser utilizado também na leitura de dados orçamentais, que atualmente está hardcoded.

| Campo                       | Nome Técnico   | Função                                                                                                                                                                                                                              |
| --------------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Coluna Fórmula              | COLUNA_FORMULA | Onde é indicada a coluna que é calculada por fórmula. <br><br>Nota: Essa coluna tem que ter o "Tipo de Seleção" igual a "F" (Fórmula) na tabela /USDMT/FM_COLS                                                                      |
| Coluna                      | COLUNA         | Onde é indicada uma coluna que faz parte da fórmula da coluna que está a ser calculada. Como uma fórmula é constituída por mais do que uma coluna, vão haver uma linha por cada coluna constituinte da fórmula (exemplo abaixo)     |
| Sinal                       | SINAL          | Indica se o valor da coluna indicada no campo COLUNA deve ser somado ou subtraído à fórmula                                                                                                                                         |
| Apenas relevante periodo 14 | PERIODO14      | Indica se é apenas relevante no período 14 (Compromissos a transitar, Obrigações por pagar e Receitas por cobrar no final do período)<br><br>Nota: Esta parametrização devia ser feita na tabela /USDMT/FM_COLS em vez desta tabela |

![[USDMT - Exemplo parametrização fórmula.png]]

#### /USDMT/REGR_ZERO
Tabela onde são parametrizadas as contas onde devem ser selecionados para cada regra da UNILEO, ao fazer as seleções do detalhe financeiro. Também serve para indicar o tipo de documento e conta de contra-partida que devem ser utilizados para cada regra no lançamento dos documentos de BL. 
**Nota:** Esta tabela é suposto ser parametrizada por um funcional.

| Campo                   | Nome Técnico      | Função                                                                                                                                                                                         |
| ----------------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Empresa                 | BUKRS             | Indicar a empresa relevante                                                                                                                                                                    |
| Ano de                  | GJAHR_FROM        | Ano a partir do qual a parametrização é válida                                                                                                                                                 |
| Ano até                 | GJAHR_TO          | Ano até quando a parametrização é válida                                                                                                                                                       |
| ID Mapa                 | ID_MAPA           | Identificar o mapa: DODES ou DOREC                                                                                                                                                             |
| Regra Mapa              | REGRA             | Código regra UNILEO. Exemplo: RC11                                                                                                                                                             |
| Conta do Razão          | CONTA             | Conta onde devem ser lidos os dados financeiros (através do MF /USDMT/FM_GET_CONTA_ZERO). Também é a conta para o qual é feito o lançamento nos lançamentos de documentos de BL.               |
| Período                 | MONAT             | Indicar o período, caso seja relevante apenas para um período especifico (normalmente é necessário quando o campo Exercicio é "N-1")                                                           |
| Exercício               | EXERCICIO         | Indica se os dados para esta regra devem ser obtidos para o ano de execução ("N"), ano anterior ao de execução ("N-1") ou ano posterior ao de execução ("N+1") (este último nunca é utilizado) |
| Tipo de documento       | BLART             | Tipo de documento a ser utilizado ao fazer lançamento de BL para essa regra                                                                                                                    |
| Conta de contra-partida | CONTA_CONTRA_PART | Conta de contra-partida a ser utilizada ao fazer lançamento de BL para essa regra                                                                                                              |
| Inverte Sinal           | INVERTE_SINAL     | Indica se o sinal dos valores obtidos pelo MF /USDMT/FM_GET_CONTA_ZERO deve ser invertido ("X") ou não (" ")                                                                                   |
Exemplo de parametrização da tabela "Tabela REGR_ZERO.xlsx"

#### /USDMT/CONTAS_BL
No lançamento de documentos de BL pode haver a necessidade de lançar para várias chaves, e a tabela /USDMT/REGR_ZERO não permite isso. Nesses casos as várias contas a usar no lançamento, devem ser parametrizadas nesta tabela.
**Nota:** Esta tabela é suposto ser parametrizada por um funcional.

| Campo                   | Nome Técnico      | Função                                                                            |
| ----------------------- | ----------------- | --------------------------------------------------------------------------------- |
| Empresa                 | BUKRS             | Indicar a empresa relevante                                                       |
| Ano de                  | GJAHR_FROM        | Ano a partir do qual a parametrização é válida                                    |
| Ano até                 | GJAHR_TO          | Ano até quando a parametrização é válida                                          |
| ID Mapa                 | ID_MAPA           | Identificar o mapa: DODES ou DOREC                                                |
| Regra Mapa              | REGRA             | Código regra UNILEO                                                               |
| Conta do Razão          | CONTA             | Conta para o qual é feito o lançamento nos lançamentos de documentos de BL        |
| Conta de contra-partida | CONTA_CONTRA_PART | Conta de contra-partida a ser utilizada ao fazer lançamento de BL para essa regra |

#### /USDMT/CH_CRITIC
Por vezes existem chaves orçamentais com muita informação e não é possível extrair essa informação (no detalhe orçamental e na analise comparativa de regras de mapa), e nesses casos é necessário que a execução seja feita em background. Para isso deve ser utilizada esta tabela para indicar as chaves criticas, ou seja, as chaves orçamentais para as quais a seleção e processamento de dados devem ser feitos em background.
**Nota:** Esta tabela é suposto ser parametrizada por um funcional.

| Campo             | Nome Técnico | Função                                                                         |
| ----------------- | ------------ | ------------------------------------------------------------------------------ |
| Empresa           | BURKS        | Indicar a empresa relevante                                                    |
| Fundos            | GEBER        | Indicar o fundo relevante constituinte da chave orçamental crítica             |
| Item Financeiro   | FIPEX        | Indicar o item financeiro relevante constituinte da chave orçamental crítica   |
| Centro Financeiro | FISTL        | Indicar o centro financeiro relevante constituinte da chave orçamental crítica |

#### /USDMT/AREAF_XML
Nos ficheiros XML a enviar para a UNILEO, devem ser indicadas as áreas funcionais com 3 caracteres, no entanto em SAP, as áreas funcionais têm 4 caracteres, portanto existe a necessidade de mapear as áreas funcionais SAP com as correspondentes das UNILEO.

| Campo              | Nome Técnico | Função                                                    |
| ------------------ | ------------ | --------------------------------------------------------- |
| Área funcional     | FKBER        | Área funcional SAP                                        |
| Área funcional XML | FKBER_XML    | Área funcional correspondente na UNILEO, com 3 caracteres |


### Tabelas Dados
#### /USDMT/VAL_DODES
Onde ficam registados os dados do relatório DODES, que são exibidos ao executar a opção DODES no COCKPIT

#### /USDMT/VAL_DOREC
Onde ficam registados os dados do relatório DOREC, que são exibidos ao executar a opção DOREC no COCKPIT

#### /USDMT/DETALHE
Onde ficam registados os dados do detalhe orçamental nas execuções em background (programa /USDMT/CHAVE_DETALHE), para as chaves orçamentais que estão na tabela /USDMT/CH_CRITIC

#### /USDMT/AN_COMP_C
Onde ficam registados os dados da análise comparativa de regras de contas nas execuções em background (programa /USDMT/ANALISE_COMP), para as chaves orçamentais que estão na tabela /USDMT/CH_CRITIC

#### /USDMT/LANC_BL
Onde ficam registados os documentos de BL lançados através da ferramenta. Serve como log, e também para exibir os documentos numa cor diferente no cockpit, para que seja mais fácil identificá-los (aparecem com a cor azul no detalhe financeiro, e na análise de diferenças de regras de mapa).

#### /USDMT/RECL_LOG
Onde fica o log das reclassificações feitas através da ferramenta.

#### /USDMT/EXCECOES
Tabela onde ficam registadas as exceções novas. Apenas relevante se a opção "Novas Exceções Ativa?" estiver ativada na tabela /USDMT/ACT_FUNCT.

#### /USDMT/DOCS_EXC
Tabela onde ficam registadas as exceções antigas. Apenas relevante se a opção "Novas Exceções Ativa?" estiver desativada na tabela /USDMT/ACT_FUNCT.

### Módulos Função Detalhe Orçamental 
#### Gerais
- /USDMT/FM_RETENCOES - Obtém detalhe das retenções
- /USDMT/FM_RETENCOES_NAO_PAGAS - Obtém detalhe das retenções não pagas
- /USDMT/FM_TRANSF_FUNDOS - Obtém detalhe das transferências de fundos
#### DODES (Despesa)
- /USDMT/FM_D_CABIMENTOS - Obtém detalhe dos cabimentos
- /USDMT/FM_D_CATIVOS - Obtém detalhe dos cativos
- /USDMT/FM_D_CATIVOS_DESCATIVOS  - Obtém detalhe dos cativos/descativos
- /USDMT/FM_D_COMPROMISSOS - Obtém detalhe dos compromissos
- /USDMT/FM_D_COMPR_ASSUM_FUT_N1 - Obtém detalhe dos compromissos assumidos de anos futuros + 1
- /USDMT/FM_D_COMPR_ASSUM_FUT_N2 - Obtém detalhe dos compromissos assumidos de anos futuros + 2
- /USDMT/FM_D_COMPR_ASSUM_FUT_N3 - Obtém detalhe dos compromissos assumidos de anos futuros + 3
- /USDMT/FM_D_COMPR_ASSUM_FUT_N4 - Obtém detalhe dos compromissos assumidos de anos futuros + 4
- /USDMT/FM_D_COMPR_ASSUM_FUT_SE - Obtém detalhe dos compromissos assumidos de anos futuros seguintes
- /USDMT/FM_D_COMPR_TRANSITAR - Obtém detalhe dos compromissos a transitar
- /USDMT/FM_D_DESCATIVOS - Obtém detalhe dos descativos
- /USDMT/FM_D_DESPESAS_PAGAR - Obtém detalhe das despesas por pagar
- /USDMT/FM_D_DESP_PAGAS_BRUTAS - Obtém detalhe das despesas pagas brutas
- /USDMT/FM_D_DESP_PAGAS_LIQ_AA - Obtém detalhe das despesas pagas líquidas de anos anteriores
- /USDMT/FM_D_DESP_PAGAS_LIQ_COR - Obtém detalhe das despesas pagas líquidas do ano corrente
- /USDMT/FM_D_DESP_PAGAS_LIQ_TOT - Obtém detalhe das despesas pagas líquidas totais
- /USDMT/FM_D_DOT_CORRIGIDAS - Obtém detalhe das dotações corrigidas
- /USDMT/FM_D_DOT_DISPONIVEIS - Obtém detalhe das dotações disponíveis
- /USDMT/FM_D_OBRIGACOES - Obtém detalhe das obrigações
- /USDMT/FM_D_OBRIGACOES_TRANSIT - Obtém detalhe das obrigações a transitar
- /USDMT/FM_D_REP_ABAT_PAG_EMIT - Obtém detalhe das RAPs emitidas
- /USDMT/FM_D_REP_ABAT_PAG_REC - Obtém detalhe das RAPs recebidas
#### DOREC (Receita)
- /USDMT/FM_R_LIQ_ANULADAS - Obtém detalhe das liquidações anuladas
- /USDMT/FM_R_PREV_CORRIGIDAS - Obtém detalhe das previsões corrigidas
- /USDMT/FM_R_PREV_POR_LIQUIDAR - Obtém detalhe das previsões por liquidar
- /USDMT/FM_R_REC_COBR_ANT - Obtém detalhe das receitas por cobrar de anos anteriores
- /USDMT/FM_R_REC_COB_BRUTAS - Obtém detalhe das receitas cobradas brutas
- /USDMT/FM_R_REC_COB_FINAL_PER - Obtém detalhe da receita a cobrar no final do período
- /USDMT/FM_R_REC_COB_LIQ_ANT - Obtém detalhe da receita cobrada líquida de anos anteriores
- /USDMT/FM_R_REC_COB_LIQ_COR - Obtém detalhe da receita cobrada líquida do ano corrente
- /USDMT/FM_R_REC_COB_LIQ_TOT - Obtém detalhe da receita cobrada líquida total
- /USDMT/FM_R_REC_LIQUIDADAS - Obtém detalhe da receita liquidada
- /USDMT/FM_R_REEMB_EMIT - Obtém detalhe dos reembolsos emitidos
- /USDMT/FM_R_REEMB_EMIT_NAO_TRA - Obtém detalhe dos reembolsos emitidos não transitados
- /USDMT/FM_R_REEMB_EMIT_TRANSIT - Obtém detalhe dos reembolsos emitidos transitados
- /USDMT/FM_R_REEMB_PAGOS - Obtém detalhe dos reembolsos pagos
- /USDMT/FM_R_REEMB_PAGOS_AA  - Obtém detalhe dos reembolsos pagos de anos anteriores

### Módulos Função Detalhe Financeiro

- /USDMT/FM_GET_CONTA_ZERO - Obtém detalhe financeiro, através das contas do razão

### Programas Auxiliares

#### /USDMT/CHAVE_DETALHE
Quando uma chave orçamental é critica (está na tabela /USDMT/CH_CRITIC), o detalhe deve ser executado em background através deste programa e o resultado é gravado na tabela /USDMT/DETALHE.

####  /USDMT/ANALISE_COMP
Quando uma chave orçamental é critica (está na tabela /USDMT/CH_CRITIC), o análise comparativa de regras de contas deve ser executado em background através deste programa e o resultado é gravado na tabela /USDMT/AN_COMP_C.

#### /USDMT/MIGRAR_EXCECOES
Quando um cliente utilizou durante algum tempo as exceções antigos e depois passou a utilizar as exceções novas (/USDMT/ACT_FUNCT-NOVAS_EXC_ACTIVE preenchido), pode haver a necessidade de migrar as exceções que já existiam, e isso pode ser feito através deste programa.

### Exits
Na leitura do detalhe orçamental é possível usar código personalizado ao invés do código "standard" da ferramenta USDMT. Para tal foram adicionados pontos onde são chamados módulos de função Z, listados abaixo:

- ZUSDMTXD_CABIMENTOS_01 - Substitui os dados obtidos na seleção principal dos cabimentos
- ZUSDMTXD_CABIMENTOS_02 - Substitui os dados obtidos na seleção extra dos cabimentos (seleção das despesas por pagar)
- ZUSDMTXD_COMPROMISSOS_01 - Substitui os dados obtidos na seleção principal dos compromissos
- ZUSDMTXD_COMPROMISSOS_02 - Substitui os dados obtidos na seleção extra dos compromissos (seleção das despesas por pagar)
- ZUSDMTXD_DESPESAS_PAGAR_01 - Substitui os dados obtidos na seleção principal das despesas por pagar
- ZUSDMTXD_DESP_PAGAS_BRUTAS_01 (OBSOLETO) - Substitui os dados obtidos na seleção principal das despesas pagas brutas
- ZUSDMTXD_DESP_PAGAS_BRUTAS_02 (OBSOLETO) -Substitui os dados obtidos na seleção extra das despesas pagas brutas
- ZUSDMTXD_DESP_PAGAS_LIQ_AA_01 - Substitui os dados obtidos na seleção principal das despesas pagas líquidas de anos anteriores
- ZUSDMTXD_DESP_PAGAS_LIQ_COR_01 - Substitui os dados obtidos na seleção principal das despesas pagas líquidas do ano corrente
- ZUSDMTXD_OBRIGACOES_01 - Substitui os dados obtidos na seleção principal das obrigações
- ZUSDMTXD_OBRIGACOES_02 - Substitui os dados obtidos na seleção extra das obrigações (adiantamentos)
- ZUSDMTXD_REP_ABAT_PAG_EMIT_01 - Substitui os dados obtidos na seleção principal das RAPs emitidas
- ZUSDMTXR_LIQ_ANULADAS_01 - Substitui os dados obtidos na seleção principal das liquidações anuladas
- ZUSDMTXR_REC_COBR_ANT_01 - Substitui os dados obtidos na seleção principal da receita por cobrar de anos anteriores
- ZUSDMTXR_REC_COB_BRUTAS_01 (OBSOLETO) - Substitui os dados obtidos na seleção principal da receita cobrada bruta
- ZUSDMTXR_REC_COB_BRUTAS_02 (OBSOLETO) -Substitui os dados obtidos na seleção extra das receita cobrada bruta
- ZUSDMTXR_REC_COB_LIQ_ANT_01 - Substitui os dados obtidos na seleção principal da receita cobrada líquida de anos anteriores
- ZUSDMTXR_REC_COB_LIQ_COR_01 - Substitui os dados obtidos na seleção principal da receita cobrada líquida do ano corrente
- ZUSDMTXR_REC_LIQUIDADAS_01 - Substitui os dados obtidos na seleção principal da receita liquidada
- ZUSDMTXR_REEMB_EMIT_01 - Substitui os dados obtidos na seleção principal dos reembolsos emitidos
- ZUSDMTXR_REEMB_PAGOS_01 - Substitui os dados obtidos na seleção principal dos reembolsos pagos
- ZUSDMTX_RETENCOES_01 - Substitui os dados obtidos na seleção principal dos retenções
- ZUSDMTX_RETENCOES_NAO_PAGAS_01 - Substitui os dados obtidos na seleção principal dos retenções não pagas
- ZUSDMTXD_CATIVOS_SET_NAME - Permite utilizar outro set sem ser o predefinido ZTIPO_DOC_CATIVOS
- ZUSDMTXD_DESCATIVOS_SET_NAME - Permite utilizar outro set sem ser o predefinido ZTIPO_DOC_DESCATIVOS
- ZUSDMTXD_TRANS_FUNDOS_SET_NAME - Permite utilizar outro set sem ser os predefinidos ZPFM_TF_CORR (para ano corrente) e ZPFM_TF_AA (para anos anteriores)
- ZUSDMTX_TRATA_DADOS_FINAL - Substitui os dados já na tabela de output, já depois de terem sido tratados
- ZUSDMTX_LER_SOCIEDADE_PARCEIRA - Permite selecionar a sociedade parceira de outra forma, sem ser a predefinida da ferramenta

Exemplo exit ZUSDMTXR_REC_LIQUIDADAS_01:

```
FUNCTION ZUSDMTXR_REC_LIQUIDADAS_01.  
*"----------------------------------------------------------------------  
*"*"Interface local:  
*"  TABLES  
*"      T_FMIOI_FILTERED STRUCTURE  /USDMT/ST_FMIOI OPTIONAL  
*"      T_FMIFIIT_FILTERED STRUCTURE  /USDMT/ST_FMIFIIT OPTIONAL  
*"      T_DADOS STRUCTURE  /USDMT/ST_DOCS_MAPAS OPTIONAL  
*"----------------------------------------------------------------------  
    
  T_FMIFIIT_FILTERED[] = gt_fmifiit[].  
  
  PERFORM clear_ranges.  
  PERFORM add_wrttp USING 'I' 'EQ' '54' ''.  
  PERFORM add_wrttp USING 'I' 'EQ' '61' ''.  
*  PERFORM add_wrttp USING 'I' 'EQ' '66' ''.  
  PERFORM add_btart USING 'I' 'EQ' '0100' ''.  
  PERFORM add_btart USING 'I' 'EQ' '0600' ''.  
  PERFORM add_btart USING 'I' 'EQ' '0650' ''.  
  PERFORM add_rldnr USING 'I' 'EQ' '9A' ''.  
  
  PERFORM add_stats USING ''.  
  
  REFRESH gr_blart.  
  PERFORM add_etapa USING 'E' 'RNCC ' gv_bukrs ''.  
  
  PERFORM filter_fmifiit TABLES T_FMIFIIT_FILTERED.  
  
ENDFUNCTION.
```

Exemplo exit ZUSDMTXD_TRANS_FUNDOS_SET_NAME:

```
FUNCTION ZUSDMTXD_TRANS_FUNDOS_SET_NAME.  
*"----------------------------------------------------------------------  
*"*"Interface local:  
*"  EXPORTING  
*"     REFERENCE(E_SETNAME) TYPE  SETNAMENEW  
*"     REFERENCE(E_INVERTE) TYPE  /USDMT/INVERTE_SINAL  
*"----------------------------------------------------------------------  
  
  DATA: lt_ctm_rfc_call TYPE sys_callst, "Callstack Table  
        ls_ctm_rfc_call TYPE sys_calls. "Callstack Line  
  
  CALL FUNCTION 'SYSTEM_CALLSTACK'  
    IMPORTING  
      et_callstack = lt_ctm_rfc_call.  
  
  READ TABLE lt_ctm_rfc_call INTO ls_ctm_rfc_call INDEX 4.  
  IF sy-subrc EQ 0.  
  
    CASE ls_ctm_rfc_call-eventname.  
	      WHEN '/USDMT/FM_R_REEMB_EMIT' OR '/USDMT/FM_R_REEMB_PAGOS' OR '/USDMT/FM_R_REC_COB_LIQ_COR'.  
        e_setname = 'ZPFM_TF_REM'.  
  
      WHEN '/USDMT/FM_R_REC_LIQUIDADAS'.  
        e_setname = 'ZPFM_TF_NC'.  
        e_inverte = 'X'.  
  
      WHEN '/USDMT/FM_R_REC_COBR_ANT'.  
        e_setname = 'ZPFM_TF_NC_AA'.  
        e_inverte = 'X'.  
  
      WHEN '/USDMT/FM_R_LIQ_ANULADAS'.  
        e_setname = 'ZPFM_TF_12_13'.  
  
    ENDCASE.  
  
  ENDIF.  
    
ENDFUNCTION.
```


Exemplo exit ZUSDMTX_TRATA_DADOS_FINAL:

```
FUNCTION ZUSDMTX_TRATA_DADOS_FINAL.  
*"----------------------------------------------------------------------  
*"*"Interface local:  
*"  IMPORTING  
*"     REFERENCE(I_COLUNA) TYPE  /USDMT/COLUNA  
*"  TABLES  
*"      T_DADOS STRUCTURE  /USDMT/ST_DOCS_MAPAS  
*"----------------------------------------------------------------------  
  
  "Adiciona transferências de fundos adicionais  
  DATA: lt_fmioi      TYPE TABLE OF ty_fmioi,  
        lt_dados_aux  TYPE          /USDMT/TT_DOCS_MAPAS.  
  
  DATA: lv_inverte(1),  
        lv_inverte_aux(1).  
  
  IF gv_mapa EQ 'DODES'.  
    lv_inverte = 'X'.  
  ENDIF.  
  
  PERFORM clear_ranges.  
  PERFORM add_rldnr USING 'I' 'EQ' '9B' ''.  
  PERFORM add_wrttp USING 'I' 'EQ' '64' ''.  
  
  CASE i_coluna.  
    WHEN 'REEMB_RESTIT_EMIT' OR 'REEMB_RESTIT_PAGOS'.  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = lv_inverte.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_REM'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
    WHEN 'REC_COB_LIQ_CORRENTE'.  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = 'X'.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_REM'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = 'X'.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_NC'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
    WHEN 'REC_LIQUIDADAS'.  
*      REFRESH: lt_dados_aux, gr_bl_doc_type.  
*      lt_fmioi = gt_fmioi.  
*      lv_inverte_aux = 'X'.  
*      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_NC'.  
*      PERFORM filter_fmioi TABLES lt_fmioi.  
*      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
*                                              lt_dados_aux  
*                                      USING   lv_inverte_aux  
*                                              'TF'.  
*      APPEND LINES OF lt_dados_aux TO t_dados.  
  
    WHEN 'LIQ_ANULADAS'.  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = lv_inverte.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_REM'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = lv_inverte.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_NC'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = lv_inverte.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_NC_AA'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
    WHEN 'REC_COB_LIQ_ANTERIOR'.  
      REFRESH: lt_dados_aux, gr_bl_doc_type.  
      lt_fmioi = gt_fmioi.  
      lv_inverte_aux = 'X'.  
      PERFORM add_tipo_doc_tf_aa USING '' 'ZPFM_TF_NC_AA'.  
      PERFORM filter_fmioi TABLES lt_fmioi.  
      PERFORM fill_output_table_fmioi TABLES  lt_fmioi  
                                              lt_dados_aux  
                                      USING   lv_inverte_aux  
                                              'TF'.  
      APPEND LINES OF lt_dados_aux TO t_dados.  
  
  ENDCASE.  
  
ENDFUNCTION.
```

Também foi criado um exit adicional, que permite definir os semáforos/icones na ALV principal do DODES e DOREC. Alguns clientes têm regras diferentes, portanto apenas o código "standard" deixou de dar resposta em algumas situações.

- ZUSDMTX_DODES_DOREC_ICONS - Permite ajustar os ícones nos relatórios DODES e DOREC

Se o pressuposto for que o exit seja usado em vez do código "standard", a flag C_EXIT_ATIVO deve ser preenchida no módulo de função, para que o código standard seja ignorado. Para além disso deve ser incluído o código necessário para ajustar os ícones de acordo com as necessidades do cliente.
Exemplo de implementação do exit:


```
FUNCTION ZUSDMTX_DODES_DOREC_ICONS.  
*"----------------------------------------------------------------------  
*"*"Interface local:  
*"  IMPORTING  
*"     REFERENCE(I_ID_MAPA) TYPE  /USDMT/ID_MAPA  
*"     REFERENCE(I_CONTAS_OPT) TYPE  CHAR1 OPTIONAL  
*"  EXPORTING  
*"     REFERENCE(C_EXIT_ATIVO) TYPE  XFLAG  
*"  CHANGING  
*"     REFERENCE(T_DODES) TYPE  /USDMT/TT_DODES_ALV OPTIONAL  
*"     REFERENCE(T_DOREC) TYPE  /USDMT/TT_DOREC_ALV OPTIONAL  
*"----------------------------------------------------------------------  
  
  FIELD-SYMBOLS:  <fs_dodes> TYPE /usdmt/st_dodes_alv,  
                  <fs_dorec> TYPE /usdmt/st_dorec_alv.  
  
  DATA: ls_dodes TYPE /usdmt/st_dodes_alv,  
        ls_dorec TYPE /usdmt/st_dorec_alv.  
  
  DATA: lv_exc_rc11(1),  
        lv_tot_col    TYPE /USDMT/MONT_MAPAS,  
        lv_tot_regra  TYPE /USDMT/MONT_MAPAS.  
  
  
  C_EXIT_ATIVO = 'X'. "Prenche flag, para depois não executar o codigo standard  
  
  
  IF i_id_mapa EQ 'DODES'.  
  
    "Valida se a regra 11 é excluida da validação do semaforo  
    LOOP AT T_DODES INTO ls_dodes WHERE fistl NE 'ZTOTAL'.  
      lv_tot_col = lv_tot_col + ls_dodes-desp_pagar_per_ant.  
    ENDLOOP.  
    READ TABLE T_DODES INTO ls_dodes WITH KEY fistl = 'ZTOTAL'.  
    lv_tot_regra = ls_dodes-rc11.  
    IF abs( lv_tot_col ) EQ abs( lv_tot_regra ).  
      lv_exc_rc11 = 'X'.  
    ENDIF.  
  
    LOOP AT T_DODES ASSIGNING <fs_dodes>.  
      IF i_contas_opt IS INITIAL.  
        IF  <fs_dodes>-rm1    NE 0 OR  
            <fs_dodes>-rm2    NE 0 OR  
            <fs_dodes>-rm4    NE 0 OR  
            <fs_dodes>-rm3    NE 0 OR  
            <fs_dodes>-rm5    NE 0 OR  
            <fs_dodes>-rm7    NE 0 OR  
            <fs_dodes>-rm8    NE 0 OR  
            <fs_dodes>-rm6_1  NE 0 OR  
            <fs_dodes>-rm6_2  NE 0 OR  
            <fs_dodes>-rm6_3  NE 0 OR  
            <fs_dodes>-rm6_4  NE 0 OR  
            <fs_dodes>-rm6_5  NE 0 OR  
            <fs_dodes>-dot_corrigidas           LT 0 OR  
            <fs_dodes>-desp_pagar_per_ant       LT 0 OR  
            <fs_dodes>-cativos                  LT 0 OR  
            <fs_dodes>-descativos               LT 0 OR  
            <fs_dodes>-cativo_descativo         LT 0 OR  
            <fs_dodes>-cabimentos               LT 0 OR  
            <fs_dodes>-compromissos             LT 0 OR  
            <fs_dodes>-dot_disponiveis          LT 0 OR  
            <fs_dodes>-obrigacoes               LT 0 OR  
            <fs_dodes>-desp_pag_brutas          LT 0 OR  
            <fs_dodes>-rep_abat_pag_emitidas    LT 0 OR  
            <fs_dodes>-rep_abat_pag_rec         LT 0 OR  
            <fs_dodes>-desp_pag_liq_anterior    LT 0 OR  
            <fs_dodes>-desp_pag_liq_corrente    LT 0 OR  
            <fs_dodes>-desp_pag_liq_total       LT 0 OR  
            <fs_dodes>-compromisso_transitar    LT 0 OR  
            <fs_dodes>-obrigacoes_por_pagar     LT 0 OR  
            <fs_dodes>-compr_assum_fut_nm1      LT 0 OR  
            <fs_dodes>-compr_assum_fut_nm2      LT 0 OR  
            <fs_dodes>-compr_assum_fut_nm3      LT 0 OR  
            <fs_dodes>-compr_assum_fut_nm4      LT 0 OR  
            <fs_dodes>-compr_assum_fut_seg      LT 0 OR  
            <fs_dodes>-obrig_period_futuro_n1   LT 0 OR  
            <fs_dodes>-obrig_period_futuro_n2   LT 0 OR  
            <fs_dodes>-obrig_period_futuro_n3   LT 0 OR  
            <fs_dodes>-obrig_period_futuro_n4   LT 0 OR  
            <fs_dodes>-obrig_period_seguintes   LT 0.  
  
          <fs_dodes>-icon = '@0A@'. "Vermelho  
  
        ELSEIF  <fs_dodes>-rc12   NE 0 OR  
                ( <fs_dodes>-rc11   NE 0 AND lv_exc_rc11 IS INITIAL ) OR  
                <fs_dodes>-rc13   NE 0 OR  
                <fs_dodes>-rc14   NE 0 OR  
                <fs_dodes>-rc16   NE 0 OR  
                <fs_dodes>-rc17   NE 0 OR  
                <fs_dodes>-rc15   NE 0 OR  
                <fs_dodes>-rc18   NE 0 OR  
                <fs_dodes>-rc19   NE 0 OR  
                <fs_dodes>-rc20   NE 0 OR  
                <fs_dodes>-rc21   NE 0 OR  
                <fs_dodes>-rc22   NE 0 OR  
                <fs_dodes>-rc23   NE 0 OR  
                <fs_dodes>-rc24   NE 0 OR  
                <fs_dodes>-rc25   NE 0 OR  
                <fs_dodes>-rc26   NE 0 OR  
                <fs_dodes>-rc27   NE 0 OR  
                <fs_dodes>-rc28   NE 0 OR  
                <fs_dodes>-rc29   NE 0 OR  
                <fs_dodes>-rc30   NE 0 OR  
                <fs_dodes>-rc31   NE 0 OR  
                <fs_dodes>-rc32   NE 0 OR  
                <fs_dodes>-rc33   NE 0 OR  
                <fs_dodes>-rc34   NE 0 OR  
                <fs_dodes>-rc35   NE 0.  
  
          IF i_contas_opt IS INITIAL.  
            <fs_dodes>-icon = '@09@'. "Amarelo  
          ELSE.  
            <fs_dodes>-icon = '@08@'. "Verde  
          ENDIF.  
        ELSE.  
          <fs_dodes>-icon = '@08@'. "Verde  
        ENDIF.  
        IF <fs_dodes>-fistl EQ 'ZTOTAL'.  
          <fs_dodes>-icon = '@08@'. "Verde  
        ENDIF.  
  
      ELSE.  
        IF  <fs_dodes>-rm1    NE 0 OR  
            <fs_dodes>-rm2    NE 0 OR  
            <fs_dodes>-rm4    NE 0 OR  
            <fs_dodes>-rm3    NE 0 OR  
            <fs_dodes>-rm5    NE 0 OR  
            <fs_dodes>-rm7    NE 0 OR  
            <fs_dodes>-rm8    NE 0 OR  
            <fs_dodes>-rm6_1  NE 0 OR  
            <fs_dodes>-rm6_2  NE 0 OR  
            <fs_dodes>-rm6_3  NE 0 OR  
            <fs_dodes>-rm6_4  NE 0 OR  
            <fs_dodes>-rm6_5  NE 0 OR  
            <fs_dodes>-CONTAS_12  LT 0 OR  
            <fs_dodes>-CONTAS_11  LT 0 OR  
            <fs_dodes>-CONTAS_13  LT 0 OR  
            <fs_dodes>-CONTAS_14  LT 0 OR  
            <fs_dodes>-CONTAS_16  LT 0 OR  
            <fs_dodes>-CONTAS_17  LT 0 OR  
            <fs_dodes>-CONTAS_15  LT 0 OR  
            <fs_dodes>-CONTAS_18  LT 0 OR  
            <fs_dodes>-CONTAS_19  LT 0 OR  
            <fs_dodes>-CONTAS_20  LT 0 OR  
            <fs_dodes>-CONTAS_21  LT 0 OR  
            <fs_dodes>-CONTAS_22  LT 0 OR  
            <fs_dodes>-CONTAS_23  LT 0 OR  
*            <fs_dodes>-desp_pag_liq_total       LT 0 OR  
            <fs_dodes>-CONTAS_24  LT 0 OR  
            <fs_dodes>-CONTAS_25  LT 0 OR  
            <fs_dodes>-CONTAS_26  LT 0 OR  
            <fs_dodes>-CONTAS_27  LT 0 OR  
            <fs_dodes>-CONTAS_28  LT 0 OR  
            <fs_dodes>-CONTAS_29  LT 0 OR  
            <fs_dodes>-CONTAS_30  LT 0 OR  
            <fs_dodes>-CONTAS_31  LT 0 OR  
            <fs_dodes>-CONTAS_32  LT 0 OR  
            <fs_dodes>-CONTAS_33  LT 0 OR  
            <fs_dodes>-CONTAS_34  LT 0 OR  
            <fs_dodes>-CONTAS_35  LT 0.  
  
          <fs_dodes>-icon = '@0A@'.  
  
        ELSE.  
          <fs_dodes>-icon = '@08@'. "Verde  
        ENDIF.  
        IF <fs_dodes>-fistl EQ 'ZTOTAL'.  
          <fs_dodes>-icon = '@08@'. "Verde  
        ENDIF.  
      ENDIF.  
  
      IF <fs_dodes>-fistl EQ 'ZTOTAL'.  
        <fs_dodes>-line_color = 'C310'.  
*      ELSE.  
*        IF <fs_dodes>-chave_mapa EQ ''.  
*          <fs_dodes>-line_color = 'C700'.  
*        ENDIF.  
      ENDIF.  
    ENDLOOP.  
  
    "Elimina linhas que não são chave de mapa e têm semaforo verde.  
    DELETE T_DODES  WHERE fistl       NE 'ZTOTAL' AND  
                          icon        EQ '@08@'   AND  
                          chave_mapa  EQ ''.  
  
  ELSEIF i_id_mapa EQ 'DOREC'.  
    LOOP AT T_DOREC ASSIGNING <fs_dorec>.  
      IF i_contas_opt IS INITIAL.  
        IF      "<fs_dorec>-RM1    NE 0 OR  
                <fs_dorec>-rm2    NE 0 OR  
                <fs_dorec>-rm3    NE 0 OR  
                <fs_dorec>-rm4    NE 0 OR  
                <fs_dorec>-rm5    NE 0 OR  
                <fs_dorec>-prev_corrigidas          LT 0 OR  
                <fs_dorec>-rec_cobr_anteriores      LT 0 OR  
                <fs_dorec>-rec_liquidadas           LT 0 OR  
                <fs_dorec>-liq_anuladas             LT 0 OR  
*                <fs_dorec>-rec_cobbrutas            LT 0 OR  
                <fs_dorec>-reemb_restit_emit        LT 0 OR  
                <fs_dorec>-reemb_restit_pagos       LT 0 OR  
*                <fs_dorec>-rec_cob_liq_anterior     LT 0 OR  
*                <fs_dorec>-rec_cob_liq_corrente     LT 0 OR  
*                <fs_dorec>-rec_cob_liq_total        LT 0 OR  
                <fs_dorec>-rec_cobr_final_peri      LT 0 OR  
                <fs_dorec>-liq_fut_n1               LT 0 OR  
                <fs_dorec>-liq_fut_n2               LT 0 OR  
                <fs_dorec>-liq_fut_n3               LT 0 OR  
                <fs_dorec>-liq_fut_n4               LT 0 OR  
                <fs_dorec>-liq_fut_seg              LT 0.  
  
          <fs_dorec>-icon = '@0A@'.  
  
        ELSEIF  <fs_dorec>-rc6    NE 0 OR  
                <fs_dorec>-rc7    NE 0 OR  
                <fs_dorec>-rc8    NE 0 OR  
                <fs_dorec>-rc9    NE 0 OR  
                <fs_dorec>-rc10   NE 0 OR  
                <fs_dorec>-rc11   NE 0 OR  
                <fs_dorec>-rc12   NE 0 OR  
                <fs_dorec>-rc13   NE 0 OR  
                <fs_dorec>-rc14   NE 0 OR  
                <fs_dorec>-rc15   NE 0 OR  
                <fs_dorec>-rc16   NE 0 OR  
                <fs_dorec>-rc18   NE 0 OR  
                <fs_dorec>-rc19   NE 0 OR  
                <fs_dorec>-rc20   NE 0 OR  
                <fs_dorec>-rc21   NE 0 OR  
                <fs_dorec>-rc22   NE 0.  
  
          IF i_contas_opt IS INITIAL.  
            <fs_dorec>-icon = '@09@'. "Amarelo  
          ELSE.  
            <fs_dorec>-icon = '@08@'. "Verde  
          ENDIF.  
        ELSE.  
          <fs_dorec>-icon = '@08@'. "Verde  
        ENDIF.  
        IF <fs_dorec>-fistl EQ 'ZTOTAL'.  
          <fs_dorec>-icon = '@08@'. "Verde  
        ENDIF.  
  
      ELSE.  
        IF      "<fs_dorec>-RM1    NE 0 OR  
                <fs_dorec>-rm2    NE 0 OR  
                <fs_dorec>-rm3    NE 0 OR  
                <fs_dorec>-rm4    NE 0 OR  
                <fs_dorec>-rm5    NE 0 OR  
                <fs_dorec>-CONTAS_6   LT 0 OR  
                <fs_dorec>-CONTAS_8   LT 0 OR  
                <fs_dorec>-CONTAS_9   LT 0 OR  
                <fs_dorec>-CONTAS_10  LT 0 OR  
                <fs_dorec>-CONTAS_11  LT 0 OR  
                <fs_dorec>-CONTAS_12  LT 0 OR  
                <fs_dorec>-CONTAS_13  LT 0 OR  
                <fs_dorec>-CONTAS_14  LT 0 OR  
                <fs_dorec>-CONTAS_15  LT 0 OR  
*                <fs_dorec>-rec_cob_liq_total        LT 0 OR  
                <fs_dorec>-CONTAS_16  LT 0 OR  
                <fs_dorec>-CONTAS_18  LT 0 OR  
                <fs_dorec>-CONTAS_19  LT 0 OR  
                <fs_dorec>-CONTAS_20  LT 0 OR  
                <fs_dorec>-CONTAS_21  LT 0 OR  
                <fs_dorec>-CONTAS_22  LT 0.  
  
          <fs_dorec>-icon = '@0A@'.  
  
        ELSE.  
          <fs_dorec>-icon = '@08@'. "Verde  
        ENDIF.  
        IF <fs_dorec>-fistl EQ 'ZTOTAL'.  
          <fs_dorec>-icon = '@08@'. "Verde  
        ENDIF.  
      ENDIF.  
  
      IF <fs_dorec>-fistl EQ 'ZTOTAL'.  
        <fs_dorec>-line_color = 'C310'.  
*      ELSE.  
*        IF <fs_dorec>-chave_mapa EQ ''.  
*          <fs_dorec>-line_color = 'C700'.  
*        ENDIF.  
      ENDIF.  
  
    ENDLOOP.  
  
    "Elimina linhas que não são chave de mapa e têm semaforo verde.  
    DELETE T_DOREC  WHERE fistl       NE 'ZTOTAL' AND  
                          icon        EQ '@08@'   AND  
                          chave_mapa  EQ ''.  
  
  ENDIF.  
  
  
ENDFUNCTION.
```


## DFC
Esta opção executa o relatório que permite fazer a comparação entre os valores DFC (Demonstração de Fluxos de Caixa) e a orçamental. 

**Nota:** Existem duas versões do relatório DFC, nesta opção é utilizada a mais recente. O normal será ter apenas uma das versões ativas (na tabela /USDMT/ACT_FUNCT). Qual deve ser usada irá depender do cliente.

Programa: /USDMT/DFC_FI_ORC

É possível usar um programa criado pelo cliente em vez do "standard" recorrendo ao exit ZUSDMTX_DFC_ORC.
Exemplo de implementação do exit:
```
FUNCTION ZUSDMTX_DFC_ORC.  
*"----------------------------------------------------------------------  
*"*"Interface local:  
*"  IMPORTING  
*"     REFERENCE(I_BUKRS) TYPE  BUKRS OPTIONAL  
*"     REFERENCE(I_GJAHR) TYPE  GJAHR OPTIONAL  
*"     REFERENCE(I_MONAT_INI) TYPE  MONAT OPTIONAL  
*"     REFERENCE(I_MONAT_FIM) TYPE  MONAT OPTIONAL  
*"     REFERENCE(I_MT_IVA) TYPE  DMBTR OPTIONAL  
*"     REFERENCE(I_ALL) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_DOC) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_MONT) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_RECUR) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_TIMES) TYPE  /USDMT/NUM_EXEC OPTIONAL  
*"     REFERENCE(I_TABELA) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_LER) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_CARR) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_JOB_NAME) TYPE  BTCJOB OPTIONAL  
*"     REFERENCE(I_JOB_NUMBER) TYPE  BTCJOBCNT OPTIONAL  
*"     REFERENCE(I_DFC_OLD) TYPE  CHAR1 OPTIONAL  
*"     REFERENCE(I_CHECK_ATIVO) TYPE  CHAR1 OPTIONAL  
*"  EXPORTING  
*"     REFERENCE(C_EXIT_ATIVO) TYPE  XFLAG  
*"     REFERENCE(C_DFC_OLD_ATIVO) TYPE  XFLAG  
*"----------------------------------------------------------------------  
  
  DATA: lr_monat  TYPE RANGE OF monat,  
        lrs_monat LIKE LINE OF  lr_monat.  
  
  IF i_dfc_old IS INITIAL.  
    C_EXIT_ATIVO = 'X'.  
  ELSE.  
    C_EXIT_ATIVO = 'X'.  
  ENDIF.  
*  C_DFC_OLD_ATIVO = 'X'.  
  
  IF i_check_ativo IS INITIAL.  
  
    lrs_monat-sign    = 'I'.  
    lrs_monat-low     = i_monat_ini.  
    IF i_monat_fim IS INITIAL.  
      lrs_monat-option  = 'EQ'.  
    ELSE.  
      lrs_monat-option  = 'BT'.  
      lrs_monat-high    = i_monat_fim.  
    ENDIF.  
    APPEND lrs_monat TO lr_monat.  
  
    IF i_dfc_old IS INITIAL.  
  
     IF i_job_number IS INITIAL.  
  
       SUBMIT zpsm_dfc_fi_orc_v2 WITH p_bukrs  =   i_bukrs  
                                 WITH p_gjahr  =   i_gjahr  
                                 WITH s_monat  IN  lr_monat  
                                 WITH p_recur  =   i_recur  
                                 WITH p_times  =   i_times  
                                 WITH p_tabela =   i_tabela  
                                 WITH r_ler    =   i_ler  
                                 WITH r_carr   =   i_carr  
                                 AND RETURN.  
  
     ELSE.  
  
       SUBMIT zpsm_dfc_fi_orc_v2 WITH p_bukrs  =   i_bukrs  
                                 WITH p_gjahr  =   i_gjahr  
                                 WITH s_monat  IN  lr_monat  
                                 WITH p_recur  =   i_recur  
                                 WITH p_times  =   i_times  
                                 WITH p_tabela =   i_tabela  
                                 WITH r_ler    =   i_ler  
                                 WITH r_carr   =   i_carr  
                                 VIA JOB i_job_name  
                                 NUMBER  i_job_number  
                                 AND RETURN.  
  
  
     ENDIF.  
   
   ELSE.  
     IF i_job_number IS INITIAL.  
  
       SUBMIT zpsm_dfc_fi_orc WITH p_bukrs  =   i_bukrs  
                              WITH p_gjahr  =   i_gjahr  
                              WITH s_monat  IN  lr_monat  
                              WITH p_mt_iva =   i_mt_iva  
                              WITH p_all    =   i_all  
                              WITH p_doc    =   i_doc  
                              WITH p_mont   =   i_mont  
                              WITH p_tabela =   i_tabela  
                              WITH r_ler    =   i_ler  
                              WITH r_carr   =   i_carr  
                              AND RETURN.  
  
     ELSE.  
  
       SUBMIT zpsm_dfc_fi_orc WITH p_bukrs  =   i_bukrs  
                              WITH p_gjahr  =   i_gjahr  
                              WITH s_monat  IN  lr_monat  
                              WITH p_mt_iva =   i_mt_iva  
                              WITH p_all    =   i_all  
                              WITH p_doc    =   i_doc  
                              WITH p_mont   =   i_mont  
                              WITH p_tabela =   i_tabela  
                              WITH r_ler    =   i_ler  
                              WITH r_carr   =   i_carr  
                              VIA JOB i_job_name  
                              NUMBER  i_job_number  
                              AND RETURN.  
  
  
     ENDIF.  
   ENDIF.  
  
  ENDIF.  
  
ENDFUNCTION.
```


## DFC Antigo
Esta opção executa o relatório que permite fazer a comparação entre os valores DFC (Demonstração de Fluxos de Caixa) e a orçamental. 

**Nota:** Existem duas versões do relatório, nesta opção é utilizada a mais antiga. O normal será ter apenas uma das versões ativas (na tabela /USDMT/ACT_FUNCT). Qual deve ser usada irá depender do cliente.

Programa: /USDMT/DFC_FI_ORC_OLD

Tal como no relatório DFC é possível usar um programa criado pelo cliente em vez do "standard" recorrendo ao mesmo exit, ZUSDMTX_DFC_ORC, utilizando o parâmetro I_DFC_OLD, para distinguir entre a versão nova e antiga.


## DFC Rubrica/Item Financeiro
Esta opção executa o relatório que permite fazer a comparação entre os valores DFC (Demonstração de Fluxos de Caixa) e a orçamental, com os valores agregados por rubricas (intervalos de itens financeiros).

Programa: /USDMT/RUBR_DFC_ITEM_FIN

É possível usar um programa criado pelo cliente em vez do "standard" recorrendo ao exit ZUSDMTX_DFC_RUBRICA.

## OT
Esta opção executa o relatório que permite fazer a comparação entre os valores OT (Operações de Tesouraria) e a orçamental.

Programa: /USDMT/OT_FI_ORC


---
# ⚙️ Instalação e configuração

## 1. Adicionar namespace /USDMT/ no sistema de destino

Ir à transação SE03 -> Exibir/Modificar conjuntos de nomes e adicionar namespace /USDMT/
![[USDMT - Adicionar namespace no destino.png]]

De seguida, entrar no namespace e definir a função como costumizing "C" e adicionar a licença de reparação (ver o código da licença no Vaultwarden)
![[USDMT - Licenca reparacao namespace.png]]

Depois têm que se definir o namespace /USDMT/ como modificável. Para isso ir à transação SE03 -> Definir opções de modificação do sistema
![[USDMT - Definir namespace modificavel.png]]

## 2. Importar objetos no sistema de destino

### Método 1: Tradicional

No sistema de origem:
1. Criar uma ordem de transporte de cópias
2. Adicionar à OT todos os objetos do pacote /USDMT/USDMT
3. Adicionar à OT todos os objetos do pacote ZUSDMT_EXITS 
4. Incluir layouts da ALV (/DODES, /DOREC, /VAL_DODES e /VAL_DOREC) da ferramenta na OT
5. Liberar a OT
6. Fazer download do ficheiros DATA e COFILES

No sistema de destino:
1. Carregar ficheiros DATA e COFILES
2. Importar a OT no ambiente de desenvolvimento

### Método 2: ABAP Git 

**Nota:** Este método só pode ser utilizado caso a ferramenta ABAP Git esteja instalada tanto no sistema de origem como no sistema de destino

No sistema de origem:
1. Fazer download do pacote /USDMT/USDMT utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)
2. Fazer download do pacote ZUSDMT_EXITS utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)

No sistema de destino:
1. Fazer upload do pacote /USDMT/USDMT utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)
2. Fazer upload do pacote ZUSDMT_EXITS utilizando a ferramenta ABAP Git (ZABAPGIT_STANDALONE)

## 3. Alterar camada de transporte dos pacotes /USDMT/USDMT e ZUSDMT_EXITS

Alterar camada de transporte do pacote /USDMT/USDMT para um válido no sistema de destino, na transação SE21

## 4. Parametrizar tabelas (Ambientes de desenvolvimento, qualidade e produção)

- Parametrizar tabela /USDMT/ACT_FUNCT - Consultor ABAP
- Parametrizar tabela /USDMT/FUNC_ESP - Consultor Funcional
- Parametrizar tabela /USDMT/AREA_FUNC - Consultor Funcional
- Parametrizar tabela /USDMT/REGR_ZERO (ver exemplo da parametrização no ficheiro "Tabela REGR_ZERO.xlsx") - Consultor Funcional 
- Parametrizar tabela /USDMT/CONTAS_BL (se relevante para o cliente) - Consultor funcional
- Parametrizar tabela /USDMT/FM_COLS (Ver exemplo da parametrização no ficheiro "Tabela FM_COLS.xlsx") - Consultor ABAP
- Parametrizar tabela /USDMT/FORMULAS - Consultor ABAP
- Parametrizar tabela /USDMT/ALV_FIELD para DODES e DOREC - Consultor ABAP

## 5. Criar layouts para ALV

**Nota:** Este passo só é necessário fazer caso os layouts não tenham sido exportados do sistemas de origem e importados no sistema de destino.

Criar layouts /DODES, /DOREC, /VAL_DODES e /VAL_DOREC para o cockpit (copiar de um cliente onde a ferramenta já esteja implementada) (Consultor Funcional)

## 6. Criar PARAMETER ID com o nome /USDMT/ID_MAPA

Criar PARAMETER ID (tabela TPARA) com o nome /USDMT/ID_MAPA

---

# 📎Anexos

**Nota:** Se não for possível abrir diretamente os anexos clicando nos links abaixo, ou se os links não estiverem visíveis, é possível encontrar os anexos na pasta "anexos".


Exemplo parametrização tabela /USDMT/FM_COLS: ![[Tabela FM_COLS.xlsx]]

Exemplo parametrização tabela /USDMT/REGR_ZERO: ![[Tabela REGR_ZERO.xlsx]]


