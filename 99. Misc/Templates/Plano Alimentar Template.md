<%*
const date_from = await tp.system.prompt("Data Início:");
const date_to = await tp.system.prompt("Data Fim:");
const title = `Plano Alimentar ${date_from} - ${date_to}`;
tp.file.rename(title);
%>---
tags:
  - eating_plan
---

|               | Almoço | Jantar |
| ------------- | ------ | ------ |
| Segunda-Feira |        |        |
| Terça-Feira   |        |        |
| Quarta-Feira  |        |        |
| Quinta-Feira  |        |        |
| Sexta-Feira   |        |        |
| Sábado        |        |        |
| Domingo       |        |        |
