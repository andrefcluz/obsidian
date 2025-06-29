---
created: 2025-06-02 17:10
updated: 2025-06-29 16:32
tags:
  - ipl/safemed
---
Nota original: [[IPL - Safemed]]

Ticket: JP1-639-S35V

- [x] Flag Inativo
	- [x] Estão a ser enviados os registos pela data de modificação, e quando um trabalhador é marcado como inativo numa data futura, esse registo fica com a data de modificação de hoje, mas esse registo não pode ser logo enviado, porque assim o trabalhador iria ficar inativo na Safemed imediatamente. Tem que se ajustar de forma ao enviar os registo do infótipo 0000, ao fazer as seleções deve olhar também para a data de inicio do registo, em vez de olhar apenas para a data de modificação
- [ ] Categoria Profissional
	- [x] Enviar sempre para as medidas P1 e PL
	- [ ] Criar programa para carregar todos os campos relacionados com a categoria profissional, de todos os trabalhadores, na Safemed
	- [ ] Passar a enviar sempre, independentemente da medida
- [ ] Percentagem de Trabalho - Enviar dados do infótipo 0007 (PA0007)
	- [ ] Flag de tempo parcial (PA0007-TEILK)
	- [ ] Percentagem de horário de trabalho (PA0007-EMPCT)
  
  ![[IPL - Safemed - Ajustes (JP1-639-S35V) - Horario de trabalho.png]]

Relativamente à questão dos trabalhadores a tempo parcial, vão ser criados dois novos campos para registar esses dados e facilitar essa gestão do IPL. Estes campos ainda não estão disponíveis no webservice mas podem já ficar com registo dos mesmos para adicionar ao envio do vosso lado:
- bool partialContract
- string partialContractNotes