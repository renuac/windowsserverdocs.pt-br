---
title: Conjunto de subcomandos-DriverPackage
description: Tópico de referência para subcomando set-DriverPackage, que renomeia e/ou habilita ou desabilita um pacote de driver em um servidor.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 11804bb6-ca29-4461-8c63-5131748cd742
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 40a812e785df6820da404a8951af6731cced15d3
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721718"
---
# <a name="subcommand-set-driverpackage"></a>Subcomando: Set-DriverPackage

Renomeia e/ou habilita ou desabilita um pacote de driver em um servidor.

## <a name="syntax"></a>Sintaxe

```
WDSUTIL /Set-DriverPackage [/Server:<Server name>] {/DriverPackage:<Name> | /PackageId:<ID>} [/Name:<New Name>] [/Enabled:{Yes | No}
```

### <a name="parameters"></a>Parâmetros

|        Parâmetro         |                                                                                                                                                                                                               Descrição                                                                                                                                                                                                                |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [/Server:\<nome do servidor>] |                                                                                                                                                 Especifica o nome do servidor. Pode ser o nome NetBIOS ou o FQDN. Se um nome de servidor não for especificado, o servidor local será usado.                                                                                                                                                 |
| [/DriverPackage:\<nome>] |                                                                                                                                                                                       Especifica o nome atual do pacote de driver a ser modificado.                                                                                                                                                                                        |
|    [/PackageId:\<ID>]    | Especifica a ID dos serviços de implantação do Windows do pacote de driver. Você deve especificar essa opção se o pacote de driver não puder ser identificado exclusivamente pelo nome. Para localizar essa ID para um pacote, clique no grupo de drivers no qual o pacote está (ou no nó **todos os pacotes** ), clique com o botão direito do mouse no pacote e clique em **Propriedades**. A ID do pacote é listada na guia **geral** . Por exemplo: {DD098D20-1850-4FC8-8E35-EA24A1BEFF5E}. |
|   [/Name:\<novo nome>]    |                                                                                                                                                                                              Especifica o novo nome para o pacote de driver.                                                                                                                                                                                              |
|      [/Enabled: {Sim      |                                                                                                                                                                                                                   Foi                                                                                                                                                                                                                    |

## <a name="examples"></a>Exemplos

Para alterar as configurações de um pacote, digite um dos seguintes:
```
WDSUTIL /Set-DriverPackage /PackageId:{4D36E972-E325-11CE-BFC1-08002BE10318} /Name:MyDriverPackage
```
```
WDSUTIL /Set-DriverPackage /DriverPackage:MyDriverPackage /Name:NewName /Enabled:Yes
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)