---
title: IP - USDMT - DFC
updated: 2024-10-06 10:50
created: 2022-01-07 11:51:55Z
author: André Luz
tags:
  - ip
  - usdmt
---

Tabelas FLQ*
FLQITEMFI

* * *

Mapeamento de documentos DFC <> Orçamental

1. Adiciona documentos do DFC à tabela da ALV (collect sem item do documento) - 321

2. Na tabela da ALV, faz o mapeamento direto com os documentos orçamentais KN - 331

3. Trata as linhas da tabela da ALV que ainda não têm documento orçamental preenchido.  - 341

    1. Para cada linha da ALV sem documento orçamental preenchido, vai percorrer a tabela dos documentos orçamentais que sobraram no passo anterior que tenham o VOBELNR igual ao documento do DFC. Adiciona o KNBELNR corresponde dessas linhas a um range (GR_KNBELNR).

    2. De seguinda percorre a tabela dos documentos orçamentais para as linhas que tenham o KNBELNR no range criado anteriormente (GR_KNBELNR), e adiciona os VOBELNR dessas linhas a um outro range (GR_VOBELNR)

    3. Verifica se algum dos documentos do range GR_VOBELNR já se encontra na tabela da ALV, no lado dos documentos orçamentais, e se existir ignora-os

    4. Se nenhum deles existir na ALV, vai adicionar o montante de todos os documentos à tabela da ALV, preenchedo o documento orçamental com o mesmo documento do DFC

4. Adiciona os restantes documento orçamentais que sobram à ALV, sem documento DFC preenchido - 438

Tratamento de dados

1. Preenche tipos de documentos na ALV - 606
    1. Vai à BKPF ver o BLART do documento do DFC

    2. Se o STBLG (estorno) estiver preenchido, verifica se o documento de estorno tambem está na tabela da ALV, e se estiver, nas linhas correspondentes limpa o documento e montante

    3. Repete os dois passos anteriores para o documento orçamental

2. Elimina da tabela da ALV todas a linhas que agora tiverem o documento DFC e orçamental vazio - 678

3. Trata documentos compensados do DFC - BSE_CLR - 686

    1. Percorre linhas da tabela da ALV com documento DFC preenchido e documento orçamental vazio

    2. Lê na BSE_CLR com o documento de compensação igual ao documento DFC

    3. Para os documentos que encontrar na BSE_CLR, vai à tabela da ALV verificar se esses documento estão no lado da orçamental e verifica se essas linhas não têm o documento DFC preenchido

    4. Se encontrar linhas com essas condições vai preencher a coluna do documento DFC e respetivo montante com o que apanhou na BSE_CLR

    5. Subtrai esse montante do montante do DFC da linha original da ALV (linha que estava a tratar com o documento DFC usado para fazer a seleção à BSE_CLR)

4. Elimina da tabela da ALV todas as linhas com montante DFC e montante orçamental igual a 0 - 717

5. Verifica documentos compensados do DFC - 720

    1. Percorre linhas da tabela da ALV com documento DFC preenchido e documento orçamental vazio

    2. Vai à BSEG com o documento DFC

    3. Percorre linhas da BSEG que apanhou com o AUGBL preenchido (documento de compensação)

    4. Coloca o documento na clouna AUGBL da tabela da ALV. Se houver vários coloca o valor "VARIOS" nessa coluna

    5. Preenche a coluna das OBSERVACOES na tabela da ALV

        1. Se a coluna AUGBL estive vazia - 'Documento lançado na FI sem compensação no período selecionado'

        2. Coluna AUGBL preenchida com um documento

            1. Se data de compensação estiver no periodo de execução da ferramenta - 'Compensado. Analisar situações'.

            2. Se data de compensação não estiver no periodo de execução da ferramenta - 'Documento lançado na FI sem compensação no período selecionado'.

        3. Coluna AUGBL preenchida com "VARIOS" - 'Vários documentos de compensação'.

6. Verifica documentos compensados da orçamental - 760

    1. Percorre linhas da tabela da ALV com documento DFC vazio e documento orçamental preenchido

    2. Seleciona linhas da BSEG com item (BUZEI) diferentes dos que apanhou nas seleções iniciais à FMIFIIT

    3. Percorre linhas da BSEG com documento de compensação (AUGBL) preenchido e faz a mesma coisa que fez no passo anterior para os documentos DFC

7. Para documentos orçamentais compensados verifica se têm linhas para além de K e D - 899

    1. Percorre linhas da tabela da ALV com documento DFC vazio, documento orçamental preenchido e documento de compensação preenchido

    2. Vai à BSEG com o documento de compensação e KOART diferente de K e D

    3. Se não apanhar nada coloca no campo OBSERVACOES - 'Compensação gerou 57 na orçamental.'

8. Faz match de documentos DFC e ORC com montante igual e com apenas uma ocorrencia para esse montante - 918

    1. Percorre linhas da ALV com documento DFC preenchido e documento orçamental vazio

    2. Verifica se há mais linhas com o mesmo montante DFC da linhas que está a ver

    3. Se só houver 1 linha com esse montante vai ver se existe uma linha  com o montante orçamenta com esse montante e com documento DFC vazio

    4. Se encontrar apenas uma linha, elimina-a da ALV e passa o documento orçamental e montante para a linha que está a processar, e adicionar nas OBSERVACOES o texto "Match feito por valor"

9. Trata documentos orçamentais com fornecedor 250000 ou cliente 113426 - 949

    1. Percorre linhas da ALV com documento DFC vazio e documento orçamental preenchido

    2. Vai à BSEG com esse documento ler as linhas com KOART D ou K
    3. Verifica se o fornecedor é 250000 ou o cliente é 113426

    4. Se for um dos dois coloca nas OBSERVACOES o texto "Encontro de contas EMEF CP."

10. Trata documentos ORC que se anulam e geram mais e menos pagamento - 985

    1. Percorre linhas da ALV com documento DFC vazio e documento orçamental preenchido e que ainda não foi tratado antes

    2. Para esse documento, se existir outro documento orçamental com o mesmo montante mas inverso, coloca o texto nas OBSERVACOES de ambas as linhas "Documentos ORC que se anulam e geram mais e menos pagamento"

11. Trata documentos DFC que se anulam e geram mais e menos pagamento - 1006

    1. Percorre linhas da ALV com documento DFC preenchido e documento orçamental vazio e que ainda não foi tratado antes

    2. Para esse documento, se existir outro documento DFC com o mesmo montante mas inverso, coloca o texto nas OBSERVACOES de ambas as linhas "Documentos DFC que se anulam e geram mais e menos pagamento"

12. Preenche tipos de documento na ALV - 1028

13. Elimina documentos orçamentais 'duplicados' - 1077
    1. Parte 1

        1. Percorre linhas da ALV com doc DFC vazio e doc orçamental preenchido e com tipo de documento ZZ

        2. Vai à BSE_CLR com o BELNR igual a esses documentos

        3. Se encontrar dados, vai novamente à BSE_CLR com o BELNR_CLR igual aos documentos BELNR_CLR que apanhou na seleção anterior

        4. Adiciona os documento BELNR_CLR e BELNR que apanhou nesta ultima seleção a uma tabela interna de exclusão (GT_DOCS_EXC)

    2. Parte 2
        1. Percorre tabela dos documentos de exclusão
        2. Lê na tabela da ALV para o doc orçamental igual a esse documento

        3. Percorre todas as linhas da ALV com AUGBL igual ao AUGBL da linha anterior e adiciona o montante de cada um deles a uma variavel auxiliar

        4. No fim se o montante na variavel auxiliar for igual a zero, considera o documento de exclusão válido adicionando-o a uma tabela interna

    3. Parte 3

        1. Percorre a tabela de documentos de exclusão válidos e elimina as linhas da ALV que tenham doc DFC vazio e doc orçamental igual ao documento de exclusão

14. Trata PESSOAL (HR) - 1162
    1. Percorre linhas com doc DFC preenchido

    2. Se documento tiver o item financeiro S113 coloca o texto "PESSOAL" nas OBSERVACOES

    3. Vai à BSE_CLR com o BELNR_CLR igual ao doc DFC

    4. Dessas linhas vê se alguma tem algum dos itens do documento DFC (das linhas que apanhou na seleção inicial) e se tiver adiciona o BSE_CLR-BELNR a um range

    5. Faz nova seleção à BSE_CLR com o BELNR igual ao range que preencheu no passo anterior e preenche um outro range com os BELNR_CLR que apanhou

    6. Combina os dois ranges num só e depois percorre as linhas da ALV com doc orçamental contido nesse range e para eles colocar o texto "PESSOAL" em OBSERVACOES

15. Adicionar PESSOAL aos docs AB - 1240

    1. Percorre linahs da ALV com documento orçamental do tipo AB e coloca PESSOAL no texto das OBSERVACOES

16. Calcula a diferença de montante entre DFC e orçamental

* * *

# **IPL - DFC**

![image.png](image-91.png)