---
title: Usar Virtual Env
updated: 2022-10-21 10:30:06Z
created: 2022-08-09 13:25:57Z
author: André Luz
tags:
  - coding
---

## Criar VirtualEnv

`py -m venv <directory_path> `
OU
`py -m venv .`

* * *

## Ativar VirtualEnv

### CMD

`Scripts\activate`

### PowerShell

```
Set-ExecutionPolicy RemoteSigned
Scripts\Activate.ps1
```

* * *

## Instalar Packages

`Scripts\python.exe Scripts\pip.exe install <package_name>`

* * *

## Executar Script Python

`Scripts\python.exe <nome_script>.py`

* * *

## Desativar VirtualEnv

### CMD

`deactivate`

### PowerShell

`deactivate`

* * *

##