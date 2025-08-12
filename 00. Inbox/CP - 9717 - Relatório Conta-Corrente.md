---
created: 2025-08-11 16:26
updated: 2025-08-12 16:18
share_link: https://share.note.sx/1up9snes
share_updated: 2025-08-12T16:05:47+01:00
---

- Item Fin.
- Centro Fin
- Fundos
- Cabimento
- Item Cabimento
- Compromisso
- Item Compromisso
- Requisição Compras
- Item Requisição
- Pedidos Compras
- Item Pedido
- Faturas
- Conta Fatura (collect itens com a mesma conta)
- Pagamentos...

# Programa carregamento - 68

- [ ] Seleções - 24 
	- [ ] Cabimentos - 8
	- [ ] Compromissos (cabimentos) - 2
	- [ ] Requisições compra (cabimentos) - 2
	- [ ] Pedidos compra (cabimentos) - 2
	- [ ] Faturas (compromissos) - 2
	- [ ] Pagamentos (faturas) - 2
	- [ ] Transferências Fundos - 2
	- [ ] Exceções - 2
	- [ ] Retenções - 2
- [ ] Tratamento dados - 40
- [ ] Carregamento tabela - 4

# Programa exibição - 52

- [ ] Exibição com leitura direta da tabela - 14
	- [ ] Seleção dos dados - 2
	- [ ] Tratamento - 12 
- [ ] Leitura em tempo real para documentos específicos - 22
	- [ ] Tipos documento (ecrãs) - 8
		- [ ] Cabimentos - 2
		- [ ] Compromissos - 2
		- [ ] Requisições compra - 2
		- [ ] Pedidos compra - 2
	- [ ] Seleções (usar módulos de função do programa de carregamento) - 12
		- [ ] Cabimentos - 2
		- [ ] Compromissos - 2
		- [ ] Requisições compra - 2
		- [ ] Pedidos compra - 2
		- [ ] Chamar MF dos cabimentos, passando como parâmetros as tabelas internas com os dados obtidos nas seleções anteriores - 2
		- [ ] Chamar os restantes MF para selecionar os dados que faltam - 2
	- [ ] Tratamento dados (usar módulo função do programa de carregamento) - 2
- [ ] Exibição (exibição ALV, classe eventos ALV, cores) - 16