---
created: 2025-10-08 11:33
updated: 2025-10-13 15:04
---
**1 - ZWS_PD_GET_DOC_IMP - alterar designação do documento (4h)**
   
Nós não conseguimos manipular o nome do ficheiro em si, o que conseguimos fazer é criar um campo de saída, e colocar o nome do ficheiro nesse campo. Essa solução serviria para vocês? Também ficamos na dúvida se querem que o nome seja mesmo "Cabimento" ou "Compromisso" ou que seja o número do documento em si (e depois concatenado o número do item e respetiva modificação, nos casos em que é relevante)? 
   
**2 -  ZWS_PD_GET_DOC_IMP – não diferencia entre layout cabimento/compromisso e modificação (8h)**
   
Estivemos a analisar essa situação em sistema, e verificamos que existem 3 tipos de layouts:
1. Só se indica o documento - neste caso é feita a impressão do documento completo, com todos os itens (é o que acontece atualmente no serviço)
2. É indicado o documento e item - neste caso é impresso o item indicado, com os valores originais (antes de ter sido feita qualquer modificação)
3. É indicado o documento, item e número de modificação do item - neste caso é impresso o item indicado, com o valor da modificação indicada

O que querem é ter a possibilidade de fazer o mesmo no serviço ZWS_PD_GET_DOC_IMP? Ou seja, se passarem só o documento, faz o que faz atualmente, se passarem documento e item (sem número de modificação), imprime o item original, e se passarem documento/item/nº modificação, devolve o item com a modificação indicada. Isto também levanta a questão, vocês têm acesso às modificações de cada item, para indicarem qual pretendem que seja impressa?
   
**3 - Novo webservice - n.º project builder (8h)**
   
Como parâmetro de entrada, é suficiente a definição do projeto, certo? Uma vez que a dominação não é um campo chave, é irrelevante ao chamar o serviço.

**4 - Novo webservice - n.º contrato escrito (8h)**
   
Nada a apontar
   
**5 - ZWS_PD_CRIA_COMP - enviar Valor total previsto s IVA para SAP (6h)**
   
Neste serviço (ZWS_PD_CRIA_COMP) é feita a criação do compromisso, e vocês estão a pedir que seja ajustado um valor no contrato, que é um objeto diferente. É possível fazer, mas precisamos de mais informação de como se iria processar. Nós assumimos que na estrutura IT_COMP_ITEM, enviam os itens do compromisso e os PEPs/contratos, e que são esses contratos que querem que sejam ajustados. Se for esse o caso, é para preencher com o valor da soma do campo montante dos itens todos? Ou seria para incluir um campo novo onde indicariam o montante para esse campo específico? E já agora, conseguem dizer-nos se é possível no mesmo compromisso haverem PEPs diferentes, ou à partida será o mesmo para todos os itens?

![[BABEL - Melhorias e-Despesa CML-20251009-083047.png]]
 
   
**6 - ZWS_PD_MOD_PEP - acrescentar campo Data envio ao TC (4h)**
   
Nada a apontar