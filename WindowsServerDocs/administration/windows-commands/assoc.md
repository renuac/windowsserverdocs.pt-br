---
title: assoc
description: Tópico de referência para o comando Assoc, que exibe ou modifica associações de extensão de nome de arquivo.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 237bedda-b24c-4fec-a39c-9b7eacf96417
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 58735201a1a0711db4d0cee9c292363acf5121f3
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83819636"
---
# <a name="assoc"></a>assoc

Exibe ou modifica associações de extensão de nome de arquivo. Se usado sem parâmetros, **assoc** exibe uma lista de todas as associações de extensão de nome de arquivo atuais.

> [!NOTE]
> Só há suporte para esse comando no cmd. exe e ele não está disponível no PowerShell.

## <a name="syntax"></a>Sintaxe

```
assoc [<.ext>[=[<filetype>]]]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `<.ext>` | Especifica a extensão de nome de arquivo. |
| `<filetype>` | Especifica o tipo de arquivo a ser associado à extensão de nome de arquivo especificada. |
| /? | Exibe a ajuda no prompt de comando. |

### <a name="remarks"></a>Comentários

- Para remover a associação de tipo de arquivo para uma extensão de nome de arquivo, adicione um espaço em branco após o sinal de igual pressionando a barra de espaços.

- Para exibir os tipos de arquivo atuais que têm cadeias de comando abertas definidas, use o comando **ftype** .

- Para redirecionar a saída de **assoc** para um arquivo de texto, use o `>` operador de redirecionamento.

## <a name="examples"></a>Exemplos

Para exibir a associação de tipo de arquivo atual para a extensão de nome de arquivo. txt, digite:

```
assoc .txt
```

Para remover a associação de tipo de arquivo para a extensão de nome de arquivo. bak, digite:

```
assoc .bak=
```

> [!NOTE]
> Certifique-se de adicionar um espaço após o sinal de igual.

Para exibir a saída de **assoc** uma tela por vez, digite:

```
assoc | more
```

Para enviar a saída de **assoc** para o arquivo Assoc. txt, digite:

```
assoc>assoc.txt
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [comando ftype](ftype.md)
