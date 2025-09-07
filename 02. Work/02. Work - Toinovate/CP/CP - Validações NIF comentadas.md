---
created: 2025-07-07 12:20
updated: 2025-08-20 15:26
tags:
  - cp
cliente: cp
---
![[CP - Validações NIF comentadas-1751887250510.png]]


Include ZXM08U16
```abap
**&---------------------------------------------------------------------*
**&  Include           ZXM08U16
**&---------------------------------------------------------------------*
**    Data     | Alterado por |             Marca/Comentários
**&---------------------------------------------------------------------*
** 2015-02-12  |   PMONTEZ    | Remove código que guarda na o NIF
**                            | que o utilizador inserio na MIRO
**                            | Remove validação para os estornos
**&---------------------------------------------------------------------*
*
*" Verifica se o tipo de documento não é um estorno
*IF E_TRBKPV-BLART ne 'ZZ'.
*  DATA: w_lfa1 TYPE lfa1,
*        ls_aux TYPE zfi_miro_nif.
*
*  CLEAR w_lfa1.
*  SELECT SINGLE * FROM lfa1 INTO w_lfa1
*    WHERE lifnr EQ e_trbkpv-lifnr.
*
**  JEGD 14.11.2011 INS BEG.
*  IF ( e_trbkpv-tcode EQ 'MR8M' OR e_trbkpv-stblg NE space ) AND e_trbkpv-bldat < '20111111'.
*    EXIT.
*  ENDIF.
*  IF e_trbkpv-tcode EQ 'MR8M' OR e_trbkpv-stblg NE space.
*    SELECT SINGLE stceg FROM zfi_miro_nif INTO nfiscal
**    WHERE belnr = e_trbkpv-stblg AND gjahr = e_trbkpv-gjahr."REM PCT 16.02.2012
*    WHERE belnr = e_trbkpv-stblg AND gjahr = e_trbkpv-stjah."INS PCT 16.02.2012
*  ELSE.
*    IF nfiscal IS INITIAL.
*      SELECT SINGLE stceg FROM zfi_miro_nif INTO nfiscal
*      WHERE belnr = e_trbkpv-belnr AND gjahr = e_trbkpv-gjahr.
*    ENDIF.
*  ENDIF.
*
*  IF nfiscal IS INITIAL.
*    IF nfiscal NE w_lfa1-stceg.
*      MESSAGE e005(zfi).
*    ENDIF.
**  JEGD 14.11.2011 INS END.
*  ELSEIF nfiscal NE w_lfa1-stceg.
*    MESSAGE e004(zfi) WITH 'NºId.Fiscal do forn. associado ao Pedido de Compra.'.
*  ENDIF.
*ENDIF.

"INSERT.INI ALUZ 03.04.2020
DATA: w_lfa1  TYPE lfa1,
      ls_rbkp TYPE rbkp.

IF sy-tcode NE 'MR8M' AND
    e_trbkpv-lifnr IS NOT INITIAL AND
    ( E_TRBKPV-blart EQ 'KR' OR
      E_TRBKPV-blart EQ 'KS' OR
      E_TRBKPV-blart EQ 'KT' OR
      E_TRBKPV-blart EQ 'KG' ).

  SELECT SINGLE *
    FROM rbkp
    INTO ls_rbkp
    WHERE belnr EQ e_trbkpv-belnr
      AND gjahr EQ e_trbkpv-gjahr.

  IF sy-subrc NE 0.
    CLEAR w_lfa1.
    SELECT SINGLE * FROM lfa1 INTO w_lfa1
      WHERE lifnr EQ e_trbkpv-lifnr.

    IF nfiscal IS INITIAL.
      IF nfiscal NE w_lfa1-stceg.
        MESSAGE e005(zfi).
      ENDIF.
    ELSEIF nfiscal NE w_lfa1-stceg.
      MESSAGE e006(zfi) WITH 'NºId.Fiscal do forn. associado ao Pedido de Compra.'.
    ENDIF.
  ENDIF.
ENDIF.
"INSERT.END ALUZ 03.04.2020
```


Include ZXM08U31

```abap
*&---------------------------------------------------------------------*
*&  Include           ZXM08U31
*&---------------------------------------------------------------------*

"INSERT.INI ALUZ 11.03.2020
"Migração EMEF

DATA: lv_nif TYPE stceg.
DATA: lv_flag_nif(1).

CHECK i_invfo-blart EQ 'KR'
    OR i_invfo-blart EQ 'KS'
    OR i_invfo-blart EQ 'KT'
    OR i_invfo-blart EQ 'KG'.

SELECT SINGLE stceg FROM lfa1 INTO lv_nif
  WHERE lifnr = i_invfo-lifnr.
IF i_invfo-belnr IS INITIAL.

IF i_invfo-lifnr IS not INITIAL.
  IF nfiscal IS INITIAL or nfiscal ne lv_nif.
    MESSAGE 'Indicar o NºId.Fiscal do fornecedor que consta na fatura' TYPE 'I' DISPLAY LIKE 'E'.
*    lv_flag_nif = 'X'.
*    EXPORT lv_flag_nif TO MEMORY ID 'FLAG_NIF_MIRO'. "Importado no Enhancement Point Z_FI04
*    EXIT.
  ENDIF.
  endif.
  endif.
*ELSE.
**  IF nfiscal IS INITIAL.
**    IF nfiscal <> lv_nif.
***      MESSAGE 'Indicar o NºId.Fiscal do fornecedor que consta na factura' TYPE 'I' DISPLAY LIKE 'E'.
**      lv_flag_nif = 'X'.
**      EXPORT lv_flag_nif TO MEMORY ID 'FLAG_NIF_MIRO'. "Importado no Enhancement Point Z_FI04
**      EXIT.
**    ENDIF.
**  ENDIF.
*ENDIF.
*JEGD 14.11.2011 INS END.
"INSERT.END ALUZ 11.03.2020
```


