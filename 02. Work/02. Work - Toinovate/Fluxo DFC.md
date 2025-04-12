---
title: Fluxo DFC
updated: 2024-10-06 10:50
created: 2020-11-17 11:10:22Z
author: André Luz
tags:
  - cp
---

1. Faz match dos documentos DFC com orçamental - **FEITO**
2. Obtem tipos de documento - **FEITO**
3. Trata documentos compensados do DFC (BSE_CLR) - **FEITO**
4. <s>Trata documentos compensados orçamental (BSE_CLR)</s>

5. Verifica documentos compensados do DFC (BSEG-AUGBL) - Mensagens "Documento lançado na FI sem compensação no período selecionado",  "Compensado. Analisar situações" e "Vários documentos de compensação" - **FEITO **

6. Verifica documentos compensados da orçamental (BSEG-AUGBL) - **FEITO**

7. Nas linhas de documentos de orçamento com o documento de compensação ir à BSEG buscar os items com KOART diferente de K e D. Quando não apanha nada colocar no texto "Compensação gerou 57 na orçamental" - **FEITO **

8. Para linhas apenas com documento orçamental preenchido verificar se tem fornecedor 250000 ou 113426 e colocar texto "Encontro de contas EMFE CP" - **FEITO **

9. Para linhas apenas com documento orçamental preenchido e diferente de "Encontro de contas EMFE CP" verificar se há outro registo igual mas com o montante com sinal contrário e colocar texto "Documentos que se anulam e geram mais e menos pagamento" - (Isto substitui a parte de tratar documento compensados da orçamental??? Em parte sim) - **FEITO**

10. Elimina documentos orçamentais duplicados - Vê os que tem o tipo de documento ZZ, depois vai à BSE_CLR ver os documentos que esses anulam e exclui ambos da ALV - **FEITO**

11. FIPOS DFC
12. Calcula diferenças nos montantes e adiciona semáforo - **FEITO**
13. Filtra tabela consoante o pisco dos parametros de seleção - **FEITO**