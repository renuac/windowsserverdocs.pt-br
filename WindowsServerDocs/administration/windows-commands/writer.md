---
title: gravador
description: Tópico de referência para o gravador, que verifica se um gravador ou componente está incluído ou exclui um gravador ou componente do procedimento de backup ou restauração.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 7cf98295-411d-4705-8573-f898ff45c140
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: aed202ac774b17041f48df24333565727b110c53
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82720638"
---
# <a name="writer"></a>gravador



Verifica se um gravador ou componente está incluído ou exclui um gravador ou componente do procedimento de backup ou restauração. Se usado sem parâmetros, o **Writer** exibirá a ajuda no prompt de comando.

## <a name="syntax"></a>Sintaxe

```
writer verify [<Writer> | <Component>]
writer exclude [<Writer> | <Component>]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro  |                                                                                      Descrição                                                                                      |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   verificar   | Verifica se o gravador ou o componente especificado está incluído no procedimento de backup ou restauração. O procedimento de backup ou restauração falhará se o gravador ou o componente não estiver incluído. |
|  exclude   |                                                   Exclui o gravador ou componente especificado do procedimento de backup ou restauração.                                                    |
| [\<> do gravador |                                                                                     <Component>]                                                                                      |

## <a name="examples"></a>Exemplos

Para verificar um gravador especificando seu GUID (para este exemplo, 4dc3bdd4-AB48-4d07-adb0-3bee2926fd7f), digite:
```
writer verify {4dc3bdd4-ab48-4d07-adb0-3bee2926fd7f}
```
Para excluir um gravador com o nome System Writer, digite:
```
writer exclude System Writer
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)