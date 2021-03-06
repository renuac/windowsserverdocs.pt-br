---
title: MLS FTP
description: Tópico de referência para o comando de MLS do FTP, que exibe uma lista abreviada de arquivos e subdiretórios em um diretório remoto.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 4738fd49-0e80-4bdf-a773-0f973db3a710
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 372c0b9a42fdfb8600083a301b71c37ada43c014
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83820389"
---
# <a name="ftp-mls"></a>MLS FTP

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Exibe uma lista abreviada de arquivos e subdiretórios em um diretório remoto.

## <a name="syntax"></a>Sintaxe

```
mls <remotefile>[ ] <localfile>
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `<remotefile>` | Especifica o arquivo para o qual você deseja ver uma listagem. Ao especificar *remotefiles*, use um hífen para representar o diretório de trabalho atual no computador remoto. |
| `<localfile>` | Especifica um arquivo local no qual armazenar a listagem. Ao especificar o *LocalFile*, use um hífen para exibir a listagem na tela. |

### <a name="examples"></a>Exemplos

Para exibir uma lista abreviada de arquivos e subdiretórios para *dir1* e *dir2*, digite:

```
mls dir1 dir2 -
```

Para salvar uma lista abreviada de arquivos e subdiretórios para *dir1* e *dir2* no arquivo local *DirList. txt*, digite:

```
mls dir1 dir2 dirlist.txt
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [Diretrizes adicionais de FTP](https://docs.microsoft.com/previous-versions/orphan-topics/ws.10/cc756013(v=ws.10))
