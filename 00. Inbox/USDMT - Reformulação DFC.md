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


1. Match Direto - Match Direto
2. Tratar documentos de compensação - Compensação / Compensação - Diferenças nos documentos de compensação
    1. Trata documentos de compensação de forma recursiva - Compensação Recursivo / Compensação Recursivo - Diferenças nos documentos de compensação
3. Match direto DFC e Orçamental com diferença de montante - Match Direto com Diferença de Montante
4. Match por valor - Match feito por valor 
5. Tratar documentos orçamentais que sobram - Documentos Orçamentais Restantes - Compensação só pela orçamental / Documentos Orçamentais Restantes
6. Tratar documento DFC que sobram - Documentos DFC Restantes - Não existe documento na orçamental
7. Documentos integração vencimentos - Documentos Integração Vencimentos



Passo 1 - Match direto DFC e Orçamental  
Documentos iguais e montante igual

Passo 2 - Trata documentos KP  
Faz match entre documentos DFC e orçamental mas com montante  
absoluto maior no lado da orçamental. Para esses casos verifica  
se o documento N+1 ou N-1 está no lado do DFC por tratar, e se  
estiver e o montante dele for igual à diferença dos documentos que  
se estão a comparar, junta-os todos no mesmo grupo

Passo 2.1 - Trata documentos KP - Quando tem vários pagamentos  
Faz match entre documentos DFC e orçamental mas com montante  
absoluto maior no lado da orçamental. Para esses casos verifica  
todos os documentos pagos e junta todos no mesmo grupo

Passo 3 - Tratar documentos de IVA Z9  
Para todos os documentos da orçamental do tipo ‘SA’ que não  
tenham tido match direto, vamos tratar os que têm o  
KNBELNR = intervalo de documento do Z9.  
- Primeiro será necessário ir aos documentos Z9 ler o campo  XBLNR-BKPF (que indicará o doc original + ano)  
*  Com o número do documento original será necessário ler o  campo BSEG-AUGBL (que indicará o documento KZ que estará  na ferramenta a amarelo)  
*  Depois será necessário na ferramenta ler, entre os KZ a amarelo, aqueles que foram atrás mapeados e comparar o  valor do mesmo com o valor dos docs que tenham esse  nr doc no campo AUGBL  
*  Se o montante dos docs Kz na ferramenta for totalmente justificado pelos docs com esse doc no campo AUGBL o  semáforo para esse KZ e para o doc Z9 deve passar a verde, caso contrário deve permanecer amarelo e  vermelho, respetivamente  

Passo 4 - Tratar documentos de compensação  
Para cada documento do DFC que sobrou, vamos a BSEG, ver os  documentos de compensação, que sejam diferentes dele próprio,  que sejam linhas K ou D ou S com contas de HR. A data de  compensação tem de estar compreendida nas datas de análise do mapa.  Colocamos numa tabela interna repetindo o documento de DFC nas  várias linhas e colocando os documentos de compensação, com um ID.  O valor será o do doc DFC e não se pode repetir nas linhas.  No seguinte documento de DFC fazer o mesmo procedimento, mas se  este documento tiver algum documento de compensação que já esteja "  na tabela, então teria de ficar com o mesmo ID.  Ao terminar, vai então percorrer esta tabela, por ID de grupo,  ler na ORC_VO os documentos de compensação e totalizar por ID de  grupo. Se o valor for igual, estas linhas ficavam verdes, se fosse  diferente ficava amarelo com o comentário ‘Diferenças nos documentos  de compensação. (se fosse possível e para facilitar os testes, ao  clicar nestas linhas, podia passar para a tabela interna onde estão  os documentos de compensação para se ver o detalhe e perceber o  que falhou).  Para a ALV passava o doc de DFC, os DOC de ORC_VO, e o ID de grupo.

Passo 4.1 - Trata documentos de compensação de forma recursiva

Passo 5 - Match direto DFC e Orçamental com diferença de montante

Passo 6 - Match por valor  
Fazer match de documentos DFC e ORC com montante igual e com  apenas uma ocorrencia para esse montante

Passo 7 - Tratar documentos orçamentais que sobram  
Os documentos que sobram do lado da orçamental verificar se alguns se compensam entre si, que são faturas e notas de crédito compensadas, ou encontro de contras entre clientes e fornecedores.  Estes devem totalizar ‘zero’ por isso ficam com verde, na descrição ‘Compensação só pela orçamental’.

Passo 8 - Tratar documento DFC que sobram  
Dos documentos que sobram do lado do DFC, ficam com a mensagem ‘Não existe documento na orçamental’

Passo 9 - Documentos integração vencimentos