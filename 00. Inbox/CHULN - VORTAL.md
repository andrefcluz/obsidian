---
created: 2025-04-22 16:00
updated: 2025-07-11 08:08
tags:
  - chuln
---

Pacote: **ZVORT**

Configuração da porta na tabela **ZMM_INT_CONFIG**

Utilizador: 701229015_241203162431
Palavra-Chave: (QwMZB_8nE
Código da Entidade: 	70122901
Códigos de Utilizadores:

| Utilizador            | Código  |
| --------------------- | ------- |
| Leonardo Vieira Catro | 3357019 |
| José Alves            | 3356029 |



Solicitação BI QLD 3100068491


NPD Vortal


Fornecedor
LS_RESPONSE_MESSAGE > PROCEDURE_REQUEST_OFFER_DETAIL > BASE > OFFERS > BASE > NEW_ENTITIES > ITEMS > OFFER_EXTERNAL_INTEGRATION_CRE [] > BASE > VAT

Lotes
LS_RESPONSE_MESSAGE > PROCEDURE_REQUEST_OFFER_DETAIL > BASE > OFFERS > BASE > NEW_ENTITIES > ITEMS > OFFER_EXTERNAL_INTEGRATION_CRE [] > BASE > LOTS_REPLIED_TO > BASE > NEW_ENTITIES > ITEMS > LOTS_REPLIED_TO_EXTERNAL_INTEG [] > BASE > LOT_NUMBER

Numero Solicitação Vortal
LS_RESPONSE_MESSAGE > PROCEDURE_REQUEST_OFFER_DETAIL > BASE > OFFERS > BASE > NEW_ENTITIES > ITEMS > OFFER_EXTERNAL_INTEGRATION_CRE [] > BASE > UNIQUE_IDENTIFIER

---

- [ ] ME41
	- [x] Tipo solicitação - ZAN fixo
	- [x] Data solicitação - SubmitDate da Vortal
	- [x] Prazo cotação - igual à data solicitação
	- [x] Organização de compras - 1100 fixo
	- [x] Grupo de compradores - Derivar da RC
- [ ] ME47
	- [ ] Preço liquido - TotalValue da Vortal?
	- [ ] Prazo de entrega - Mesma data do prazo da solicitação?
	- [ ] Prazo de pagamento - Mesma data do prazo da solicitação?
- [ ] Estados NPD



---

ls_offer_detail-OFFER_DETAIL-BASE-QUESTIONNAIRES-BASE-NEW_ENTITIES-ITEMS-QUESTIONNAIRE_EXTERNAL_INTEGRA[]-...

...-BASE-QUESTIONS-BASE-NEW_ENTITIES-ITEMS-QUESTION_EXTERNAL_INTEGRATION[]-...

...-BASE-LOT_NUMBER (Número do lote???)

...-SPECIFICATIONS-BASE-NEW_ENTITIES-ITEMS-SPECIFICATION_QUESTION_EXTERNA[]-...

...-BASE-REPLY_VALUE (Valor???)