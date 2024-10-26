### Cockpit

- [x] Situação 1 
Selecionar linhas para lançar - Ignorar linhas que já estão a verde ???

![[IPL - CXA - Reformulação-20241025112323749.png]]

### Cliente

- [x] Situação 2
Aqui alterar para modificar para ignorar linhas com S (Caso não se faça o passo acima)

![[IPL - CXA - Reformulação-20241025110500432.png]]


### Documento

 - [x] Situação 3
Aqui tentar modificar para ler a tabela ZFI_INTERF_CONT em vez de ir à BKPF e substituir o EXT_XBLNR por EXT_ID_FATURA

![[IPL - CXA - Reformulação-20241025111613511.png]]

- [x] Situação 4
Isto não funciona, porque foi desenvolvido com o pressuposto que a linha da NC viria logo a seguir à da FT, o que não é o caso. Tem que se ajustar, para quando ler a linha da NE, de alguma forma conseguir identificar a linha da FT correspondente

![[IPL - CXA - Reformulação-20241025112157960.png]]

 - [x] Situação 5
Mudar a forma como vai buscar o item da fatura, porque pode não ser assim tão linear. E comentar o código que tá a mais

![[IPL - CXA - Reformulação-20241025112716987.png]]

- [ ] Situação 6
Em todos os tipos de doc dá prioridade ao PAYOR, exceto no RGNC, ai usa sempre o KUNNR

![[IPL - CXA - Reformulação-20241025125729476.png]]
![[IPL - CXA - Reformulação-20241025125747738.png]]


### Melhorias

- [ ] Editar dados - modificar todas as linhas para processo antigo e apenas o item selecionado se for do processo novo
- [ ] Log por item em vez de ser por documento
- [ ] Modificação do cliente depois de lançar o documento - Fazer apenas uma vez por documento
- [ ] Corrigir programa ZFI_CORRIGE_INTERF_CONT