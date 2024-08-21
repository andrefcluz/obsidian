---
title: Toinovate - USDMT
updated: 2022-05-12 09:14:49Z
created: 2021-06-29 15:14:36Z
author: André Luz
tags:
  - usdmt
---

**[Template Todoist USDMT](https://todoist.com/API/v8.7/import/project_from_url?t_url=https%3A%2F%2Fd1aspxi4rjqbaz.cloudfront.net%2F5c42d8c733d983b8fc5fcd12116bd992_Toinovate%2520-%2520USDMT.csv)**

### SAP Namespaces

https://blogs.sap.com/2018/09/19/creating-your-own-namespace-how/
https://answers.sap.com/questions/3604528/create-a-new-namespace.html

/USDMT/
![Untitled.jpeg](Untitled.jpeg)
07986643674067557938
37964496811581600175

* * *

SE03 -> Exibir/Modificar conjuntos de nomes

![image.png](image-103.png)![image.png](image-101.png)

SE03 -> Definir opções de modificação do sistema
![image.png](image-104.png)

* * *

Sample de código de preenchimento da tabela para validar o mapa DODES

![image.png](image-102.png)

```
FORM executa_valida_dodes .
  DATA: gt_val_dodes TYPE TABLE OF  zvalida_dodes,
        gs_val_dodes TYPE           zvalida_dodes.
  DATA: lv_job_number   TYPE tbtcjob-jobcount,
        lv_jobname      TYPE tbtcjob-jobname.
  DATA: lv_data TYPE datum,
        lv_hora TYPE uzeit.
  RANGES: r_monat FOR bkpf-monat. "INSERT ALUZ 06.11.2020
  lv_data = sy-datum.
  lv_hora = sy-uzeit.
  "INSERT.INI ALUZ 06.11.2020
  IF p_period+1(2) EQ '01'.
    r_monat-sign    = 'I'.
    r_monat-option  = 'EQ'.
    r_monat-low     = p_period+1(2).
    APPEND r_monat.
  ELSE.
    r_monat-sign    = 'I'.
    r_monat-option  = 'BT'.
    r_monat-low     = '01'.
    r_monat-high    = p_period+1(2).
    APPEND r_monat.
  ENDIF.
  "INSERT.END ALUZ 06.11.2020
  "Elimina entrada da tabela ZVALIDA_DODES para a chave
  DELETE FROM zvalida_dodes WHERE bukrs EQ r_bukrs-low
                              AND gjahr EQ p_gjahr
                              AND monat EQ p_period.
  COMMIT WORK AND WAIT.
  "Volta a preencher a tabela com os dados atualizados
  LOOP AT it_dados.
    CLEAR gs_val_dodes.
    gs_val_dodes-bukrs = it_dados-bukrs.
    gs_val_dodes-gjahr = p_gjahr.
    gs_val_dodes-monat = p_period.
    gs_val_dodes-fistl = it_dados-fistl.
    gs_val_dodes-geber = it_dados-geber.
    IF it_dados-fkber NE '0000'.
      gs_val_dodes-fkber = it_dados-fkber.
    ELSE.
      gs_val_dodes-fkber = '000'.
    ENDIF.
*    gs_val_dodes-fipex = it_dados-fipos.
    CALL FUNCTION 'CONVERSION_EXIT_FMCIL_INPUT'
      EXPORTING
        input  = it_dados-fipos
      IMPORTING
        output = gs_val_dodes-fipex
      .
    gs_val_dodes-organica_legal = it_dados-organica_legal.
    gs_val_dodes-chave_mapa = 'X'.
    gs_val_dodes-dot_corrigidas         =
        it_dados-dot_corrigidas.
    gs_val_dodes-desp_pagar_per_ant     =
        it_dados-despesas_pagar.
    gs_val_dodes-cativos                =
        it_dados-cativos.
    gs_val_dodes-descativos             =
        it_dados-descativos.
    gs_val_dodes-cativo_descativo       =
        it_dados-cativo_descativo.
    gs_val_dodes-cabimentos             =
        it_dados-cabimentos.
    gs_val_dodes-compromissos           =
        it_dados-compromissos.
    gs_val_dodes-dot_disponiveis        =
        it_dados-dot_disponiveis.
    gs_val_dodes-obrigacoes             =
        it_dados-obrigacoes.
    gs_val_dodes-desp_pag_brutas        =
        it_dados-desp_pag_brutas.
    gs_val_dodes-rep_abat_pag_emitidas  =
        it_dados-rep_abat_pag_emitidas.
    gs_val_dodes-rep_abat_pag_rec       =
        it_dados-rep_abat_pag_rec.
    gs_val_dodes-desp_pag_liq_anterior  =
        it_dados-desp_pag_liq_anterior.
    gs_val_dodes-desp_pag_liq_corrente  =
        it_dados-desp_pag_liq_corrente.
    gs_val_dodes-desp_pag_liq_total     =
        it_dados-desp_pag_liq_total.
    gs_val_dodes-compromisso_transitar  =
        it_dados-compromisso_transitar.
    gs_val_dodes-obrigacoes_por_pagar   =
        it_dados-obrigacoes_por_pagar.
    gs_val_dodes-compr_assum_fut_nm1    =
        it_dados-comprassumparaperifutanonm1.
    gs_val_dodes-compr_assum_fut_nm2    =
        it_dados-comprassumparaperifutanonm2.
    gs_val_dodes-compr_assum_fut_nm3    =
        it_dados-comprassumparaperifutanonm3.
    gs_val_dodes-compr_assum_fut_nm4    =
      it_dados-comprassumparaperifutanonm4.
    gs_val_dodes-compr_assum_fut_seg    =
        it_dados-comprassumparaperifutanoseg.
    gs_val_dodes-obrig_period_futuro_n1 =
        it_dados-obrig_period_futuro_n1.
    gs_val_dodes-obrig_period_futuro_n2 =
        it_dados-obrig_period_futuro_n2.
    gs_val_dodes-obrig_period_futuro_n3 =
        it_dados-obrig_period_futuro_n3.
    gs_val_dodes-obrig_period_futuro_n4 =
        it_dados-obrig_period_futuro_n4.
    gs_val_dodes-obrig_period_seguintes =
        it_dados-obrigparaperifutanosseg.
    gs_val_dodes-data_extracao = lv_data.
    gs_val_dodes-hora_extracao = lv_hora.
    COLLECT gs_val_dodes INTO gt_val_dodes.
  ENDLOOP.
  MODIFY zvalida_dodes FROM TABLE gt_val_dodes.
  COMMIT WORK AND WAIT.
  "Chama o programa para validar os dados
  IF sy-subrc EQ 0.
    IF sy-batch IS NOT INITIAL.
      SUBMIT zpsm_usdmt WITH p_dodes  = 'X'
                        WITH p_dorec  = ''
                        WITH p_bukrs  = r_bukrs-low
                        WITH p_gjahr  = p_gjahr
*                        WITH p_monat  = p_period+1(2) "DELETE ALUZ 06.11.2020
                        WITH so_monat IN r_monat "INSERT ALUZ 06.11.2020
                        WITH p_nproc  = ''
                        WITH p_proc   = 'X'
                        WITH p_regra  = ''
                        AND RETURN.
    ELSE.
      CONCATENATE 'Valida DODES-' sy-datum '-' sy-uzeit
          INTO lv_jobname.
      CALL FUNCTION 'JOB_OPEN'
        EXPORTING
          jobname          = lv_jobname
        IMPORTING
          jobcount         = lv_job_number
        EXCEPTIONS
          cant_create_job  = 1
          invalid_job_data = 2
          jobname_missing  = 3
          OTHERS           = 4.
      SUBMIT zpsm_usdmt WITH p_dodes  = 'X'
                        WITH p_dorec  = ''
                        WITH p_bukrs  = r_bukrs-low
                        WITH p_gjahr  = p_gjahr
*                        WITH p_monat  = p_period+1(2) "DELETE ALUZ 06.11.2020
                        WITH so_monat IN r_monat "INSERT ALUZ 06.11.2020
                        WITH p_nproc  = ''
                        WITH p_proc   = 'X'
                        WITH p_regra  = ''
                    VIA JOB lv_jobname
                    NUMBER lv_job_number
                    AND RETURN.
      "Ver se se tem que preencher o TARGETSERVER
      "como está no cockpit
      CALL FUNCTION 'JOB_CLOSE'
        EXPORTING
          jobcount             = lv_job_number
          jobname              = lv_jobname
          strtimmed            = 'X'
        EXCEPTIONS
          cant_start_immediate = 1
          invalid_startdate    = 2
          jobname_missing      = 3
          job_close_failed     = 4
          job_nosteps          = 5
          job_notex            = 6
          lock_failed          = 7
          invalid_target       = 8
          OTHERS               = 9.
    ENDIF.
  ENDIF.
ENDFORM.                    " EXECUTA_VALIDA_DODES
```