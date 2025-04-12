---
title: PAP Espap
updated: 2024-10-06 10:50
created: 2018-03-12 14:56:49Z
author: André Luz
tags:
  - espap
---

Bom dia

relativamente ás BADI da PAP existem as seguintes :

-->**ZCL_IM_PFM_PAP (2009)**** **-que tem os seguinte métodos
      BEFORE_LIQDOC_CREATE
      SET_ACCITEMS_LIQUIDATION

     Aqui  pode -se fazer substituições, e também validações, sendo que estas validações não podem ser replicadas em vários momentos

--> **ZCL_PFM_PAP_CHECK (2014) -** que tem os seguintes métodos
      CHECK_ON_ADD
      CHECK_ON_APPROVAL
      CHECK_ON_SAVE
      CHECK_ON_SETTLEMENT

      Todos estes métodos são de validações, e não de substituições, pois não tem parâmetros de saída na assinatura dos mesmos

      Aqui as validações podem ser replicadas/chamadas  nos vários momentos (ao entrar ; verificar; gravar;aprovar)

As validações do Balcão 13 foram assim transferidas e ajustadas para serem chamadas nos métodos dos momentos da nova BADI criada após o refactoring da PAP.

As substituições ficaram no método da BADI antiga.

@Paula por favor testa tudo de novo !!

obg
MEG