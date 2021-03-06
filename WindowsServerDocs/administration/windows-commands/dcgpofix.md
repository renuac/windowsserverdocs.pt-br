---
title: dcgpofix
description: Tópico de referência para o comando Dcgpofix, que recria os objetos de Política de Grupo padrão (GPOs) para um domínio.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 81d5fa65-2aea-49d3-b353-357441846c00
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: f11b7db8110cd2d7dcf08cd250eba411e7ff21a8
ms.sourcegitcommit: fad2ba64bbc13763772e21ed3eabd010f6a5da34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2020
ms.locfileid: "82993173"
---
# <a name="dcgpofix"></a>dcgpofix

Recria os objetos de Política de Grupo padrão (GPOs) para um domínio. Para acessar o Console de Gerenciamento de Política de Grupo (GPMC), você deve instalar o gerenciamento de Política de Grupo como um recurso por meio de Gerenciador do Servidor.

>[!IMPORTANT]
> Como prática recomendada, você deve configurar o GPO de política de domínio padrão somente para gerenciar as configurações de **políticas de conta** padrão, a política de senha, a política de bloqueio de conta e a política Kerberos. Além disso, você deve configurar o GPO de política de controladores de domínio padrão somente para definir direitos de usuário e políticas de auditoria.

## <a name="syntax"></a>Sintaxe

```
dcgpofix [/ignoreschema] [/target: {domain | dc | both}] [/?]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| /ignoreschema | Ignora a versão do esquema de Active Directory quando você executa esse comando. Caso contrário, o comando só funcionará na mesma versão do esquema que a versão do Windows na qual o comando foi enviado. |
| `/target {domain | dc | both` | Especifica se a política de domínio padrão deve ser direcionada, a política de controladores de domínio padrão ou ambos os tipos de políticas. |
| /? | Exibe a ajuda no prompt de comando. |

## <a name="examples"></a>Exemplos

Para gerenciar as configurações de **políticas de conta** padrão, a política de senha, a política de bloqueio de conta e a política do Kerberos, ao ignorar a versão do esquema de Active Directory, digite:

```
dcgpofix /ignoreschema /target:domain
```

Para configurar o GPO de política de controladores de domínio padrão somente para definir direitos de usuário e políticas de auditoria, enquanto ignora a versão do esquema de Active Directory, digite:

```
dcgpofix /ignoreschema /target:dc
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)