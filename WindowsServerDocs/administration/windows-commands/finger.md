---
title: finger
description: Tópico de referência para o comando Finger, que exibe informações sobre os usuários em um computador remoto especificado executando o serviço Finger ou o daemon.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 907ea637-5c6c-4752-84c2-46bbf2a68a33
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: a3403e10a1777bc117659eb052958d3a20668557
ms.sourcegitcommit: bf887504703337f8ad685d778124f65fe8c3dc13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83437231"
---
# <a name="finger"></a>finger

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Exibe informações sobre os usuários em um computador remoto especificado (normalmente um computador executando UNIX) que está executando o serviço Finger ou o daemon. O computador remoto especifica o formato e a saída da exibição de informações do usuário. Usado sem parâmetros, **Finger** exibe a ajuda.

> [!IMPORTANT]
> Esse comando estará disponível somente se o protocolo TCP/IP estiver instalado como um componente nas propriedades de um adaptador de rede em conexões de rede.

## <a name="syntax"></a>Sintaxe

```
finger [-l] [<user>] [@<host>] [...]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| -l | Exibe informações do usuário em formato de lista longa. |
| `<user>` | Especifica o usuário sobre o qual você deseja obter informações. Se você omitir o parâmetro *User* , esse comando exibirá informações sobre todos os usuários no computador especificado. |
| `@<host>` | Especifica o computador remoto que executa o serviço Finger em que você está procurando informações do usuário. Você pode especificar um nome de computador ou endereço IP. |
| /? | Exibe a ajuda no prompt de comando. |

#### <a name="remarks"></a>Comentários

- Você deve prefixar parâmetros de **dedo** com um hífen (-) em vez de uma barra (/).

- Vários `user@host` parâmetros podem ser especificados.

### <a name="examples"></a>Exemplos

Para exibir informações para *user1* no computador *users.Microsoft.com*, digite:

```
finger user1@users.microsoft.com
```

Para exibir informações para *todos os usuários* no computador *users.Microsoft.com*, digite:

```
finger @users.microsoft.com
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
