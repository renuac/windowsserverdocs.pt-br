---
title: nfsstat
description: Tópico de referência para o comando nfsstat, que exibe informações estatísticas sobre o NFS (sistema de arquivos de rede) e chamadas RPC (chamada de procedimento remoto).
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: da7a9768-44bd-404b-97ee-c388d00dc395
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 85eb1184d3eb8ee731cf698a6d805e3f11d878ce
ms.sourcegitcommit: 99d548141428c964facf666c10b6709d80fbb215
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "84721509"
---
# <a name="nfsstat"></a>nfsstat

Um utilitário de linha de comando que exibe informações estatísticas sobre o NFS (sistema de arquivos de rede) e chamadas de RPC (chamada de procedimento remoto). Usado sem parâmetros, esse comando exibe todos os dados estatísticos sem redefinir nada.

## <a name="syntax"></a>Sintaxe

```
nfsstat [-c][-s][-n][-r][-z][-m]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| -c | Exibe somente as chamadas NFS e RPC e NFS do lado do cliente enviadas e rejeitadas pelo cliente. Para exibir somente as informações de NFS ou RPC, combine esse sinalizador com o parâmetro **-n** ou **-r** . |
| -S | Exibe somente as chamadas NFS e RPC e NFS do lado do servidor enviadas e rejeitadas pelo servidor. Para exibir somente as informações de NFS ou RPC, combine esse sinalizador com o parâmetro **-n** ou **-r** . |
| -M | Exibe informações sobre os sinalizadores de montagem definidos por opções de montagem, sinalizadores de montagem internos ao sistema e outras informações de montagem. |
| -n | Exibe informações de NFS para o cliente e o servidor. Para exibir apenas as informações de cliente ou servidor NFS, combine esse sinalizador com o parâmetro **-c** ou **-s** . |
| -r | Exibe informações de RPC para o cliente e o servidor. Para exibir apenas as informações do cliente RPC ou do servidor, combine esse sinalizador com o parâmetro **-c** ou **-s** . |
| -Z | Redefine as estatísticas de chamada. Esse sinalizador só está disponível para o usuário raiz e pode ser combinado com qualquer um dos outros parâmetros para redefinir determinados conjuntos de estatísticas depois de exibi-los. |

### <a name="examples"></a>Exemplos

Para exibir informações sobre o número de chamadas RPC e NFS enviadas e rejeitadas pelo cliente, digite:

```
nfsstat -c
```

Para exibir e imprimir as informações relacionadas à chamada do NFS do cliente, digite:

```
nfsstat -cn
```

Para exibir informações relacionadas à chamada RPC para o cliente e o servidor, digite:

```
nfsstat -r
```

Para exibir informações sobre o número de chamadas RPC e NFS recebidas e rejeitadas pelo servidor, digite:

```
nfsstat -s
```

Para redefinir todas as informações relacionadas à chamada para zero no cliente e no servidor, digite:

```
nfsstat -z
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [Referência aos comandos dos Serviços para Network File System](services-for-network-file-system-command-reference.md)

- [Referência de cmdlets do NFS](https://docs.microsoft.com/powershell/module/nfs)
