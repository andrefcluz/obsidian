---
title: IPL - Fatura Eletronica
updated: 2025-08-20 15:28
created: 2022-01-04 12:30:06Z
author: André Luz
tags:
  - ipl/fatura eletronica
cliente: ipl
---

### Transportes

|     |     |     |     |
| --- | --- | --- | --- |
| OT  | Descrição | QLD | PRD |
| DPLK905305 | TOIN.AL: Desenvolvimentos Fatura Eletronica | 31/05/2022 | 18/11/2022 |
| DPLK905749 | TOIN.AL: Desenvolvimentos Fatura Eletronica #2 | 31/05/2022 | 18/11/2022 |
| DPLK905826 | TOIN.AL: Desenvolvimentos Fatura Eletronica #3 | 01/08/2022 | 18/11/2022 |
| DPLK905852 | TOIN.AL: Desenvolvimentos Fatura Eletronica #4 | 24/08/2022 | 18/11/2022 |
| DPLK905854 | TOIN.AL: Desenvolvimentos Fatura Eletronica #5 | 18/11/2022 | 18/11/2022 |
| DPLK906279 | TOIN.AL: Desenvolvimentos Fatura Eletronica #6 | 13/04/2023 | 13/04/2023 |

* * *

### Passos transportes

- Parametrizar tabela ZFE_API_DATA
- Importar certificados na STRUST

* * *

Testes: https://ppr-svc.feap.gov.pt/Doc.WebApi.Services/api/index.html
Live: https://svc.feap.gov.pt/Doc.WebApi.Services/api/index.html

* * *

Programa de impressão: ZRFKORD50 (include ZRFKORI35_NEW)

* * *

Ticket: 8J7-M7B-VYX7

* * *

Dados Espap:

Testes

Portal: [*https://ppr-doc.feap.gov.pt/netdocs*](https://ppr-doc.feap.gov.pt/netdocs)

Webservice:  https://ppr-svc.feap.gov.pt/Doc.WebApi.Services
WSCommsPT508519713
<s>To!novate22</s>
poLisbo@22

Produção
Portal: [*https://doc.feap.gov.pt/netdocs*](https://doc.feap.gov.pt/netdocs)
Webservice: https://svc.feap.gov.pt/Doc.WebApi.Services
WSCommsPT508519713_PRD
IPLfe2023!

Recuperação password:

[*https://doc.feap.gov.pt/Netdocs/Public_Templates/CNDRecoveryPassword.aspx*](https://doc.feap.gov.pt/Netdocs/Public_Templates/CNDRecoveryPassword.aspx)

* * *

Contato Nuno Gomes: 917 419 730

* * *

Dados Teste 2022.05.27

Solicitar Correspondencia - FB12
Imprimir Correspondencia - F.64

1000/4060000017/2022

https://stthana.toinovate.com:8081/

admin
Nep2020

* * *

Exemplo XML assinado

![image.png](image-73.png)

* * *

|     |     |     |
| --- | --- | --- |
| FG  | ZFI_FG_PRINT_DATA |     |
| FM  | ZFI_MF_GET_PRINT_DATA | Obtem dados de impressão para o formulário que também são usado na FE |
|     |     |     |
|     |     |     |

Tabelas de log

|     |     |
| --- | --- |
| ZFE_LOG |     |
| ZFE_LOG_DETAIL |     |
| ZFE_LOG_ERROR |     |

|     |     |
| --- | --- |
| ![image.png](image-77.png) | ![image.png](image-72.png) |
| ![image.png](image-76.png) |     |

* * *

Email Marco:
Boas André,

Relativamente a FE vamos determinar o modo de envio e chamar o webservice no programa de impressão ZRFKORD50.

No dado mestre do cliente precisamos de novos campos a armazenar na KNA1:

               Um campo chamado Fatura Eletrónica – vazio e X (X para marcarmos nos clientes de FE). A chamada do webservice no programa de impressão vai ser feita em função deste campo

               Um campo chamado tipo de envio com as opções EDI e email.  (este campo servirá para um por menor de preenchimento de um campo no XML a vermos nos testes )

Em anexo o mapeamento de alguns campos. A maior parte deles devemos garantir a seleção de dados tal como está no programa de impressão. O ideal até será fazer a construção do XML exatamente no mesmo momento em que se chama o MF de chamada do smartform pois ai já temos as estruturas todas preenchidas para o formulário e é com base nisso que vamos construir o XML.

Depois quando já tivermos uma base feita podemos ver em conjunto as estruturas e tabelas que temos na chamada no smartform para mapearmos essas para o xml.

Patricia, é suposto enviar-se o PDF da fatura embebido no XML? Outra coisa, sabes se atualmente eles metem o compromisso em algum campo especifico do documento quando faturam?

Obrigado,
Marco Veloso

* * *

Casos de teste DEV

FT iva isento 4060000028
FT com um iva isento um a 23 e um a 13 4060000029
NC com referencia a 1ª fatura 4050000002
NC com referencia a 2 fatura 4050000003

4050000004
4050000005
4060000031
4060000032
4060000033

* * *

# **Mapeamento campos**

Estruturas
BKPF i
SIPT_BKPF e
T001 i
ADRC_T001 e
KNA1 i
* ADRC_KNA1
GS_TAXAMOUNT e ZST_TAX_AMOUNT_PRINT

Tabelas
GT_TAXES e ZTT_TAXES_PRINT
lt_BSEG e bseg_t

Variaveis
GV_DATA_VENCIMENTO e datum

|     |     |     |
| --- | --- | --- |
| **Campo** | **SD** | **FI** |
| **ZFE_CIUS_S_INVOICE** |
| ID  | SIPT_VBRK-INV_NO | MS_SIPT_BKPF-INV_NO |
| ISSUEDATE | VBRK-FKDAT | MS_BKPF-BUDAT |
| INVOICETYPECODE | FIEUD_SDGEN-TAGT_INV_TYPE | *FIEUD_MFI-TAGT_INV_TYPE - Já está a selecionar no programa de impressão, passar para o MF |
| DUEDATE | MF "SD_PRINT_TERMS_OF_PAYMENT" | MV_DATA_VENCIMENTO |
| TAXPOINTDATE | = ISSUEDATE | MV_DATA_VENCIMENTO |
| NOTE | TEXTO VBBK 0002<br>+ SIPT_VBRK | MS_BKPF-BKTXT<br>+ SIPT_BKPT |
| DOCUMENTCURRENCYCODE + TAXCURRENCYCODE | VBRK-WAERK | MS_BKPF-WAERS |
| ACCOUNTINGCOST (Compromisso) | VBKD-BSTKD_E | *A definir |
| **ORDERREFERENCE** |
| ID (Pedido) | VBKD-BSTKD | *A definir |
| **BILLINGREFERENCE **(Quando é nota de credito ou debito, preenche dados da fatura) |
| INVOICEDOCUMENTREFERENCE-ID | SIPT_VBRK-INV_NO |     |
| INVOICEDOCUMENTREFERENCE-ISSUEDATE | VBRK-FKDAT |     |
| **ACCOUNTINGSUPPLIERPARTY** |
| PARTYIDENTIFICATION-ID | T001-STCEG | MS_T001-STCEG |
| PARTYNAME-NAME | T001-BUTXT | MS_T001-BUTXT |
| POSTALADDRESS-STREETNAME | ADRC-STREET + ADRC-HOUSE_NUM1 | MS_ADRC_T001-STREET + MS_ADRC_T001-HOUSE_NUM1 |
| POSTALADDRESS-CITYNAME | ADRC-CITY1 | MS_ADRC_T001-CITY1 |
| POSTALADDRESS-POSTALZONE | ADRC-POST_CODE1 | MS_ADRC_T001-POST_CODE1 |
| POSTALADDRESS-COUNTRY-IDENTIFICATIONCODE | ADRC-COUNTRY | MS_ADRC_T001-COUNTRY |
| PARTYTAXSCHEME-COMPANYID | T001-STCEG | MS_T001-STCEG |
| PARTYTAXSCHEME-TAXSCHEME-ID | 'VAT' | 'VAT' |
| PARTYLEGALENTITY-REGISTRATIONNAME | T001-BUTXT | MS_T001-BUTXT |
| PARTYLEGARENTITY-COMPANYID | T001-STCEG | MS_T001-STCEG |
| CONTACT-NAME | T001-BUTXT | MS_T001-BUTXT |
| CONTACT-TELEPHONE | ADRC-TEL_NUMBER | MS_ADRC_T001-TEL_NUMBER |
| **ACCOUNTINGCUSTOMERPARTY** |
| PARTYIDENTIFICATION-ID | KNA1-STCEG | MS_KNA1-STCEG |
| PARTYNAME-NAME | KNA1-NAME1 + KNA1-NAME2 | MS_KNA1-NAME1 + MS_KNA1-NAME2 |
| POSTALADDRESS-STREETNAME | ADRC-STREET + ADRC-HOUSE_NUM1 | MS_ADRC_KNA1-STREET + MS_ADRC_KNA1-HOUSE_NUM1 |
| POSTALADDRESS-CITYNAME | ADRC-CITY1 | MS_ADRC_KNA1-CITY1 |
| POSTALADDRESS-POSTALZONE | ADRC-POST_CODE1 | MS_ADRC_KNA1-POST_CODE1 |
| POSTALADDRESS-COUNTRY-IDENTIFICATIONCODE | ADRC-COUNTRY | MS_ADRC_KNA1-COUNTRY |
| PARTYTAXSCHEME-COMPANYID | KNA1-STCEG | MS_KNA1-STCEG |
| PARTYTAXSCHEME-TAXSCHEME-ID | 'VAT' | 'VAT' |
| PARTYLEGALENTITY-REGISTRATIONNAME | KNA1-NAME1 + KNA1-NAME2 | MS_KNA1-NAME1 + MS_KNA1-NAME2 |
| PARTYLEGARENTITY-COMPANYID | KNA1-STCEG | MS_KNA1-STCEG |
| CONTACT-NAME | KNA1-NAME1 + KNA1-NAME2 | MS_KNA1-NAME1 + MS_KNA1-NAME2 |
| CONTACT-TELEPHONE | ADRC-TEL_NUMBER | MS_ADRC_KNA1-TEL_NUMBER |
| **DELIVERY** |
| PARTYIDENTIFICATION-ID | VBPA-STCEG | MS_KNA1-STCEG |
| POSTALADDRESS-STREETNAME | ADRC-STREET + ADRC-HOUSE_NUM1 | MS_ADRC_KNA1-STREET + MS_ADRC_KNA1-HOUSE_NUM1 |
| POSTALADDRESS-CITYNAME | ADRC-CITY1 | MS_ADRC_KNA1-CITY1 |
| POSTALADDRESS-POSTALZONE | ADRC-POST_CODE1 | MS_ADRC_KNA1-POST_CODE1 |
| POSTALADDRESS-COUNTRY-IDENTIFICATIONCODE | ADRC-COUNTRY | MS_ADRC_KNA1-COUNTRY |
| **PAYMENTMEANS** |
| PAYMENTMEANSCODE | 'TB' | *Ver como fazer para a ref. multibanco |
| PAYEEFINANCIALACCOUNT-ID | ZMAIN_BANK_DATA-IBAN |     |
| PAYEEFINANCIALACCOUNT-FINANCIALINSTITUTIONBRANCH-ID | ZMAIN_BANK_DATA-SWIFT |     |
| **PAYMENTTERMS** |
| NOTE | TVZBT-VTEXT | *TVZBT-VTEXT (BSEG-ZTERM linha D) |
| **TAXTOTAL** |
| TAXAMOUNT | VBRP-MWSBP | MS_TAXAMOUNT-AMOUNT3 |
| TAXSUBTOTAL-TAXABLEAMOUNT | VBRP-NETWR | MT_TAXES-INCID |
| TAXSUBTOTAL-TAXAMOUNT | VBRP-MWSBP | MT_TAXES-MONTA |
| TAXSUBTOTAL-TAXCATEGORY-ID | Metodo GET_TAX_PERCENT | SAFT_PT_TAX_DATA-TAX_CODE_OFFICIA (TAXCODE = BSEG-MWSKZ para linhas S) |
| TAXSUBTOTAL-TAXCATEGORY-PERCENT | Metodo GET_TAX_PERCENT | SAFT_PT_TAX_DATA-TAXPERCENTAGE |
| TAXSUBTOTAL-TAXCATEGORY-TAXEXEMPTIONREASONCODE | Metodo GET_TAX_PERCENT | SAFT_PT_TAX_DATA-TAXEXEMPTIONCODE |
| TAXSUBTOTAL-TAXCATEGORY-TAXEXEMPTIONREASON | Metodo GET_TAX_PERCENT | SAFT_PT_TAX_DATA-TAXEXEMPTIONREAS |
| TAXSUBTOTAL-TAXCATEGORY-TAXSCHEME-ID | 'VAT' | 'VAT' |
| TAXSUBTOTAL-TAXCURRENCYCODE | VBRK-WAERK | MS_BKPF-WAERS |
| **LEGALMONETARYTOTAL** |
| LINEEXTENSIONAMOUNT | VBRP-NETWR | Somatorio MT_BSEG-DMBTR (linhas S sem BUZID???) |
| TAXEXCLUSIVEAMOUNT | VBRP-NETWR | Somatorio MT_BSEG-DMBTR (linhas S sem BUZID???) |
| TAXINCLUSIVEAMOUNT | VBRP-NETWR + VBRP-MWSBP | Somatorio MT_BSEG-DMBTR (linhas D) ? |
| <s>ALLOWANCETOTALAMOUNT</s> | -   |     |
| <s>CHARGETOTALAMOUNT</s> | -   |     |
| <s>PREPAIDAMOUNT</s> | -   |     |
| <s>PAYABLEROUNDINGAMOUNT</s> | -   |     |
| PAYABLEAMOUNT | VBRP-NETWR + VBRP-MWSBP | Somatorio MT_BSEG-DMBTR (linhas D) |
| **INVOICELINE** |
| ID  | VBRP-POSNR | MT_BSEG-BUZEI |
| NOTE | Texto VBBP 0000 | MT_BSEG-SGTXT |
| INVOICEDQUANTITY | VBRP-FKIMG | '1' |
| LINEEXTENSIONAMOUNT | VBRP-NETWR | MT_BSEG-DMBTR |
| ITEM-DESCRIPTION | VBRP-ARKTX | screenshot |
| ITEM-NAME | VBRP-ARKTX | screenshot |
| ITEM-CLASSIFIEDTAXCATEGORY-ID | Metodo GET_TAX_PERCENT | SAFT_PT_TAX_DATA-TAX_CODE_OFFICIA (como tá antes, ver os dados para o MWSKZ correspondente ao do item que está a tratar) |
| ITEM-CLASSIFIEDTAXCATEGORY-PERCENT | Metodo GET_TAX_PERCENT | SAFT_PT_TAX_DATA-TAXPERCENTAGE (como tá antes, ver os dados para o MWSKZ correspondente ao do item que está a tratar) |
| ITEM-CLASSIFIEDTAXCATEGORY-TAXSCHEME-ID | 'VAT' | 'VAT' |
| ITEM-ADDITIONALITEMPROPERTY | Metodo GET_TAX_PERCENT + Pedido (VBKD) + Compromisso (VBKD)  + Item Compromisso (VBKD) |     |
| PRICE-PRICEAMOUNT | VBRP-NETWR | MT_BSEG-DMBTR |
| PRICE-BASEQUANTITY | VBRP-FKIMG | '1' |
| UNIT | MF UNIT_OF_MEASURE_SAP_TO_ISO (VBRP-VRKME) | ????? |
| TAXCURRENCYCODE | VBRK-WAERK | MS_BKPF-WAERS |

* * *

https://gocoding.org/calculate-a-hash-in-abap/

* * *

### Assinatura Digital DigitalSign (Não usado)

[DigitalSign | Certificadora Digital](https://www.digitalsign.pt/pt/)

[andre.luz@toinovate.com](mailto:andre.luz@toinovate.com)
toin1234

https://qscd-dev.digitalsign.pt/oauth/authorize?response_type=code&client_id=toinovate&redirect_uri=http://localhost/toinovate&scope=totp

[*https://qscd-dev.digitalsign.pt/oauth/authorize?response_type=code&client_id=toinovate&scope=totp*](https://qscd-dev.digitalsign.pt/oauth/authorize?response_type=code&client_id=toinovate&scope=totp)

![image.png](image-75.png)

![image.png](image-78.png)

* * *

![image.png](image-79.png)

* * *

SECXML_SIGN_SIGNED_XML
![image.png](image-74.png)

* * *

Password para descompactar certificado z3bqjd6wrihg584suqj3v3q6cul7lysq.p7b.7z:

m)Fz{/b('8n_)6sY