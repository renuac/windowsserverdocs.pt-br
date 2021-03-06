---
title: montagem automática
description: Tópico de referência para o comando de montagem automática, que habilita ou desabilita o recurso de montagem automática.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 4635fc91-a477-4f17-8dcc-aa08854bfe45
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 0a3ff8782b2110dd1b8039477c0b748dc4ab8f44
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82718722"
---
# <a name="automount"></a>montagem automática

Aplica-se a: Windows Server (Canal Semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

> [!IMPORTANT]
> Em configurações de SAN (rede de área de armazenamento), desabilitar a montagem automática impede que o Windows monte automaticamente ou atribua letras de unidade a quaisquer novos volumes básicos visíveis ao sistema.

## <a name="syntax"></a>Sintaxe

automount [{habilitar | desabilitar | limpeza}] [NOERR]

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| enable | Permite que o Windows monte automaticamente novos volumes básicos e dinâmicos que são adicionados ao sistema e atribua a eles letras de unidade. |
| disable | Impede que o Windows monte automaticamente novos volumes básicos e dinâmicos que são adicionados ao sistema.<p>**Observação**: desabilitar a montagem automática pode fazer com que os clusters de failover falhem na parte de armazenamento do assistente para validar uma configuração. |
| scrubbing | Remove os diretórios de ponto de montagem de volume e configurações de registro para volumes que não estão mais no sistema. Isso impede que volumes que estavam anteriormente no sistema sejam montados automaticamente e recebam seus antigos pontos de montagem de volume quando são adicionados de volta ao sistema. |
| NOERR | Somente para scripts. Quando um erro é encontrado, o DiskPart continua processando comandos como se o erro não tivesse ocorrido. Sem esse parâmetro, um erro faz com que o DiskPart saia com um código de erro. |

## <a name="examples"></a>Exemplos

Para ver se o recurso de montagem automática está habilitado, digite os seguintes comandos de dentro do comando diskpart:

```
automount
```

Para habilitar o recurso de montagem automática, digite:

```
automount enable
```

Para desabilitar o recurso de montagem automática, digite:

```
automount disable
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [comandos do DiskPart](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc770877(v%3dws.11))
