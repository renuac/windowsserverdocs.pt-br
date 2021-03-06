---
title: LCD de FTP
description: Tópico de referência para o comando de LCD de FTP, que altera o diretório de trabalho no computador local.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 60a25808-6abb-408b-8373-0bbdcd0994b4
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c941adcc8c56d2598ad4ff56852309a256656878
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83820126"
---
# <a name="ftp-lcd"></a>LCD de FTP

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Altera o diretório de trabalho no computador local. Por padrão, o diretório de trabalho é o diretório no qual o comando de **FTP** foi iniciado.

## <a name="syntax"></a>Sintaxe

```
lcd [<directory>]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `[<directory>]` | Especifica o diretório no computador local para o qual alterar. Se o *diretório* não for especificado, o diretório de trabalho atual será alterado para o diretório padrão. |

### <a name="examples"></a>Exemplos

Para alterar o diretório de trabalho no computador local para *c:\Dir1*, digite:

```
lcd c:\dir1
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [Diretrizes adicionais de FTP](https://docs.microsoft.com/previous-versions/orphan-topics/ws.10/cc756013(v=ws.10))
