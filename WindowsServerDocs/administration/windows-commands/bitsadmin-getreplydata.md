---
title: bitsadmin getreplydata
description: Tópico de referência para o comando Bitsadmin getreplydata, que recupera os dados de upload-resposta do servidor em formato hexadecimal para o trabalho.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 819f97d5-b255-4b2d-9f63-0daa73915434
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: ea2a82403fe05776abbbf65e87a4b6e72c8767b8
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82717624"
---
# <a name="bitsadmin-getreplydata"></a>bitsadmin getreplydata

Recupera os dados de resposta de upload do servidor em formato hexadecimal para o trabalho.

> [!NOTE]
> Esse comando não tem suporte no BITS 1,2 e versões anteriores.

## <a name="syntax"></a>Sintaxe

```
bitsadmin /getreplydata <job>
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| -------------- | -------------- |
| trabalho | O nome de exibição ou o GUID do trabalho. |

## <a name="examples"></a>Exemplos

Para recuperar os dados de resposta de upload para o trabalho chamado *myDownloadJob*:

```
bitsadmin /getreplydata myDownloadJob
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [comando Bitsadmin](bitsadmin.md)
