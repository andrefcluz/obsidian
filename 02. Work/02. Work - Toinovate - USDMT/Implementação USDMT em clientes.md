---
title: Implementação USDMT em clientes
updated: 2023-06-14 10:49:26Z
created: 2022-03-16 09:55:05Z
author: André Luz
tags:
  - usdmt
---

### Sistema Origem

- [ ] Criar OT de transporte de cópias
- [ ] Incluir pacote /USDMT/USDMT na OT
- [ ] Incluir pacote ZUSDMT_EXITS na OT
- [ ] Incluir layouts da ALV da ferramenta na OT
- [ ] Liberar OT
- [ ] Fazer download do ficheiros DATA e COFILES

### Sistema Destino

- [ ] Adicionar namespace /USDMT/ ao sistema de destino (SE03 -> Exibir/Modificar conjuntos de nomes)
- [ ] Definir o namespace /USDMT/ como modificável (SE03 -> Definir opções de modificação do sistema)
- [ ] Carregar ficheiros DATA e COFILES
- [ ] Importar OT
- [ ] Alterar camada de transporte do pacote /USDMT/USDMT na SE21
- [ ] Parametrizar tabela /USDMT/ACT_FUNCT em todos os ambientes
- [ ] Parametrizar tabela /USDMT/FUNC_ESP
- [ ] Parametrizar tabela /USDMT/FM_COLS
- [ ] Parametrizar tabela /USDMT/ALV_FIELD para DODES e DOREC
- [ ] Parametrizar tabela /USDMT/REGR_ZERO (Funcional)
- [ ] Parametrizar tabela /USDMT/CONTAS_BL (Funcional)
- [ ] <s>Criar layouts (/DODES, /DOREC, /VAL_DODES e /VAL_DOREC) para o cockpit (Funcional)</s>
- [ ] Criar PARAMETER ID (TPARA) com o nome /USDMT/ID_MAPA