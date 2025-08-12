<%*
const date_from = await tp.system.prompt("Data Início:");
const date_to = await tp.system.prompt("Data Fim:");
const title = `Plano Alimentar ${date_from} - ${date_to}`;
tp.file.rename(title);
%>---
tags:
  - eating_plan
---
- Segunda-Feira
	- Almoço: 
	- Jantar: 
- Terça-Feira
	- Almoço: 
	- Jantar: 
- Quarta-Feira
	- Almoço: 
	- Jantar: 
- Quinta-Feira
	- Almoço: 
	- Jantar: 
- Sexta-Feira
	- Almoço: 
	- Jantar: 
- Sábado
	- Almoço: 
	- Jantar: 
- Domingo
	- Almoço: 
	- Jantar: 