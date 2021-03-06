---
title: unlodctr
description: Tópico de referência para o Unlodctr, que remove nomes de contadores de desempenho e texto explicativo para um serviço ou driver de dispositivo do registro do sistema
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: fc8aa6f0-c1d9-47ea-937a-28152148e774
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 8551b6fc76984b06f28bdda92dcd63791721ec90
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83821286"
---
# <a name="unlodctr"></a>unlodctr

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Remove os nomes de **contadores de desempenho** e o texto **explicativo** para um serviço ou driver de dispositivo do registro do sistema.

## <a name="syntax"></a>Sintaxe
```
Unlodctr <DriverName>
```
#### <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
|\<> de driver|Remove as configurações do nome do contador de desempenho e o texto explicativo para driver ou serviço <DriverName> do registro do Windows Server 2003.|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários
> [!WARNING]
> A edição incorreta do Registro pode causar danos graves ao sistema. Antes de alterar o Registro, faça backup de todos os dados importantes do computador.

Se as informações fornecidas contiverem espaços, use aspas em volta do texto (por exemplo, <DriverName> ).

## <a name="examples"></a>Exemplos
Para remover as configurações atuais do registro de desempenho e o texto explicativo do contador para o serviço SMTP:
```
unlodctr SMTPSVC
```
## <a name="additional-references"></a>Referências adicionais
- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

