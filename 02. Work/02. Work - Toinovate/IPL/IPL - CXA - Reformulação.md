---
tags:
  - ipl/cxa
created: 2024-11-05 18:02
updated: 2025-08-20 15:28
cliente: ipl
---
### Melhorias/Correções (31.10.2024)

Correções:
- [x] Eliminar dados recebidos do CXA com mais de 6 meses
- [x] Editar dados - modificar todas as linhas para processo antigo e apenas o item selecionado se for do processo novo
- [ ] Log por item em vez de ser por documento


Melhorias:
- [ ] Melhorias de performance - Criar uma tabela de arquivo para colocar processos fechados / modificação do cliente depois de lançar o documento (fazer apenas uma vez por documento)
- [ ] Melhorar pesquisa logs
- [ ] Quando documentos são estornados, atualizar automaticamente documentos no cockpit
- [ ] Bloquear cockpit para impedir que sejam feitos lançamentos quando está mais do que uma pessoa no cockpit, à semelhança do que acontece no USDMT

---
### Erros

- [x] RGNC ESCS2024/233 (Seleciona mal documentos e montante)
- [x] NR ISCAL2024/256 (Datas) - Item Errado
- [x] NR ISCAL2024/261 (Datas) - Item Errado
- [x] NR ISCAL2024/270 (Datas) - Item Errado
- [x] NR ESCS2024/86 (Seleciona mal documentos)
- [x] NR ISCAL2024/198 (Seleciona mal documentos)
- [x] NR ISCAL2024/202 (Seleciona mal documentos)

---

### Situações a rever

- [x] A linha a amarelo está marcada como eliminada, no entanto o doc SAP está lançado e não está estornado
![[IPL - CXA - Reformulação-20241029180332704.png]]


- [ ] A linha amarelo ficou em erro ao executar o job, mas depois ao executar manualmente lançou com sucesso sem ter feito nenhuma alteração. Deve ser uma questão de sequencialidade ao executar o job. 
![[IPL - CXA - Reformulação-20241030090647742.png]]

### Mapeamento


|                     |                 |      | Atual      | Certo      |
| ------------------- | --------------- | ---- | ---------- | ---------- |
| cxa_20241030_020037 | NR ESTSL2024/80 | RGNR | LINENUMBER | LINEREF    |
|                     |                 | RGNL | LINENUMBER | LINEREF    |
|                     |                 | RGNC | LINENUMBER | LINENUMBER |


---
### Objetos

ZFI_INTEGRA_CONTABILIZ_UPD - MF Integração dados CXA
ZFI_INTERFACE_POST_DOCUMENT - MF Lançamento docs CXA
ZFI_INTERFACE_CREATE_KUNNR - MF Criação/Modificação clientes

ZFI_COCKPIT_CONTAB - Cockpit
ZFI_CORRIGE_INTERF_CONT - Programa correção documentos CXA para processo novo

ZFI_INTERF_CONT - Tabela dados CXA
ZFI_INTERF_LOG - Tabela LOG


---
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

- [x] Situação 6
Em todos os tipos de doc dá prioridade ao PAYOR, exceto no RGNC, ai usa sempre o KUNNR

![[IPL - CXA - Reformulação-20241025125729476.png]]
![[IPL - CXA - Reformulação-20241025125747738.png]]


