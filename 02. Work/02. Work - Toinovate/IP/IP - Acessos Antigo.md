---
title: Acessos IP - Antigo
updated: 2025-10-16T10:12
created: 2019-01-24 17:00:26Z
source: https://webmail.smartcloud.pt/owa/
author: André Luz
tags:
  - ip
cliente: ip
---

**SAP**

Username: EXAFLUZ
Password: Toin9++2017

Descrição: IP - RFD - Desenvolvimento
Servidor: rforsapdev002.refer.pt
Instância: 00
ID sist.: RFD

* * *

**VPN**

Username: EXENARCISO
Password: iP.134250

Username: EXPPIRES
Password: iP.140546

https://support.microsoft.com/en-us/help/926179/how-to-configure-an-l2tp-ipsec-server-behind-a-nat-t-device-in-windows

New-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\PolicyAgent" -Name "AssumeUDPEncapsulationContextOnSendRule" -Value "2" -PropertyType DWORD -Force

Add-VpnConnection -Name "IP - VPNALD" -ServerAddress "vpnald.infraestruturasdeportugal.pt" -TunnelType "L2tp" -EncryptionLevel "Required" -AuthenticationMethod Eap -L2tpPsk "alaska-syjM90sgG4RQ3I" -Force -PassThru

Write-Host "Please reboot" -ForegroundColor Red