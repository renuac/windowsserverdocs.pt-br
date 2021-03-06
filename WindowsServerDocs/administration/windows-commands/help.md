---
title: ajuda
description: Tópico de referência para o comando de ajuda, que exibe uma lista dos comandos disponíveis ou informações de ajuda detalhadas sobre um comando especificado.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: c65b5ac3-711a-4368-95b8-ba82e2d00713
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 9b73ef32b49b834a91f24e943749eb21398c8588
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83818656"
---
# <a name="help"></a>ajuda

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Exibe uma lista de comandos disponíveis ou informações de ajuda detalhadas sobre um comando especificado. Se usado sem parâmetros, lista de **ajuda** e descreve brevemente todos os comandos do sistema.

## <a name="syntax"></a>Sintaxe

```
help [<command>]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `<command>` | Especifica o comando para o qual exibir informações de ajuda detalhadas. |

### <a name="examples"></a>Exemplos

Para exibir informações sobre o comando **Robocopy** , digite:

```
help robocopy
```

Para exibir uma lista de todos os comandos disponíveis no DiskPart, digite:

```
help
```

Para exibir informações de ajuda detalhadas sobre como usar o comando **criar partição primário** no DiskPart, digite:

```
help create partition primary
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
