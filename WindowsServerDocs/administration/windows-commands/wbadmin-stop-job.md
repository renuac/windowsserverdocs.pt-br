---
title: Wbadmin parar trabalho
description: Tópico de referência para WBADMIN Stop Job, que cancela a operação de backup ou recuperação que está em execução no momento. As operações canceladas não podem ser reiniciadas — você deve executar novamente uma operação de backup ou recuperação cancelada desde o início.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 3b83b398-39c7-4410-bf17-5c1fb1a4f46d
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 6e6d2be62468102060aad502d47efbb6eae4fca8
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83821356"
---
# <a name="wbadmin-stop-job"></a>Wbadmin parar trabalho



Cancela a operação de backup ou recuperação que está em execução no momento. As operações canceladas não podem ser reiniciadas — você deve executar novamente uma operação de backup ou recuperação cancelada desde o início.

Para interromper uma operação de backup ou recuperação com este subcomando, você deve ser membro do grupo **operadores de backup** ou do grupo **Administradores** ou ter recebido a autoridade apropriada. Além disso, você deve executar o **Wbadmin** em um prompt de comandos com privilégios elevados. (Para abrir um prompt de comando com privilégios elevados, clique com o botão direito do mouse em **prompt de comando** e clique em **Executar como administrador**.)

## <a name="syntax"></a>Sintaxe

```
wbadmin stop job
[-quiet]
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|-quiet|Executa o subcomando sem prompts para o usuário.|

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
-   [Wbadmin](wbadmin.md)