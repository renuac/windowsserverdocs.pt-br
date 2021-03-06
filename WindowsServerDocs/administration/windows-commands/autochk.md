---
title: autochk
description: Tópico de referência para o comando autochk, que é executado quando o computador é iniciado e antes do Windows Server começar a verificar a integridade lógica de um sistema de arquivos.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 8787e6a3-f023-4ea5-b2d1-61c6876d8aff
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: a767e8f6cebee9c946f53e0403198384b7c0b790
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82718784"
---
# <a name="autochk"></a>autochk

É executado quando o computador é iniciado e antes do Windows Server começar a verificar a integridade lógica de um sistema de arquivos.

O **autochk. exe** é uma versão do **chkdsk** que é executada somente em discos NTFS e somente antes de o Windows Server ser iniciado. o **autochk** não pode ser executado diretamente da linha de comando. Em vez disso, o **autochk** é executado nas seguintes situações:

- Se você tentar executar **chkdsk** no volume de inicialização.

- Se **chkdsk** não puder obter uso exclusivo do volume.

- Se o volume for sinalizado como sujo.

## <a name="remarks"></a>Comentários

> [!WARNING]
> A ferramenta de linha de comando **autochk** não pode ser executada diretamente da linha de comando. Em vez disso, use a ferramenta de linha de comando **chkntfs** para configurar a maneira que você deseja que o **autochk** seja executado na inicialização.
>
> - Você pode usar o **chkntfs** com o parâmetro **/x** para impedir que o **autochk** seja executado em um volume específico ou em vários volumes.
>
> - Use a ferramenta de linha de comando **chkntfs. exe** com o parâmetro **/t** para alterar o atraso de Autochk de 0 segundo para até 3 dias (259.200 segundos). No entanto, um longo atraso significa que o computador não inicia até que o tempo decorra ou até que você pressione uma tecla para cancelar o **autochk**.

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [comando chkdsk](chkdsk.md)

- [comando chkntfs](chkntfs.md)
