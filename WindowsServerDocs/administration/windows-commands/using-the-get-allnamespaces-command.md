---
title: obter namespaces
description: Tópico de referência para Get-MyNamespaces, que exibe informações sobre todos os namespaces em um servidor.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: e8fe896d-a69a-4180-923b-9f18185f5941
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 710918eb11ef7a746716a1a2bff9200cfa1d98c1
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82720003"
---
# <a name="get-allnamespaces"></a>obter namespaces

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Exibe informações sobre todos os namespaces em um servidor.

## <a name="syntax"></a>Sintaxe
Windows Server 2008:
```
wdsutil /Get-AllNamespaces [/Server:<Server name>] [/ContentProvider:<name>] [/Show:Clients] [/ExcludedeletePending]
```
Windows Server 2008 R2:
```
wdsutil /Get-AllNamespaces [/Server:<Server name>] [/ContentProvider:<name>] [/details:Clients] [/ExcludedeletePending]
```
### <a name="parameters"></a>Parâmetros

|         Parâmetro         |                                                                               Windows Server 2008                                                                               | Windows Server 2008 R2 |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|
|  [/Server:<Server name>]  | Especifica o nome do servidor. Pode ser o nome NetBIOS ou o FQDN (nome de domínio totalmente qualificado). Se nenhum nome de servidor for especificado, o servidor local será usado. |                        |
| [/ContentProvider:<name>] |                                                        Exibe somente os namespaces para o provedor de conteúdo especificado.                                                         |                        |
|      [/Show: clients]      |                            Com suporte apenas para o Windows Server 2008. Exibe informações sobre os computadores cliente que estão conectados ao namespace.                             |                        |
|    [/details: clientes]     |                           Com suporte apenas para o Windows Server 2008 R2. Exibe informações sobre os computadores cliente que estão conectados ao namespace.                           |                        |
|  [/ExcludedeletePending]  |                                                              Exclui todas as transmissões desativadas da lista.                                                              |                        |

## <a name="examples"></a>Exemplos
Para exibir todos os namespaces, digite:
```
wdsutil /Get-AllNamespaces
```
Para exibir todos os namespaces, exceto aqueles que estão desativados, digite:
- Windows Server 2008
  ```
  wdsutil /Get-AllNamespaces /Server:MyWDSServer /ContentProvider:MyContentProv /Show:Clients /ExcludedeletePending
  ```
- Windows Server 2008 R2
  ```
  wdsutil /Get-AllNamespaces /Server:MyWDSServer /ContentProvider:MyContentProv /details:Clients /ExcludedeletePending
  ```
  ## <a name="additional-references"></a>Referências adicionais
  - [Chave](command-line-syntax-key.md)
  de sintaxe de linha de comando
  [usando o comando New-namespace](using-the-new-namespace-command.md)usando o subcomando de
  [comando Remove-namespace](using-the-remove-namespace-command.md)[: Start-namespace](subcommand-start-namespace.md)
