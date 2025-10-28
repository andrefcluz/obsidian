---
created: 2025-06-02 17:10
updated: 2025-10-21T15:55
tags:
  - ipl/safemed
cliente:
  - ipl
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



---

Empregados inativos e que vão ficar ativos no futuro

| Nº Pessoal | NIF       |
| ---------- | --------- |
| 10377      | 212171925 |
| 10938      | 210723297 |
| 11079      | 214933776 |
| 11712      | 208258256 |
| 11853      | 202146995 |
| 12078      | 216689783 |
| 12191      | 212868624 |
| 12475      | 206042060 |
| 12521      | 212048082 |
| 13476      | 233102418 |
| 13478      | 205304354 |
| 13537      | 217861644 |
| 13577      | 252150597 |
| 13593      | 167128485 |
| 13662      | 160741076 |
| 13831      | 113525176 |
| 13857      | 249760312 |
| 13891      | 246842407 |
| 13989      | 244055106 |
| 14059      | 225883155 |
| 14270      | 221489690 |
| 14962      | 234072261 |
| 14987      | 212961152 |
| 15076      | 261375210 |
| 15077      | 236950355 |
| 15079      | 248962833 |
| 15109      | 188261214 |
| 15110      | 223565911 |
| 15115      | 185208681 |
