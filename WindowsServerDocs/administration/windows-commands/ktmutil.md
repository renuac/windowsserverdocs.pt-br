---
title: ktmutil
description: Tópico de referência para o comando KTMUTIL, que inicia o utilitário Gerenciador de transações do kernel.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 53bc56df-f0e5-443b-ab20-bbf8b11d4a9a
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 9ca26d2289e32d8eb618ab7cc9393678a16e318b
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83817306"
---
# <a name="ktmutil"></a>ktmutil

Inicia o utilitário Gerenciador de transações do kernel. Se usado sem parâmetros, **KTMUTIL** exibirá os subcomandos disponíveis.

## <a name="syntax"></a>Sintaxe

```
ktmutil list tms
ktmutil list transactions [{TmGUID}]
ktmutil resolve complete {TmGUID} {RmGUID} {EnGUID}
ktmutil resolve commit {TxGUID}
ktmutil resolve rollback {TxGUID}
ktmutil force commit {GUID}
ktmutil force rollback {GUID}
ktmutil forget
```

## <a name="examples"></a>Exemplos


Para forçar uma transação incerta com GUID 311a9209-03f4-11dc-918f-00188b8f707b a ser confirmada, digite:

```
ktmutil force commit {311a9209-03f4-11dc-918f-00188b8f707b}
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)