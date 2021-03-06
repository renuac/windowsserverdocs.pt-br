---
title: árvore
description: Tópico de referência para árvore, que exibe a estrutura de diretório de um caminho, ou do disco em uma unidade, graficamente.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 345d3192-401e-4a3b-a8ac-36a85c7be79d
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 94b0429dadc3965c7e41ad5aa881fc902988ec9b
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721279"
---
# <a name="tree"></a>árvore

Exibe a estrutura de diretório de um caminho ou do disco em uma unidade graficamente.



## <a name="syntax"></a>Sintaxe

```
tree [<Drive>:][<Path>] [/f] [/a]
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|\<> da unidade:|Especifica a unidade que contém o disco para o qual você deseja exibir a estrutura do diretório.|
|\<Caminho>|Especifica o diretório para o qual você deseja exibir a estrutura de diretório.|
|/f|Exibe os nomes dos arquivos em cada diretório.|
|/a|Especifica que a **árvore** deve usar caracteres de texto em vez de caracteres gráficos para mostrar as linhas que vinculam subdiretórios.|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários

A estrutura exibida pela **árvore** depende dos parâmetros que você especificar no prompt de comando. Se você não especificar uma unidade ou caminho, a **árvore** exibirá a estrutura de árvore que começa com o diretório atual da unidade atual.

## <a name="examples"></a>Exemplos

Para exibir os nomes de todos os subdiretórios no disco na unidade atual, digite:
```
tree \
```
Para exibir uma tela de cada vez, os arquivos em todos os diretórios na unidade C, digite:
```
tree c:\ /f | more 
```
Para imprimir uma lista de todos os diretórios na unidade C, digite:
```
tree c:\ /f  prn 
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)